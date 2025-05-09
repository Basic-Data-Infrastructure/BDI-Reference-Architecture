---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Event Choreography

Choreography of Principals and subcontractors: balancing effectivity with security.

### 1. Choreography of event distribution

In supply chains the chain of business activities starts when a Seller and Buyer agree upon the transaction. This agreement typically includes terms related to transport, insurance, customs, the handover of responsibilities, and payments. The successful execution of this agreement often requires coordination among a large set of actors, including authorities and their subcontractors. This coordination is managed through a "choreography" of actions, where each action is triggered by planned or executed events.

### 2. Subcontractors and principals

In this context, the Seller and Buyer serve as the Principals, each responsible for their part of the agreement. Typically, each Principal selects preferred contractors to fulfil their portion of the agreement. These main contractors, in turn, become Principals to their own subcontractors, and this chain continues down the line.

The key challenge here is distributing notifications within this dynamic and temporary data exchange network, to ensure effective and efficient coordination of activities, without overburdening the network with traffic.

### 3. Provisioning an instance

The BDI framework assumes that commercial relationships between Principals and Subcontractors are established before any actual orders are placed. In this setup, URLs are known, and through the DNS  discovery mechanism, the URIs of endpoints for each party are also known. Digital identity and trust are established within the respective associations of each party.

Each Principal is responsible for provisioning a temporary network of subcontractors associated with a specific order.

### 4. Channels {#channels}

Principals and their subcontractors communicate through channels (a.k.a. topics in a pub/sub setting). There are three kinds of channels:

* Subcontractor specific - often a principal works for different orders with a limited set of partners (preferred suppliers). There is a private channel between the principal and each partner. These channels are bidirectional (both the principal and the subcontractor can post notifications). A subcontractor specific channel exists as long as the relation between principal and subcontractor exists and hence may exceed the lifetime of a specific order.
* Order specific - a principal creates a channel specific to the execution of a particular order. Such a channel is unidirectional: the principal is the only party who is allowed to post notifications, all involved subcontractors subscribe to this channel and are therefore notified of each message sent by the principal. Order specific channels exist for the duration of the order only.
* Subject specific - often orders get bundled and unbundled during transport, for instance, being added to a container or ship. In these cases, the subject of the events shift from order to container to ship and, eventually, back to container and order. These are unidirectional channels: the origin (transporter, terminal etc.) of the events is the only producer on these channels.  It's up to the consumer of the events to switch channels when the subject shifts, for instance, when a container is loaded on a ship.  The duration of the channel depends on the lifetime of the subject.

The latter subject specific channel may be considered a low-level channel.  The events on these channels need more advanced tracking, due to the shifting subject, and may end up repackaged on the subcontractor / order specific channels.

### 5. Semantics and Lifecycle

In order to allow a consuming party to correctly interpret events, the publishing party must clearly document:

* Which events are published;
* When events are published;
* What it means when they are published;
* What sequences of events can be expected;
* What to do when an event seems to be missing or out of order;
* When a consumer should no longer expect events (see also [Closing the Order and Dissolving the Network](#closing-and-dissolving)).

Translating, repackaging, and/or combining events for consumption by other systems will rely heavily on the above documentation and need documentation of their own.  In addition these processes also need to document:

* What information is lost and what is the consequence of that loss;
* What information is added, for example, to fulfil a constraint to the target system.

### 6. Bootstrapping

The Principal publishes a specific notification to a subcontractor, with metadata on “Request order”. The data accessed by the subcontractor includes the details of the order request. The subcontractor responds with a notification containing metadata on order acceptance. The Principal then accesses the data to confirm the subcontractor's acceptance and any additional details provided.

### 7. Common Order Log

Upon confirmation, the Principal adds the subcontractor as a subscriber to the common Order Log and posts this event in the Common Order Log. The Common Order Log creates notifications to all relevant parties when an event is posted by (or on behalf of) the Principal.

### 8. Provisioning of Closed Network

To secure and streamline interactions within the temporary network, the Principal sends a JWT (JSON Web Token) to the subcontractor. This "Subco" JWT contains:

* Order Information: Specific details about the order.
* Role of the Subcontractor: Defining the subcontractor's role within the order.
* Data Access Rights: Permissions tied to the subcontractor’s role, aligned with an agreed-upon or standardized semantic model.

The subcontractor uses this JWT token when interacting with other subcontractors within the context of the order. This token allows other subcontractors to:

* Validate the Subcontractor’s Role: Confirming that the subcontractor is part of the temporary network set up by the Principal.
* Verify Access Rights: Ensuring that the subcontractor has the appropriate rights to access data associated with the order.

The Principal repeats this process with all subcontractors until the provisioning of the network is complete.

### 9. Dynamic modification

In real-world operations, it may become necessary to change subcontractors dynamically; removing one subcontractor from the network and replacing them with another.

To facilitate this, the Principal posts a notification of the change to the Order Log. This notification is then distributed to all parties involved in the network. The following steps are taken:

* Remove the old subcontractor: The old subcontractor is removed from the subscription lists, cutting off their access to further notifications and data.
* Revoke the old JWT Token: The JWT token that was issued to the old subcontractor is revoked, ensuring that they no longer have access to the network's resources.
* Add the new subcontractor: The new subcontractor is added to the network, receiving the necessary notifications and access rights.
* Create a JWT for the new subcontractor.

### 10. Managing the number of interactions

One potential pitfall of distributing notifications of events is the exponential increase in the number of interactions (API-calls, identity checks, authorization checks) with the number of participants/subcontractors in the temporary network.

There are three strategies to manage the number and costs of interactions.

#### 10.1. Star-like interactions with Principal

A subcontractor communicates most of the notifications to the Principal, one-on-one. The Principal filters notifications and posts only relevant events or notifications from all parties to the Common Order Log.

This limits the information overload while ensuring that all relevant parties are informed of relevant events.

#### 10.2. Low-risk data in notification

Notifications are sent to a closed network of parties. Some data of an event may be low-risk and can be embedded in the notification within the closed network: for example "ETA delayed by 12 hrs". The straightforward embedding reduces the need to collect the information at the source.

In this strategy, the value of the data is used to simplify the process, increasing efficiency and reducing costs. It is a business decision to balance the loss of value of the data and the gains of increased efficiency.

#### 10.3. Caching authorization results for common roles

Common roles have known authorization rules. The results of data selection for these roles may be cached near the BDI-API, reducing the need to evaluate policies in the Authorization Register.

#### 10.4. Subject versus Order / Subcontractor specific channels

The use of subject specific channels (see also [Channels](#channels)) can drastically reduce the amount of events triggered because, for instance, an event about transport equipment relates to multiple orders and (in some cases) subcontractors.

### 11. Creating an auditable log

Once all tasks related to the order have been completed, the Principal generates a signed log. This log serves as an official record of all events and actions that took place during the order's execution.

* Notification of Log Availability: A notification is sent to all parties involved, informing them that the signed log is available.
* Access and Retention: Subcontractors can access this signed log and retain a copy for future reference, whether for compliance purposes or in the event of a dispute.

This structured audit trail ensures transparency, accountability, and the ability to review and verify all actions taken during the course of the order, providing a solid foundation for trust and compliance in the BDI framework.

### 12. Closing the Order and Dissolving the Network {#closing-and-dissolving}

Once all tasks related to the order have been executed, the Principal initiates the closure of the order by:

* Distributing a Closure Notification: Informing all parties that the order is complete.
* Removing Subscriptions: Subscriptions to the Order Log are removed after a specified period.
* Revoking JWT Tokens: Invalidating the JWT tokens to dissolve the temporary network.

This process ensures the temporary network is securely dismantled, preserving the integrity and confidentiality of the data exchanged during the order's execution.

### 13. Querying for missed events

Parties may be late subscribing to channels for different reasons or need to recover from system failures, in those cases these systems need to have access to earlier events they have missed to (re)build their state.

### 14. Audit trail

Event driven coordination requires a means to “go back in time”, inspect earlier events and have an audit trail.  One obvious reason is when a subcontractor is changed: the new subcontractor has to be able to quickly come up to speed on the history of events. The second is to have a common reference for either compliance or settling of disputes.



{% file src="../../.gitbook/assets/2023-BDI-Event-Distributie-PoC.pdf" %}
