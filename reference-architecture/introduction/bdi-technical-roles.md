# BDI Technical Roles

### Summary

The building block aims to define BDI's technical roles, including Identity Provider, Identity Broker, Association Administrator, Data Owner, Data Service Provider, and Data Consumer. Each role plays a crucial part in managing identity, data control, and service provision within BDI's framework.

## Purpose of this building block

{% hint style="info" %}
**The purpose of this building block is to define the technical roles in BDI**

BDI defines these technical roles :

* Identity Provider
* Identity Broker
* Association Administrator
* Data Owner
* Data Service Provider&#x20;
* Data Consumer
{% endhint %}

### Concepts

| Role                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Identity Provider         | The Identity Provider-role is fulfilled by a legal entity whose tooling identifies and authenticates humans (and specifically, Human Data Consumers representing Data Consumers).                                                                                                                                                                                                                                                                                                                        |
| Identity Broker           | The **Identity Broker**-role is fulfilled by a legal entity that provides Data Service Providers access to different Identity Providers, and that offers humans the option to choose with which Identity Provider to identify and authenticate themselves.                                                                                                                                                                                                                                               |
| Association Administrator | Functionary responsible for operating the services of a BDI Association reporting to its Members.                                                                                                                                                                                                                                                                                                                                                                                                        |
| Data Owner                | <p></p><p>The data Owner is a legal entity who:</p><ul><li>Has control over data and access to data</li><li>Controls decisions on Data Sovereignty and Trust Sovereignty</li><li>Controls authorization policies, representation rules, professional qualification verification of staff and contractors</li><li>Controls subscription to the Event Pub/Sub Service, and publishing of events to subscribers</li><li>Controls discovery and endpoints</li><li>Controls roles assumed by entity</li></ul> |
| Data Service Provider     | A Data Service Provider that acts under supervision and on behalf of the Data Owner                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Data Consumer             | <p></p><ul><li>Requests access to data and/or Representation Register and/or Professional Qualification Register of the Data Owner</li><li>Controls discovery and endpoints</li><li>Requests subscription to Event Pub/Sub Service of the Data Owner, receives and evaluates events.</li></ul>                                                                                                                                                                                                           |

### Implementation Considerations

Implementation of the basic BDI mechanisms assumes the existence of these technical roles.

### Interlinkages with other building blocks

* Digital Identity
* Authentication
* Authorisation
* Association Register
* Zero Trust Check

### Core design decisions

The iSHARE Trust Framework provides a comprehensive description of what iSHARE calls Certified Roles. The Common Roles of the BDI are derived from these descriptions, such as:

* [The role of an Authorisation Registry](https://framework.ishare.eu/is/framework-and-roles)
* [The role of Identity Provider](https://framework.ishare.eu/is/functional-requirements-per-role#Functionalrequirementsperrole-IdentityProvider)

### Further reading

[https://framework.ishare.eu/is/framework-and-roles](https://framework.ishare.eu/is/framework-and-roles)

[https://dssc.eu/space/BVE/357075333/Data+Sovereignty+and+Trust](https://dssc.eu/space/BVE/357075333/Data+Sovereignty+and+Trust)

[https://framework.ishare.eu/is/functional-requirements-per-role](https://framework.ishare.eu/is/functional-requirements-per-role)
