# INTRODUCTION

## Introduction to the BDI Reference Architecture

The Basic Data Infrastructure Framework (BDI) is an infrastructure framework for controlled data sharing, supporting automated advanced information logistics between entities acting in the physical economy.

The BDI is based on 7 core principles.

The main drivers of these principles are:

1. the data exchange characteristics in typical OSCM networks
2. what a common data exchange infrastructure should support
3. how the value of data is created
4. the relation between Identification, Authentication and Authorization (IAA) and trust
5. the implications of perimeter-less trust

Implementing the core principles can be done in stages: the BDI Framework defines “kits” as logical combinations of components in the BDI Stack, fit for implementation.

The description of the BDI Reference Architecture starts by following the taxonomy of the BDI Stack by describing the building blocks.

\[ daarna…..Kits, Security, meer intergrale zaken?]

## 1. The 7 Core Principles

The 7 core principles of the BDI are:

### Principle 1: Support operational activities in the physical economy

The BDI Framework is optimized to support value creation in the physical economy. The focus is on the data exchanges necessary for operational activities of (multiple, specialized) entities that:

* need to coordinate and report their activities to fulfill their commitments to their principal(s)
* need to perform a public task, like verifying compliance to regulations of activities of others

In the physical economy legal entities are represented by both IT-systems/processes and natural persons. To be able validate the mandate and if necessary the professional qualifications of the representatives is imperative, as the legal entities assume the liability and accountability for actions of the representatives.

### Principle 2: Time-sensitive event-driven coordination between entities

Coordination of operational activities is time-sensitive and drives a large part of data exchanges between entities, even if they have no direct contractual relationship. The driver of these exchanges is an event related to the project or order at hand. Events may be relating to planning agreements and updates, payments, compliance, physical activities and the like.

Notifications (meta-data) of events are generated by the “owner” of an event and distributed to a selective group of entities. The distribution pattern of notifications of events is set-up and coordinated (choreography) by the Principal that originates the common task at hand.

Data exchanges therefore cross organizational boundaries: that fact that entities may have different security policies and protective measures such as firewalls has to be taken into account.

The instance of a (virtual) closed network of parties involved is particular to the order, created when the order starts, dissolved after the order is fulfilled.

* Preferred suppliers may participate repeatedly in fulfilling orders.
* Authorities (compliance check) are involved, dependent on applicable regulations.

The implication is that entities have a business relationship that is established before starting the data exchange.

The second implication is that an entity may participate in multiple concurrent dynamically created (and later dissolved) instances of virtual data exchange networks .

### Principle 3: Zero Trust

The BDI Framework is based on Zero Trust principles.

* doing business in a global economy requires flexibility in choosing business partners.
* entities have to be able to deal with previously unknown sub-subcontractors that pop-up when they are subcontracted by another entity in the same virtual instance.
* neach entity is autonomous in deciding what an acceptable risk/reward trade-off is, per transaction.

The BDI is based on “perimeter-less trust”:

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

* Track what entity has requested access (when)
* Authenticate the entity (who)
* Asses the trust in this context (why and if)
* Authorize selective access (what)

### Principle 6: Subsidiarity of governance

It is common practice in most business sectors to have specific sector agreements (legal, organizational, semantic) such as:

* semantic standards
* regulations
* rules of engagement
* processes
* roles and responsibilities

Local cultural or specific regulations may add to this variety

Furthermore: innovation, competitiveness and making money depends on differentiation, specialization and the freedom to invent new offerings.

Subsidiarity is a principle of organization that holds that issues should be dealt with at the most immediate or local level that is consistent with their resolution.

The governance recommendations of the BDI Framework follow the subsidiarity principle: common agreements between entities need to fit the structure of the market, legal frameworks and local customs.

### Principle 7: Coherent security

The (IT- and operational) security of the data exchanges relies on the coherence of:

* the individual components and protocols as implemented by multiple entities,
* the interaction of components and protocols
* the interoperability of logging and other security audit trails
  * analyzing a potential breach requires the combination of logs of systems
* operational security and governance measures

## 2. Data exchange characteristics

The operational data exchange patterns that are a result of “doing business” have specific characteristics. An example from supply chains shows the characteristics:

### Order driven operational network of parties

1. Buyer and Seller agree upon conditions for a specific order, which results in shipments and consignments that need to be transported and handed over between Seller and Buyer.
2. Buyer and Seller subcontract their part (as agreed upon) of the fulfillment of the order to various specialized parties, who subcontract often parts of their commitments to other parties.
3. The network of parties involved is particular to the order, created when the order starts, dissolved after the order is fulfilled.
   * Preferred suppliers participate repeatedly in fulfilling orders.
   * Authorities (compliance check) are involved, dependent on applicable regulations.

The implication is that entities have a business relationship that is established before starting the data exchange: the decision to do business with each other, and the vetting of each other (conditions, price, payment terms, liabilities, creditworthiness etc.) is done outside the scope of an operational data exchange network

### Closed group data exchanges

* Data exchanges that are necessary to let this order-driven operational network cooperate and fulfill the commitments are limited to the parties involved per instance, and specific for each role.

### Coordination is time sensitive

* The dominant reason for data exchanges are agreements/commitments, coordination of activities (planning, in transit adjustments, fulfilled) and proof (of compliance or fulfillment of contractual obligations).
* The majority of data exchanges is time sensitive.

### Specific semantics, regulations and rules of engagement

* Each type of goods and business sector has its own particular set of rules and regulations:
  * Semantics (meaning of terms).
  * Processes, obligations and liabilities (rules of engagement).
  * Roles and responsibilities.
  * Regulations.
* They are often already existing, part of the “tricks of the trade” body of knowledge and supported by trade bodies for a sector and/or standardization bodies (UNCFACT, GS1, others)

### Liability in representation and qualification

* Persons or systems act as representative of a legal entity: the legal entity is liable for actions of the representative, if they act within their mandate.
* A person might have professional qualifications that are required for the task at hand: the entity is however liable and must verify if these qualifications are valid.

## 3. Common infrastructure

The infrastructure for data exchanges in BDI must :

* support the dynamic order-driven creation and dissolvement of (virtual) instances of operational networks per order, with potentially a different set of entities per instance.
  * The practice of sub-subcontracting by entities involved means that the number of entities in an instance is dynamic: sub-subcontractors that have not been identified at the start may be added (or removed) later in time. This practice has serious implications for managing IAA and Trust in a globalized economy: what trust to place in subcontractors of unknown origins that pop up suddenly?
* support the controlled, event-driven exchange of operational data within an instance.
  * Controlled means: control over the value of data as exchanged. The value of data is context, time and agency dependent (see chapter 4).
* allow each entity to participate in data exchanges in multiple concurrent instances, which are virtually isolated from each other.
  * A company executes multiple orders concurrently. Larger businesses operate in multiple sectors simultaneously.
* allow for specific semantics, regulations and rules of engagement per instance.
  * Innovation, competitiveness and making money depends on differentiation, specialization and the freedom to invent new offerings.
  * Local habits and regulations may be important to accommodate.
* allow for liability verification of representation of systems/processes and natural persons, and the professional qualifications of representatives
* allow for exchanges across the IT-system boundaries (firewall, policies etc.)

## 4. Controlling the value of data

The data exchange is between entities that have a business relationship, or perform a public task (compliance check for instance).

The value of the data as exchanged is created by the combination of:

* The context of the data
  * context gives meaning to data (even the absence of data may have meaning in a given context)
  * the same data in a different context has a different meaning to a different actor
* The timing: when is the meaning revealed to an actor?
  * before an event, or afterwards makes potentially a lot of difference
* The agency of the actor : can he/she act upon the revealed meaning?
  * power, capabilities, resources
  * role and responsibilities

Data exchange can therefore lead to value exchange, value creation or loss of value for the data owner. Or even risks for the data owner.

The BDI framework supports a data owner in controlling the value creation:

* in controlling when an actor is notified of the existence of new relevant data of an event, and tracking if the actor has requested access (when).
* in defining the closed/limited set of actors that is notified and is allowed conditional access to specific data (who).
* in authenticating any actor that desires access to data, and if this actor is related to specific data (why).
* in assessing how much trust can be placed in that actor (if).
* in authorizing limited access (time, data elements) for an actor that desires access in reaction to distributed notifications (what).

This control cannot be implemented by creating a “walled garden”, only accessible by trusted and vetted parties, checked for compliance by an Authority:

* doing business in a global economy requires flexibility in choosing business partners
* there is no single Authority imaginable in the near future that would span the global economy
* each entity is autonomous in deciding what an acceptable risk/reward trade-off is, per transaction.
* one has to be able to deal with unknown sub-subcontractors that pop-up when they are subcontracted by another entity.

Another way of describing a “walled garden” is “perimeter-based trust”: any party inside the perimeter is deemed to be trustworthy. The opposite is “perimeter-less trust”: each entity creates its own perimeter and decides the trustworthiness of their business partners.

This perimeter may be set up and managed individually, or established by a group/cooperative/Association as this would create efficiency.

Groups/Associations may choose to federate and use the BDI framework to exchange authentication and trust information.

## 5. Trust and IAA

Trust , identification, authentication and authorization (IAA) are related but not equivalent concepts.

* **Identification** is: assigning an unique identifier a person or entity or IT-system.
* **Authentication** is: verifying a claim that a person, entity or IT-system has a specific identity.
* **Trust** is: how much trust do we have in the entity that is authenticated as having a specific identity?
* **Authorization** is: what data may be accessed by the authenticated entity?

The conflation of these concepts is often caused by the implicit assumption that there is a common trust perimeter.

A perimeter based trust system assumes that all entities are vetted beforehand by a Trust Authority that guards the trust perimeter. Vetted and onboarded entities are regarded as trustworthy by other insiders (vetted and onboarded entities) within the trust perimeter. Authentication as being onboarded implies trust, followed by a check on authorization.

In a perimeter-less system there is no fixed perimeter with a binary status (onboarded of unknown): perimeters are custom made by each entity or group of entities. Trust is in principle assessed by each data owner for each entity that desires to exchange data. A data owner has trust sovereignty. In practice the drive for efficiency will lead to groups that create their own trust perimeter: however that perimeter does not hinder them in data exchanges with outsiders.

In this case, authentication is the first of two steps: Do we accept the identity claim?

The second step is situational: What level of trust do we bestow upon this identity, within this specific context, role and moment in time? This decision is often based on experience and reputation.

Trust in perimeter-less system requires more overhead. Perimeter-less systems scale better in large international and diverse environments, where trust is contextual and situational.

Supply chains are a good example of such an environment.

## 6. Implications of perimeter-less trust

The requirements of the BDI framework lead to a design which is based on perimeter-less trust.

There is no common trust perimeter, trust is fluid and sovereign, reputation and context based. Interoperability is desirable but a business decision, not an enforceable requirement.

The implications can be seen in the (lack of) particular measures compared to common Data Space frameworks.

* There is no overarching Data Space Authority that enforces certification of interfaces or an onboarding process, or adherence to data licenses

The BDI framework is in this sense more like other standards (like Oauth): adherence and compliance is voluntarily, because it makes business sense.

There may be local initiatives to enforce certification or specific adherences, data licenses or other specifics.

* There is no shared register of all onboarded parties

Registers are local, or even individual: a platform or company may start with it own register of trusted parties. If the need for interoperability grows, there are methods to create a common register for a group, in a BDI Association

The BDI framework defines a federated mechanism for previously unknown entities to identify themselves to another (data-owning) party, allowing this data-owner to verify the claims (preferably via the other BDI Association) and decide if there is enough trust to continue.

On the protocol level the consequence is for instance that the preferred Oauth flow is: authentication first, establish trust and proceed with authorization if (and only if) there is enough trust.

Discovery of endpoints is assumed to be a generic mechanism, for instance via DNS.

* There are undefined or un-verifiable levels of quality of IDP’s

The reality of doing business globally is that there may be a variety of means to identify an entity, person of system. Dealing with SME’s in less IT-mature environments requires simple methods, albeit with lower trust.

* Interoperability of authorization registers is a target on the horizon

In practice proprietary local implementations can be sufficient to start with., and part of a growth path. Platforms for instance may decide to start with a proprietary local authorization register, on behalf of a multitude of parties. Over time platforms and parties may find interoperability of such value that they adopt the next level.

In general one can say that subsidiarity, global differentiation and local/sectoral adaptations are seen as more important than enforcing interoperability: natural business drivers will lead to more or less interoperability between groups.

## 7. BDI Stack and kits

The BDI Stack defines the building blocks and components that form a coherent framework.

<figure><img src="../.gitbook/assets/BDI building blocks.png" alt=""><figcaption><p>Overview of BDI building blocks</p></figcaption></figure>

Implementation of the principles by means of parts of the stack is aided by the definition of “Kits”.

A Kit is a subset of the stack that forms a coherent capability. Implementing a Kit makes it easier to add capabilities later and expand the capabilities.