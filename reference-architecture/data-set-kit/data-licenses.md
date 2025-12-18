---
cover: >-
  https://images.unsplash.com/photo-1460925895917-afdab827c52f?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxkYXRhfGVufDB8fHx8MTc2NTgxMjY1MHww&ixlib=rb-4.1.0&q=85
coverY: 0
---

# Data Licenses

Data licenses describe the terms and conditions for using data. BDI recognizes a layered licensing structure. Licenses are used in authorizations for data transactions and are defined in this building block of the BDI framework.

## 1. Purpose of the building block

The purpose of the data licenses building block is to allow Data Owners to control what Data Consumers are allowed to do with their data by providing instructions on how a service may be consumed or under which conditions data may be exchanged.

## 2. Concepts

The following concepts (from the BDI Glossary) are particularly relevant in this building block:

<table><thead><tr><th width="262">Concept</th><th>Meaning</th></tr></thead><tbody><tr><td><strong>Data licenses</strong></td><td><ul><li>Descriptions of the terms and conditions for using data</li><li>Either in free form text or in ODRL</li></ul></td></tr><tr><td><strong>Data Owner</strong></td><td><ul><li>Has control over data and access to data,</li><li>Controls decisions on Data Sovereignty and Trust Sovereignty</li><li>Controls authorisation policies, representation rules, professional qualification verification of staff and contractors</li><li>Controls subscription to the Event Pub/Sub Service and publishing of events to subscribers</li><li>Controls discovery and endpoints</li><li>Controls roles assumed by entity</li></ul></td></tr><tr><td><strong>Data Consumer</strong></td><td><ul><li>Requests access to data and/or Representation Register and/or Professional Qualification Register of the data owner</li><li>Controls discovery and endpoints</li><li>Requests subscription to data owner’s Event Pub/Sub Service, receives and evaluates events</li></ul></td></tr></tbody></table>

## 3. Risks

When not selecting the correct license, the Data Consumer might not be sufficiently legally bound to the right terms and conditions for using their data, which could result in data abuse and thereby in financial or reputational damage to the Data Owner, or (indirectly) the Data Service Provider.

However well the licenses are implemented, there is no technical guarantee that the data is used in conformance with the applicable licenses. The legal context of the framework mitigates this risk, but a residual risk remains.

{% hint style="info" %}
BDI encourages participants (particularly Data Consumers) to implement proper data management and or data governance to ensure proper handling of data.
{% endhint %}

## 4. Interlinkages with other building blocks

This building block is closely tied to [authorisation-oauth-2.0-ar-dm-+-xacml-policies.md](../trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies.md "mention"), since a license may be part of an authorization. The authorization defines:

1. Which party
2. Is allowed to access which data attributes
3. (Optionally) at which Data Service Provider
4. (Optionally) with which terms and conditions for using the data (**licenses**)

## 5. Elements and their key functions

Licenses are defined in framework documentation (see below). In Authorizations, licenses are applied. As defined in [authorisation-oauth-2.0-ar-dm-+-xacml-policies.md](../trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies.md "mention"), and particularly in the [iSHARE data model for authorisations](https://dev.ishare.eu/reference/delegation-mask/policy-sets), one or more licenses ("stacking") can be applied to an Authorization. Data Owners must make sure that when more then one license is used, the licenses must not be contradictory.

{% hint style="success" %}
**Example of acceptable stacking of licenses**

* 0004 Licensee may enrich received data with own data before re-sharing
* XXXX Licensee may use received data in the region Europe
{% endhint %}

## 6. Core design decisions

Licenses are defined on three layers:

1. iSHARE layer. The available licenses are [defined in the iSHARE Trust Framework](https://framework.ishare.eu/detailed-descriptions/functional/licenses).
2. BDI layer. The available licenses are defined [in this building block](data-licenses.md#bdi-layer-licenses).
3. Association layer. The available licenses are defined in the framework agreements of a BDI Association (when these exist).

### 6.1 BDI layer licenses

There are currently no specific BDI licenses defined.

### 6.2 Combined list of available licenses

{% stepper %}
{% step %}
#### 0000

No limitations
{% endstep %}

{% step %}
#### 0001

Re-sharing with Adhering Parties only
{% endstep %}

{% step %}
#### 0002

Internal use only
{% endstep %}

{% step %}
#### 0003

Non-commercial use only: licensee may not use the data to generate revenue
{% endstep %}

{% step %}
#### 0004

Licensee may enrich received data with own data before re-sharing
{% endstep %}

{% step %}
#### 0005

Licensee may enrich received data with data of others before re-sharing
{% endstep %}

{% step %}
#### 0006

Licensee may enrich received data with own data before re-sharing on a non-commercial basis
{% endstep %}

{% step %}
#### 0007

Licensee may enrich received data with data of others before re-sharing on a non-commercial basis
{% endstep %}

{% step %}
#### 9999

As determined between Parties
{% endstep %}
{% endstepper %}

## 7. Future topics

Future topics that are of interest to this building block are:

* Research how Incoterms can be applied in the context of licenses.
* Research which technical controls are available to enforce adherence to licenses.
* Align with other data spaces initiatives on the topic of policy enforcement.
* Contribute to iSHARE's licenses framework through the [iSHARE's Change Management process](https://changes.ishare.eu), particularly through [RFC037](https://gitlab.com/ishare-foundation/cab/rfc/-/issues/7) (including improved specification on the usage of ODRL).

## 8. Further reading

This building block has been drafted using the following sources, that provide opportunity for further reading:

* [DSSC Blueprint building block “Access and usage policies enforcement”](https://dssc.eu/space/BVE/357075567/Access+%26+Usage+Policies+Enforcement)
* [iSHARE Framework documentation](https://framework.ishare.eu/), specifically on the topic of [licenses](https://framework.ishare.eu/is/licenses)
* [iSHARE Developer Portal documentation](https://dev.ishare.eu/)
