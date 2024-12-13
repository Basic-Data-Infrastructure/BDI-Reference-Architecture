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

# Authorization

### Summary

### Purpose of the building block

{% hint style="info" %}
This building block describes how to assess trustworthiness of parties involved in a transaction.
{% endhint %}

### Concepts

#### Authentication, Trust and Authorization

The concepts Authentication, Trust and Authorization are closely related but not identical. To describe their relations, we assume that a party A wants to gain access to data owned by party B. During authentication, party A provides its identification and evidence of that identification. Such evidence could be passwords, two-factor id's, PKI-based certificates, or bio-metric data such as iris scans and finger prints. Party B evaluates the evidence and assigns a trust level to A. Based on this trust level, B assigns  permissions to certain parts of the data. It will be clear that higher trust levels result in more permissions.

To assign a trust level, party B gathers data about party A. This data includes, but is not limited to, nature of the evidence (PKI certificates are trusted more than simple passwords). It can also include a reputation score built by A during previous interactions.

The following concepts (from the BDI Glossary) are particularly relevant in this building block:

<table><thead><tr><th width="207">Concept</th><th>Meaning</th></tr></thead><tbody><tr><td>Authorization</td><td>Authorization ensures that the authenticated entity, person or Process has been granted permission to gain access to the specific (data) resource requested.</td></tr><tr><td>Trust</td><td>Trust is the design and implementation of measures that evaluate the chain of trust per presented credential by any party; the decision to accept a certain level of trust is dependent on the risk of making a mistake.</td></tr><tr><td>Data Owner</td><td><ul><li>Has control over data and access to data,</li><li>Controls decisions on Data Sovereignty and Trust Sovereignty</li><li>Controls authorisation policies, representation rules, professional qualification verification of staff and contractors</li><li>Controls subscription to the Event Pub/Sub Service, and publishing of events to subscribers</li><li>Controls discovery and endpoints</li><li>Controls roles assumed by entity</li></ul></td></tr><tr><td>Data Consumer</td><td><ul><li>Requests access to data and/or Representation Register and/or Professional Qualification Register of the Data Owner</li><li>Controls discovery and endpoints</li><li>Requests subscription to Event Pub/Sub Service of the Data Owner, receives and evaluates events</li></ul></td></tr><tr><td>Data Service Provider</td><td>A Service Provider that acts under supervision and on behalf of the Data Owner</td></tr></tbody></table>

### Risks

Insufficient authorization may cause data leaks to parties that are not trusted.

### Inter-linkages with other building blocks

This building block has links to:

* [Representation Chain](../federation-kit/representation-register.md)
* [Association Register](association-register.md)
* [Data Licenses](../data-set-kit/data-licenses.md)
* [Authentication M2M](authentication.md)

The Authorization building block uses information from these related building blocks to make a decision whether or not to trust a partner in a transaction.

### Elements and their key functions

While entering into a transaction, each participant involved in the transaction will decide if it trusts the other party.

<figure><img src="../../.gitbook/assets/Trust assessment when entering into a transaction.png" alt="" width="518"><figcaption><p>Example of trust assessment where party A wants to enter a transaction with party B</p></figcaption></figure>

To make a decision on trust, the party will use relevant and available information. The BDI provides a framework for four input elements for this decision:

1. [Trust based on the membership of an Association](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-1.-trust-based-on-association-membership), one of it’s parent Associations or the root BDI Network.
2. [Trust based on the level of assurance](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-2.-trust-based-on-the-level-of-assurance-of-the-digital-identity-of-the-party) of the digital identity of the party.
3. [Trust based on the reputation of the Member](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-2.-trust-based-on-reputations) as provided by the Reputation Model.
4. [Trust based on (granular) Authorizations](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-3.-trust-based-on-authorisations) provided by a Data Owner.

### Core design decisions

The four inputs for decision making are supported by the BDI trust input elements as follows.

### 1. Trust based on association membership

#### Information gathering

This input element uses input from the building block [Authentication M2M](authentication.md). This building block provides insight into what association and (optionally) what parent associations a participant is a member of.

#### Information processing

To facilitate easier processing of the acquired information, a party can:

* Choose to follow Association business logic, in this case the Association has defined how to translate Association membership into trust levels.
* (If allowed by the Association) choose to follow it's own logic.

### 2. Trust based on the level of assurance of the digital identity of the party

#### Information gathering

This input element uses input from the/ building block [Authentication M2M](authentication.md). This building block provides insight into the level of assurance of the party.

#### Information processing

To facilitate easier processing of the acquired information, a party can:

* Choose to follow Association business logic, in this case the Association has defined how to translate Association membership into trust levels.
* (If allowed by the Association) choose to follow it's own logic.

### 3. Trust based on reputations

#### Information gathering

The [Business Partner Reputation Model](../federation-kit/business-partner-reputation-model.md) forms the basis for acquiring reputation information. It is not yet defined how information on reputation of a party can be acquired.

#### Information processing

Assuming that information on the reputation of a party is available, a party can:

* Choose to follow Association business logic.
* (If allowed by the Association) choose to follow it's own logic.

### 4. Trust based on (granular) authorizations

Authorizations provide a way for a Data Owner to specify in great detail which Data Consumer is allowed to consume data on its behalf at a Data Service Provider. From a data sovereignty perspective, Authorizations provide the highest level of 'trust' and best basis to enter into a transaction up, when transactions are happening between Service Consumers and Data Service Providers.

#### Information gathering

In terms of the technical specifications for Authorizations, the BDI Framework is inspired  on the iSHARE Trust Framework. The iSHARE Trust Framework uses the term “delegations” for the concept that in BDI is called Authorizations.

* The framework defines [the role of an Authorization Registry](https://framework.ishare.eu/is/framework-and-roles)
* Entitled Parties are enabled in exercising data sovereignty by providing delegations (as described in the [generic use cases](https://framework.ishare.eu/is/use-cases)) to parties to use their data
* [Licenses](https://framework.ishare.eu/is/licenses) specify the legal boundaries for the usage of data by a Data Consumer
* The [structure of delegation](https://framework.ishare.eu/is/structure-of-delegation-evidence) evidence is defined in the framework and the technical requirements for APIs providing delegation evidence on the [iSHARE Developer Portal](https://dev.ishare.eu/).

Functionally authorizations can:

* Be provided by the Data Consumer when requesting to consume a service at a Data Service Provider.
* Be requested by the Data Service Provider when a Data Consumer requests to consumer a service.

BDI does not define in what way an Authorization Registry needs to store policies regarding delegations.

### Trust in case of a Data Service Provider acting on behalf of a Data Owner

A specific situation occurs when a Data Service Provider acts on behalf of a Data Owner. The Data Service Provider is assumed to have a business relationship with a Data Owner in which the rules for sharing data on behalf of the Data Owner are established. Beside the input elements that can be provided using the BDI Framework, a Data Service Provider and Data Owner can agree on other inputs used to make a trust decision.

{% hint style="info" %}
**Example of a Data Service Provider**

Consider the situation where a Data Service Provider is being requested for data by a Data Consumer. The Data Service Provider could use the following information in its decision to trust the Data Consumer:

* Is the Data Consumer member of my Association, a parent Association or the root BDI Network? \[BDI input element 1]
* What is the reputation of the Data Consumer? \[BDI input element 3]
* Can the Data Consumer provide Authorizations given to him by a Data Owner? \[BDI input element 4]
* Is the Data Consumer a legal entity based in the EU? \[specific criterion, which can optionally be encapsulated in the (granular) Authorization \[BDI input element 4] as a condition

Based on both this information and the nature of the data that the Data Service Provider is requested for (for instance the confidentiality or privacy aspects), the Data Service Provider can make a business decision to provide or not provide the data.
{% endhint %}

### Data Service Providers and Authorizations

Data Service Providers processes data on behalf of Data Owners. Data Owners should make a careful choice which Data Service Providers they use as they have to consent on the Terms & Conditions of the Data Service Provider. These could consists of generic Terms & Conditions of the Data Service Provider and additional Terms & Conditions for the specific data.

Data Service Providers should cater for adequate authorization capabilities to control which organisations / users have access to which data. These authorizations can be registered in an Authorization Register of the Data Service Provider.

### Data Sharing Triggers

The sharing of data between organisations can be triggered by:

* Process steps which leads to the sharing of data. The data sharing is a side effect of the process flow. For example: a Transport Company receives a transport order from a Customer. Therefore the Transport Company needs access to the transport order data. The authorization for data sharing is an implicit result of the involvement in the business process.
* Providing explicit permission to share the data with another organisations. For example: the permission of a Terminal to share all container shipment related data with CBS.

### Patterns for authorization evidence

Data Service Providers could use external information in an external Authorization Register (AR) under the control of the Data Owner to provide access. This external information can be retrieved using different patterns including:

* The permissions are synced between the AR and the Data Service Provider. The Data Service Provider holds alocal copy which is used to provide access. Synchronization can be done by frequent polling or event updates.
* The (signed/sealed) permission is included in the data request from the Data Consumer. The Data Consumer has retrieved this permission from the Data Owner. Signing/Sealing is required to verify that the permission has been given by the Data Owner.
* The Data Service Provider polls the external Authorisation Register at runtime during a data request to check the permission. In more complicated scenario’s Authorisation Registers could refer to other Authorisation Registers validating the chain of permission to it’s source.

### Advantages and drawbacks

&#x20;

|                       | Advantage                                                                                                                           | Drawback                                                                                                                                                        |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Synchronization       | <p>No performance loss at data request.</p><p>No additional delay for polling data.</p><p> </p>                                     | Setup of synchronization process (polling or event processing)                                                                                                  |
| Embed in Data Request | <p>No performance loss at data request.</p><p>No additional delay for polling data.</p><p>No setup of synchronization required.</p> | <p>Data Consumer must retrieve authorization evidence.</p><p>Authorizations needs to be signed / sealed so it can be verified by the Data Service Provider.</p> |
| Polling at Request    | Most up to date information is always used.                                                                                         | Data Service Provider is dependent on (a) the performance (b) the additional delay (c) the availability of the external Authorization Register.                 |

### Guidance for trust decision making

It could be helpful to create a trust decision matrix, to improve manageability of decision rules. The approach would be:

1. To classify data with a required assurance level (for instance low, medium, high).
2. To assign required trust levels to an assurance level.

This could be done at a party's level or at an Association's level.

{% hint style="info" %}
**Example of data classification**

Location of a container -> low

Contents of a container -> medium

Personal data of shipper -> high
{% endhint %}

Example of a trust decision matrix:

<table data-full-width="true"><thead><tr><th width="160">Classification</th><th width="223">Association trust required</th><th width="223">Reputation trust required</th><th>Granular authorisation required</th></tr></thead><tbody><tr><td>Low</td><td>Medium</td><td>No</td><td>No</td></tr><tr><td>Medium</td><td>Medium</td><td>Medium</td><td>No</td></tr><tr><td>High</td><td>High</td><td>High</td><td>Yes</td></tr></tbody></table>

Business rules could also consist of a combination of the various trust aspects. For instance that either medium association trust OR medium reputation trust is required.

### Future topics

* For improved discoverability of the parents of a BDI Association, the BDI Association Register could be improved by returning this information for every party lookup directly as part of the party information.
* To improve interoperability between associations, BDI might consider to define standardized rules for service/data classification and a best-practice approach for trust processing.

### Case Study

{% file src="../../.gitbook/assets/20241001_DIL_BDI_Case Study Portbase on Data Service Providers and Authorisations.pdf" %}

### Further reading

This building block has been drafted using the following sources, that provide opportunity for further reading:

* [DSSC Blueprint building block “Participation Management”](https://dssc.eu/space/BVE/357074624/Participation+Management)
* [iSHARE Framework documentation](https://framework.ishare.eu)
* [iSHARE Developer Portal documentation](https://dev.ishare.eu)
* [iSHARE Dataspace Template, section Access & usage policies and enforcement](https://template.ishare.eu/data-sovereignty-and-trust/access-and-usage-policies-and-enforcement)
