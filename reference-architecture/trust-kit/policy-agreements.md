# Policy agreements

## Summary

## Purpose of the building block

## Concepts

The following concepts (from the BDI Glossary) are particularly relevant in this building block:

<table><thead><tr><th width="262">Concept</th><th>Meaning</th></tr></thead><tbody><tr><td>Authorization Register</td><td><ul><li>Holds authorization policies for one or more data owners on access to data</li><li>Also known as AR-DM, Authorization Register Data Management</li></ul></td></tr><tr><td>Data Owner</td><td><ul><li>Has control over data and access to data,</li><li>Controls decisions on Data Sovereignty and Trust Sovereignty</li><li>Controls authorisation policies, representation rules, professional qualification verification of staff and contractors</li><li>Controls subscription to the Event Pub/Sub Service and publishing of events to subscribers</li><li>Controls discovery and endpoints</li><li>Controls roles assumed by entity</li></ul></td></tr><tr><td>Data Consumer</td><td><ul><li>Requests access to data and/or Representation Register and/or Professional Qualification Register of the data owner</li><li>Controls discovery and endpoints</li><li>Requests subscription to data owner’s Event Pub/Sub Service, receives and evaluates events</li></ul></td></tr><tr><td>Data Service Provider</td><td><ul><li>A service provider that acts under the supervision and on behalf of the data owner</li></ul></td></tr></tbody></table>

## Risks

* Not providing enough guidance to parties on how to deal with authorisation policies, could lead to a decreased data sovereignty for Data Owners.
* By not specifying the authorisation framework, single point solutions (such as platforms) will independently cater to data sovereignty requirements. This will harm interoperability and create a dependency for Data Owners on those single point solutions.

## Interlinkages with other building blocks

This building block is closely tied to [authentication.md](authentication.md "mention"). An authorisation which defines:

1. Which party
2. Is allowed to access which data attributes
3. (Optionally) at which Data Service Provider
4. (Optionally) with which terms and conditions for using the data (licenses)

## Elements and their key functions

The following diagram presents how roles within a BDI context participate in the process of authorisation. The prerequisite here is that the Data Owner has an existing business relationship with:

* The Authorization Register: to manage authorisations on his behalf
* The Service Consumer: to consumer data (or a service) on his behalf
* The Data Service Provider: to provide a data service on his behalf

There is no existing bilateral relationship required between the other parties involved. The contractual context for all transactions is the membership of a BDI Association.

On an abstract level the interaction is as follows:

1. The Data Owner manages Authorizations in the Authorization Register
2. A Service Consumer requests authorisation evidence at the Authorization Register
3. The Service Consumer requests data and presents the evidence at the Data Service Provide
4. The Data Service Provider evaluates the data request and the provided evidence and if they match, the requested data is returned

Interactions 2, 3 and 4 will usually take place right after each other, while interaction 1 can take place at any moment (prior to interaction 2, 3 and 4).

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>BDI abstract authorisation interaction</p></figcaption></figure>

## Core design decisions

The following challenges are recognised in this concept:

1. If a Data Owner manages authorisations at multiple Authorization Registers, authorisations could become incomparable, when each Authorization Register defines it's own way for storing authorisations, thereby limiting the Data Owner to achieve maximum data sovereignty.
2. The Authorization Register, Service Consumer and Data Service Provider should sufficiently align in a common language, otherwise the parties won't be able to request, create and consume authorisation evidence.
3. As a policy language, XACML is suited to these tasks but requires rigorous standardization and good tools for evaluation and maintenance to be effective and practical in real-world applications. Development of these standard roles is parts of the BDI Framework deployment.
4. As a policy mechanism in data trading, ODRL allows for machine-readable policies for data usage, supporting automation of contract negotiation. In the BDI framework, this is related to data licenses. In operational data spaces, the policies for data usage (data licenses) are in most cases not used for contract negotiation but for standardizing terms and conditions, such as ‘privacy protected’ or ‘commercially confidential’.

{% hint style="success" %}
BDI specifies the following to support an interoperable authorisation model for BDI Associations, countering the challenges mentioned above.

1. BDI recommends to use a role based authorisation model.
2. BDI will define a BDI Role Model to support interoperability between role based access control models as implemented by Authorization Registers.
3. BDI will specify the evidence API and structure of authorisation evidence (technical specifications). This will be part of the BDI development documentation.
4. BDI will define a type and attribute model to support collaboration between parties involved.
{% endhint %}

{% hint style="warning" %}
BDI does not specify how parties can manage authorisations at Authorization Registers, nor does it specify how Authorization Registers store these authorizations.

In practice one party could fulfil multiple roles. A common existing combination would be the role of Authorization Register and Data Service Provider combined.
{% endhint %}

## Future topics

The following specifications are expected:

* BDI Role Model
* BDI Type and Attribute Model

## Further reading

This building block has been drafted using the following sources, that provide opportunity for further reading:
