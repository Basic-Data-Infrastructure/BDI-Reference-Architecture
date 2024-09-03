# Data Licenses

Data licenses describe the terms and conditions for using data. BDI recognises a layered licensing structure. Licenses are used in authorisations for data transactions and are defined in this building block of the BDI framework.

## Purpose of the building block

The purpose of the data licenses building block is to allow Data Owners to control what Data Consumers are allowed to do with their data by providing instructions on how a service may be consumed or under which conditions data may be exchanged.

## Concepts

The following concepts (from the BDI Glossary) are particularly relevant in this building block:

<table><thead><tr><th width="262">Concept</th><th>Meaning</th></tr></thead><tbody><tr><td>Data licenses</td><td><ul><li>Descriptions of the terms and conditions for using data</li><li>Either in free form text or in ODRL</li></ul></td></tr><tr><td>Data Owner</td><td><ul><li>Has control over data and access to data,</li><li>Controls decisions on Data Sovereignty and Trust Sovereignty</li><li>Controls authorisation policies, representation rules, professional qualification verification of staff and contractors</li><li>Controls subscription to the Event Pub/Sub Service and publishing of events to subscribers</li><li>Controls discovery and endpoints</li><li>Controls roles assumed by entity</li></ul></td></tr><tr><td>Data Consumer</td><td><ul><li>Requests access to data and/or Representation Register and/or Professional Qualification Register of the data owner</li><li>Controls discovery and endpoints</li><li>Requests subscription to data owner’s Event Pub/Sub Service, receives and evaluates events</li></ul></td></tr></tbody></table>

## Risks

When not selecting the correct license, the Data Consumer might not be sufficiently legally bound to the right terms and conditions for using their data, which could result in data abuse and thereby in financial or reputational damage to the Data Owner, or (indirectly) the Data Service Provider.

However well the licenses are implemented, there is no technical guarantee that the data is used in conformance with the applicable licenses. The legal context of the framework mitigates this risk, but a residual risk remains.

{% hint style="info" %}
BDI encourages participants (particularly Data Consumers) to implement proper data management and or data governance to ensure proper handling of data.
{% endhint %}

## Interlinkages with other building blocks

This building block is closely tied to [authorisation-oauth-2.0-ar-dm-+-xacml-policies.md](../trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies.md "mention"), since a license may be part of an authorisation. The authorisation defines:

1. Which party
2. Is allowed to access which data attributes
3. (Optionally) at which Data Service Provider
4. (Optionally) with which terms and conditions for using the data (**licenses**)

## Elements and their key functions

Licenses are defined in framework documentation (see below). In Authorisations, licenses are applied. As defined in [authorisation-oauth-2.0-ar-dm-+-xacml-policies.md](../trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies.md "mention"), and particularly in the [iSHARE data model for authorisations](https://dev.ishare.eu/reference/delegation-mask/policy-sets), one or more licenses ("stacking") can be applied to an Authorisation. Data Owners must make sure that when more then one license is used, the licenses must not be contradictory.

{% hint style="success" %}
**Example of acceptable stacking of licenses**

* 0004 Licensee may enrich received data with own data before re-sharing
* XXXX Licensee may use received data in the region Europe
{% endhint %}

## Core design decisions

Licenses are defined on three layers:

1. iSHARE layer. The available licenses are [defined in the iSHARE Trust Framework](https://framework.ishare.eu/detailed-descriptions/functional/licenses).
2. BDI layer. The available licenses are defined [in this building block](data-licenses.md#bdi-layer-licenses).
3. Association layer. The available licenses are defined in the framework agreements of a BDI Association (when these exist).

### BDI layer licenses

There are currently no specific BDI licenses defined.

### Combined list of available licenses

<table data-view="cards"><thead><tr><th></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td><p>0000</p><p>No limitations</p></td><td></td><td></td></tr><tr><td><p>0001</p><p>Re-sharing with Adhering Parties only</p></td><td></td><td></td></tr><tr><td><p>0002</p><p>Internal use only</p></td><td></td><td></td></tr><tr><td><p>0003</p><p>Non-commercial use only: licensee may not use the data to generate revenue</p></td><td></td><td></td></tr><tr><td><p>0004</p><p>Licensee may enrich received data with own data before re-sharing</p></td><td></td><td></td></tr><tr><td><p>0005</p><p>Licensee may enrich received data with data of others before re-sharing</p></td><td></td><td></td></tr><tr><td><p>0006</p><p>Licensee may enrich received data with own data before re-sharing on a non-commercial basis</p></td><td></td><td></td></tr><tr><td><p>0007</p><p>Licensee may enrich received data with data of others before re-sharing on a non-commercial basis</p></td><td></td><td></td></tr><tr><td><p>9999</p><p>As determined between Parties</p></td><td></td><td></td></tr></tbody></table>

## Future topics

Future topics that are of interest to this building block are:

* Research how Incoterms can be applied in the context of licenses.
* Research which technical controls are available to enforce adherence to licenses.
* Align with other data spaces initiatives on the topic of policy enforcement.
* Contribute to iSHARE's licenses framework through the [iSHARE's Change Management process](https://changes.ishare.eu), particularly through [RFC037](https://gitlab.com/ishare-foundation/cab/rfc/-/issues/7) (including improved specification on the usage of ODRL).

## Further reading

This building block has been drafted using the following sources, that provide opportunity for further reading:

* [DSSC Blueprint building block “Access and usage policies enforcement”](https://dssc.eu/space/BVE/357075567/Access+%26+Usage+Policies+Enforcement)
* [iSHARE Framework documentation](https://framework.ishare.eu/), specifically on the topic of [licenses](https://framework.ishare.eu/is/licenses)
* [iSHARE Developer Portal documentation](https://dev.ishare.eu/)
