---
cover: >-
  https://images.unsplash.com/photo-1715371659354-f72c4458d9a1?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxMHx8YXV0aG9yaXplZHxlbnwwfHx8fDE3NjQ3NzMxMDl8MA&ixlib=rb-4.1.0&q=85
coverY: 0
---

# Authorization

## 1. Purpose of the building block

This building block describes how to assess trustworthiness of parties involved in a transaction.

## 2. Concepts

### 2.1 Authentication, Trust and Authorization

The concepts Authentication, Trust and Authorization are closely related but not identical. To describe their relations, we assume that a party A wants to gain access to data owned by party B. During authentication, party A provides its identification and evidence of that identification. Such evidence could be passwords, two-factor id's, PKI-based certificates, or bio-metric data such as iris scans and finger prints. Party B evaluates the evidence and assigns a trust level to A. Based on this trust level, B assigns permissions to certain parts of the data. It will be clear that higher trust levels result in more permissions.

To assign a trust level, party B gathers data about party A. This data includes, but is not limited to, nature of the evidence (PKI certificates are trusted more than simple passwords). It can also include a reputation score built by A during previous interactions.

The following concepts (from the BDI Glossary) are particularly relevant in this building block:

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Authorization</strong></td><td>Authorization ensures that the authenticated entity, person or Process has been granted permission to gain access to the specific (data) resource requested.</td><td><a href="https://images.unsplash.com/photo-1636705927771-09134b0a1b1f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxhdXRob3Jpc2F0aW9ufGVufDB8fHx8MTc2NDc3NzIyNXww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1636705927771-09134b0a1b1f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxhdXRob3Jpc2F0aW9ufGVufDB8fHx8MTc2NDc3NzIyNXww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Trust</strong></td><td>Trust is the design and implementation of measures that evaluate the chain of trust per presented credential by any party; the decision to accept a certain level of trust is dependent on the risk of making a mistake.</td><td><a href="https://images.unsplash.com/photo-1521791136064-7986c2920216?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHx0cnVzdHxlbnwwfHx8fDE3NjQ3NzcyNjl8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1521791136064-7986c2920216?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHx0cnVzdHxlbnwwfHx8fDE3NjQ3NzcyNjl8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Data owner</strong></td><td><ul><li>Has control over data and access to data,</li><li>Controls decisions on Data Sovereignty and Trust Sovereignty</li><li>Controls authorization policies, representation rules, professional qualification verification of staff and contractors</li><li>Controls subscription to the Event Pub/Sub Service, and publishing of events to subscribers</li><li>Controls discovery and endpoints</li><li>Controls roles assumed by entity</li></ul></td><td><a href="https://images.unsplash.com/photo-1758876204763-5b346b174d0e?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxkYXRhJTIwb3duZXJ8ZW58MHx8fHwxNzY0Nzc3MzE2fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1758876204763-5b346b174d0e?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxkYXRhJTIwb3duZXJ8ZW58MHx8fHwxNzY0Nzc3MzE2fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Data Consumer</strong></td><td><ul><li>Requests access to data and/or Representation Register and/or Professional Qualification Register of the Data Owner</li><li>Controls discovery and endpoints</li><li>Requests subscription to Event Pub/Sub Service of the Data Owner, receives and evaluates events</li></ul></td><td><a href="https://images.unsplash.com/photo-1611095973763-414019e72400?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxwZXJzb24lMjB3aXRoJTIwbGFwdG9wfGVufDB8fHx8MTc2NDc3NzM0Nnww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1611095973763-414019e72400?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxwZXJzb24lMjB3aXRoJTIwbGFwdG9wfGVufDB8fHx8MTc2NDc3NzM0Nnww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Data Service Provider</strong></td><td>A Service Provider that acts under supervision and on behalf of the Data Owner</td><td><a href="https://images.unsplash.com/photo-1744868562210-fffb7fa882d9?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxkYXRhJTIwc2VydmljZSUyMHByb3ZpZGVyfGVufDB8fHx8MTc2NDc3NzM5NHww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1744868562210-fffb7fa882d9?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxkYXRhJTIwc2VydmljZSUyMHByb3ZpZGVyfGVufDB8fHx8MTc2NDc3NzM5NHww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

## 3. Risks

Insufficient authorization may cause data leaks to parties that are not trusted.

## 4. Interlinkages with other building blocks

This building block has links to:

<a href="../federation-kit/representation-register.md" class="button secondary">Representation Chain</a> <a href="../../readme/trust-kit/association-register-1.md" class="button secondary">Association Register</a> <a href="../data-set-kit/data-licenses.md" class="button secondary">Data Licenses</a> <a href="authentication.md" class="button secondary">Authentication M2M</a>

The Authorization building block uses information from these related building blocks to make a decision whether or not to trust a partner in a transaction.

## 5. Elements and their key functions

While entering into a transaction, each participant involved in the transaction will decide if it trusts the other party.

<figure><img src="../../.gitbook/assets/Untitled Diagram.drawio (6).png" alt="" width="563"><figcaption></figcaption></figure>

To make a decision on trust, the party will use relevant and available information. The BDI provides a framework for four input elements for this decision:

1. [Trust based on the membership of an Association](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-1.-trust-based-on-association-membership), one of it’s parent Associations or the root BDI Network.
2. [Trust based on the level of assurance](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-2.-trust-based-on-the-level-of-assurance-of-the-digital-identity-of-the-party) of the digital identity of the party.
3. [Trust based on the reputation of the Member](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-2.-trust-based-on-reputations) as provided by the Reputation Model.
4. [Trust based on (granular) Authorizations](authorisation-oauth-2.0-ar-dm-+-xacml-policies.md#id-3.-trust-based-on-authorisations) provided by a Data Owner.

## 6. Core design decisions

The four inputs for decision making are supported by the BDI trust input elements as follows.

{% stepper %}
{% step %}
**Trust based on association membership**

**Information gathering**

This input element uses input from the building block [Authentication M2M](authentication.md). This building block provides insight into what association and (optionally) what parent associations a participant is a member of.

**Information processing**

To facilitate easier processing of the acquired information, a party can:

* Choose to follow Association business logic, in this case the Association has defined how to translate Association membership into trust levels.
* (If allowed by the Association) choose to follow it's own logic.
{% endstep %}

{% step %}
**Trust based on the level of assurance of the digital identity of the party**

**Information gathering**

This input element uses input from the/ building block [Authentication M2M](authentication.md). This building block provides insight into the level of assurance of the party.

**Information processing**

To facilitate easier processing of the acquired information, a party can:

* Choose to follow Association business logic, in this case the Association has defined how to translate Association membership into trust levels.
* (If allowed by the Association) choose to follow it's own logic.
{% endstep %}

{% step %}
**Trust based on reputations**

**Information gathering**

The [Business Partner Reputation Model](../federation-kit/business-partner-reputation-model.md) forms the basis for acquiring reputation information. It is not yet defined how information on reputation of a party can be acquired.

**Information processing**

Assuming that information on the reputation of a party is available, a party can:

* Choose to follow Association business logic.
* (If allowed by the Association) choose to follow it's own logic.
{% endstep %}

{% step %}
**Trust based on (granular) authorizations**

Authorizations provide a way for a Data Owner to specify in great detail which Data Consumer is allowed to consume data on its behalf at a Data Service Provider. From a data sovereignty perspective, Authorizations provide the highest level of 'trust' and best basis to enter into a transaction up, when transactions are happening between Service Consumers and Data Service Providers.

**Information gathering**

In terms of the technical specifications for Authorizations, the BDI Framework is inspired on the iSHARE Trust Framework. The iSHARE Trust Framework uses the term “delegations” for the concept that in BDI is called Authorizations.

* The framework defines [the role of an Authorization Registry](https://framework.ishare.eu/is/framework-and-roles)
* Entitled Parties are enabled in exercising data sovereignty by providing delegations (as described in the [generic use cases](https://framework.ishare.eu/is/use-cases)) to parties to use their data
* [Licenses](https://framework.ishare.eu/is/licenses) specify the legal boundaries for the usage of data by a Data Consumer
* The [structure of delegation](https://framework.ishare.eu/is/structure-of-delegation-evidence) evidence is defined in the framework and the technical requirements for APIs providing delegation evidence on the [iSHARE Developer Portal](https://dev.ishare.eu/).

Functionally authorizations can:

* Be provided by the Data Consumer when requesting to consume a service at a Data Service Provider.
* Be requested by the Data Service Provider when a Data Consumer requests to consumer a service.

BDI does not define in what way an Authorization Registry needs to store policies regarding delegations.
{% endstep %}
{% endstepper %}

### 6.1 Trust in case of a Data Service Provider acting on behalf of a Data Owner

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

## 7. Data Service Providers and Authorizations

Data Service Providers processes data on behalf of Data Owners. Data Owners should make a careful choice which Data Service Providers they use as they have to consent on the Terms & Conditions of the Data Service Provider. These could consists of generic Terms & Conditions of the Data Service Provider and additional Terms & Conditions for the specific data.

Data Service Providers should cater for adequate authorization capabilities to control which organizations / users have access to which data. These authorizations can be registered in an Authorization Register of the Data Service Provider.

## 8. Data Sharing Triggers

The sharing of data between organizations can be triggered by:

* Process steps which leads to the sharing of data. The data sharing is a side effect of the process flow. For example: a Transport Company receives a transport order from a Customer. Therefore the Transport Company needs access to the transport order data. The authorization for data sharing is an implicit result of the involvement in the business process.
* Providing explicit permission to share the data with another organizations. For example: the permission of a Terminal to share all container shipment related data with CBS.

## 9. Patterns for authorization evidence

Data Service Providers could use external information in an external Authorization Register (AR) under the control of the Data Owner to provide access. This external information can be retrieved using different patterns including:

* The permissions are synced between the AR and the Data Service Provider. The Data Service Provider holds a local copy which is used to provide access. Synchronization can be done by frequent polling or event updates.
* The (signed/sealed) permission is included in the data request from the Data Consumer. The Data Consumer has retrieved this permission from the Data Owner. Signing/Sealing is required to verify that the permission has been given by the Data Owner.
* The Data Service Provider polls the external Authorization Register at runtime during a data request to check the permission. In more complicated scenario’s Authorization Registers could refer to other Authorization Registers validating the chain of permission to it’s source.

## 10. Advantages and drawbacks

|                           | Advantage                                                                                                                           | Drawback                                                                                                                                                        |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Synchronization**       | <p>No performance loss at data request.</p><p>No additional delay for polling data.</p>                                             | Setup of synchronization process (polling or event processing)                                                                                                  |
| **Embed in Data Request** | <p>No performance loss at data request.</p><p>No additional delay for polling data.</p><p>No setup of synchronization required.</p> | <p>Data Consumer must retrieve authorization evidence.</p><p>Authorizations needs to be signed / sealed so it can be verified by the Data Service Provider.</p> |
| **Polling at Request**    | Most up to date information is always used.                                                                                         | Data Service Provider is dependent on (a) the performance (b) the additional delay (c) the availability of the external Authorization Register.                 |

## 11. Guidance for trust decision making

It could be helpful to create a trust decision matrix, to improve manageability of decision rules. The approach would be:

1. classify data with a required assurance level (for instance low, medium, high),
2. assign required trust levels to an assurance level.

This could be done at a party's level or at an Association's level.

{% hint style="info" %}
**Example of data classification**

Location of a container -> low

Contents of a container -> medium

Personal data of shipper -> high
{% endhint %}

Example of a trust decision matrix:

<table data-full-width="false"><thead><tr><th width="152.727294921875">Classification</th><th width="206.6363525390625">Association trust required</th><th width="199.3636474609375">Reputation trust required</th><th width="227.6363525390625">Granular authorisation required</th></tr></thead><tbody><tr><td>Low</td><td>Medium</td><td>No</td><td>No</td></tr><tr><td>Medium</td><td>Medium</td><td>Medium</td><td>No</td></tr><tr><td>High</td><td>High</td><td>High</td><td>Yes</td></tr></tbody></table>

Business rules could also consist of a combination of the various trust aspects. For instance that either medium association trust OR medium reputation trust is required.

## 12. Future topics & Case study

**Future topics**

* For improved discoverability of the parents of a BDI Association, the BDI Association Register could be improved by returning this information for every party lookup directly as part of the party information.
* To improve interoperability between associations, BDI might consider to define standardized rules for service/data classification and a best-practice approach for trust processing.

**Case Study**

{% file src="../../.gitbook/assets/20241001_DIL_BDI_Case Study Portbase on Data Service Providers and Authorisations.pdf" %}

## 13. Further reading

This building block has been drafted using the following sources, that provide opportunity for further reading:

* [DSSC Blueprint building block “Participation Management”](https://dssc.eu/space/BVE/357074624/Participation+Management)
* [iSHARE Framework documentation](https://framework.ishare.eu)
* [iSHARE Developer Portal documentation](https://dev.ishare.eu)
* [iSHARE Dataspace Template, section Access & usage policies and enforcement](https://template.ishare.eu/data-sovereignty-and-trust/access-and-usage-policies-and-enforcement)
