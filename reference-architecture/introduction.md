# INTRODUCTION

## Introduction to the BDI Reference Architecture

The Basic Data Infrastructure Framework (BDI) is an infrastructure framework for controlled data sharing, supporting automated advanced information logistics in the physical economy. Departing from traditional messaging paradigms, the BDI shifts towards event-driven data collection at the source, fostering efficient and secure coordination through proven publish-and-subscribe architectures.

This introduction provides a short overview of some issues which play a role in the design of the architecture. We start with some observations about data in a logistic environment. These observations are used in the formulation of architectural principles which are in turn the basis of BDI building blocks. Finally, these building blocks are grouped in functional subsets called KITs.

See [bdinetwork.org](https://bdinetwork.org) for a full account of these concepts.

## 1. Observations&#x20;

* The data exchange patterns in typical operational networks are a result of “doing business” have specific characteristics:
  * The network of involved parties is driven by the fulfillment of an assignment - these networks are temporary and fluid, that is, members are added whenever necessary and the network is dissolved when the job is done.&#x20;
  * Data exchanges are between members of a closed group, i.e. the members are vetted in advance.
  * There can be time constraints on the exchange of data.
* A common data exchange infrastructure for operational networks should support:
  * Dynamic instances
  * Multiple concurrent instances
  * Controlled event-driven exchange
* Event-driven exchange of operational data within an instance must be:
  * Efficient: no polling, no unnecessary retrieval
  * Effective: easy distribution to multiple parties simultaneously&#x20;
  * Controlled:&#x20;
    * Limited exposure to malicious actors.
    * Only authorized parties can retrieve information.
    * Role based data access.
    * The Data Owner tracks access, providing a clear audit trail.
* The value of data:
  * Data has value
  * Data owners want to protect and monetize this value
* The importance of trust in global business networks
  * Identification authentication and authorization play an important role in establishing trust.
  * Zero trust - do not trust anyone before trust is established.
  * Perimeterless trust - do not base trust on membership of a closed group of trusted parties

## 2. The Core Principles

Based on these observations, seven principles were formulated to guide the design of the architecture. These are:

1. Support of operational activities in the physical economy
2. Time-sensitive event-driven coordination between entities
3. Zero Trust
4. Dynamic Data Life Cycle
5. Data sovereignty by maintaining data at the source
6. Subsidiarity of governance
7. Coherent security

### Principle 1: Support operational activities in the physical economy

The BDI Framework is optimized to support value creation in the physical economy. The focus is on the data exchanges necessary for operational activities of (multiple, specialized) entities that:

* need to coordinate and report their activities to fulfill their commitments to their principal(s)
* need to perform a public task, like verifying compliance to regulations of activities of others

In the physical economy legal entities are represented by both IT-systems/processes and natural persons. To be able validate the mandate and if necessary the professional qualifications of the representatives is imperative, as the legal entities assume the liability and accountability for actions of the representatives.

### Principle 2: Time-sensitive event-driven coordination between entities

Coordination of operational activities is time-sensitive and drives a large part of data exchanges between entities, even if these entities have no direct contractual relationship. Data exchanges therefore cross organizational boundaries, between multiple entities, each with its own security policy and protective measures such as firewalls.

Data exchanges are triggered by _events_ in the physical economy.  Events may be relating to planning agreements and updates, payments, compliance, physical activities and the like.

Whenever an event occurs, a _notification_ about this event can be generated. A notification is a digital message containing meta data about the event. This notification is distributed to a selective group of entities using a publication/subscription  based technology.

Notifications are published on a _channel_ and parties may choose to receive notifications on a channel (subscription). The set of channels and the rules on allowed subscriptions (defining who is able to subscribe on a channel) must be defined before hand.

Note that data associated with an event is not included in the notification. Authorised parties can retrieve data at the source.

### Principle 3: Zero Trust

Trust is an important issue in doing business. However, trust is not easily established. Each entity in a cooperative network may have its own policy to assign trust to its business partners, which may even vary between interactions. To support these flexible trust policies, the BDI framework is based on perimeter-less, zero trust principles.

#### Zero Trust:

* doing business in a global economy requires flexibility in choosing business partners.
* entities have to be able to deal with previously unknown sub-subcontractors that pop-up when they are subcontracted by another entity in the same virtual instance.
* each entity is autonomous in deciding what an acceptable risk/reward trade-off is, per transaction.

#### Perimeter-less Trust:

* trust is not delegated to a Trust Anchor or an Authority
* authentication does not equal trust
* trust is contextual and situational: for instance on how sensitive the data-element is
* reputation is an important aspect of assessing trust
* federation of trust information exchanges between entities or groups of entities

### Principle 4: Dynamic Data Life Cycle

Data relevant for operational activities has a dynamic life cycle: from proposed, planned, to in transit, modified, to registration of as executed.

The BDI acknowledges the stadia and fluidity of coordination in real life.

### Principle 5: Data sovereignty by data at the source

Data sovereignty requires control of data access by the data owner.

Notifications of events are generated by the “owner” of an event and the corresponding data, and distributed to a selective group of entities . Notifications communicate meta-data of an event to a selection of stakeholders, and allow them to link back to the data source to request specific data of the event.

The request itself allows the data owner to:

* Track what entity has requested access
* Authenticate the entity
* Asses the trust in this context
* Authorize selective access

### Principle 6: Subsidiarity of governance

It is common practice in most business sectors to have specific sector agreements (legal, organizational, semantic) such as:

* standards
* regulations
* rules of engagement
* processes
* roles and responsibilities

Standardization and generalization is a means to improve efficiency and reduce costs. But innovation and competitiveness depends on differentiation, specialization and the freedom to invent new offerings.

Subsidiarity is a principle of organization that states that issues should be dealt with at the most immediate or local level that is consistent with their resolution.

The governance recommendations of the BDI Framework follow the subsidiarity principle: common agreements between entities need to fit the structure of the market, legal frameworks and local habits and should not be defined at higher overarching levels.

### Principle 7: Coherent security

The (IT- and operational) security of the data exchanges relies on the coherence of:

* the individual components and protocols as implemented by each entity in the association
* the interaction of components and protocols
* the interoperability of logging and other security audit trails
* operational security and governance measures

The BDI provides for a coherent security framework among these disparate entities

## 3. BDI Stack and KITs

To assist the creation of applications according to the architectural principles, BDI defines many _building blocks_, where each building block provides tools and guidelines to implement parts of the required functionality. The building blocks are shown in the BDI stack:

<figure><img src="../.gitbook/assets/BDI building blocks.png" alt=""><figcaption><p>Overview of BDI building blocks</p></figcaption></figure>

Implementation of the principles by means of parts of the stack is aided by the definition of _KITs_.

A KIT is a subset of the BDI stack that forms a coherent capability. Implementing a KIT  makes it easier to start with a minimal viable subset and add additional funtionality later as the need for it arises.
