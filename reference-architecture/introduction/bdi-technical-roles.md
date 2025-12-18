---
cover: >-
  https://images.unsplash.com/photo-1570989614585-581ee5f7e165?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxyb2xlc3xlbnwwfHx8fDE3NjQzMjcwNjR8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 326
---

# BDI Technical Roles

## 1. Introduction&#x20;

The building block aims to define BDI's technical roles, including Identity Provider, Identity Broker, Association Administrator, Data Owner, Data Service Provider, and Data Consumer. Each role plays a crucial part in managing identity, data control, and service provision within BDI's framework.

## 2. Purpose of this building block

The purpose of this building block is to define the technical roles in BDI.&#x20;

## 3. Concepts

The technical roles of the BDI are given and explained below.&#x20;

| Role                          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Identity Provider**         | The Identity Provider-role is fulfilled by a legal entity whose tooling identifies and authenticates humans (and specifically, Human Data Consumers representing Data Consumers).                                                                                                                                                                                                                                                                                                                 |
| **Identity Broker**           | The **Identity Broker**-role is fulfilled by a legal entity that provides Data Service Providers access to different Identity Providers, and that offers humans the option to choose with which Identity Provider to identify and authenticate themselves.                                                                                                                                                                                                                                        |
| **Association Administrator** | Functionary responsible for operating the services of a BDI Association reporting to its Members.                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Data Owner**                | <p>The data Owner is a legal entity who:</p><ul><li>Has control over data and access to data</li><li>Controls decisions on Data Sovereignty and Trust Sovereignty</li><li>Controls authorization policies, representation rules, professional qualification verification of staff and contractors</li><li>Controls subscription to the Event Pub/Sub Service, and publishing of events to subscribers</li><li>Controls discovery and endpoints</li><li>Controls roles assumed by entity</li></ul> |
| **Data Service Provider**     | A Data Service Provider that acts under supervision and on behalf of the Data Owner                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Data Consumer**             | <ul><li>Requests access to data and/or Representation Register and/or Professional Qualification Register of the Data Owner</li><li>Controls discovery and endpoints</li><li>Requests subscription to Event Pub/Sub Service of the Data Owner, receives and evaluates events.</li></ul>                                                                                                                                                                                                           |

## 4. Implementation Considerations

Implementation of the basic BDI mechanisms assumes the existence of these technical roles.

## 5. Interactions with other building blocks

<a href="../trust-kit/digital-identity/" class="button secondary">Digital Identity</a>  <a href="../trust-kit/authentication/" class="button secondary">Authentication</a>  <a href="../trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a>  <a href="../../readme/trust-kit/association-register-1.md" class="button secondary">Association Register</a> &#x20;

## 6. Further reading

[https://framework.ishare.eu/is/framework-and-roles](https://framework.ishare.eu/is/framework-and-roles)

[https://dssc.eu/space/BVE/357075333/Data+Sovereignty+and+Trust](https://dssc.eu/space/BVE/357075333/Data+Sovereignty+and+Trust)

[https://framework.ishare.eu/is/functional-requirements-per-role](https://framework.ishare.eu/is/functional-requirements-per-role)
