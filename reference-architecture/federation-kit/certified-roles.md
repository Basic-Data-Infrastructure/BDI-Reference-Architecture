---
description: >-
  This building block was prepared  for
  https://topsectorlogistiek.atlassian.net/browse/BDI-108.
---

# Certified Roles

## Summary

BDI defines Certified Roles as the officially recognized roles for activity in the logistic chain. They form the basis for role-based authorizations and authentication.  Thus, these play a vital role in achieving trust for data sharing in BDI associations.&#x20;

## Purpose of the building block

From the DSSC building blocks, [Data Sovereignty and Trust building blocks](https://dssc.eu/space/BVE/357075333/Data+Sovereignty+and+Trust), form the functional basis for Certified Roles.&#x20;

For identification, authorisation and authentication services to be offered to a specific security standard and be readily available for Association members to use, Certified roles are required.&#x20;

BDI defines these certified roles :&#x20;

* &#x20;Authorisation Registry&#x20;
* Identity Provider&#x20;
* Identity Broker

Other important roles in BDI include : Event Broker, Association Administrator and Mandate Register. &#x20;

## Concepts

| Role                   | Description                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Certified role         | <p>Certified Roles are Roles for which certification is required, and to facilitate certain functions  that every party within the Association must be able to rely upon. <br>A BDI Certified Party MUST apply to the Certifying Authority for certification and, after providing sufficient proof, MUST sign a certification agreement with the BDI Association Administrator. </p> |
| Authorization Register | Holds authorization policies for one or more Data Owners on access to data.                                                                                                                                                                                                                                                                                                          |
| Identity Provider      | <p></p><p>The Identity Provider-role is fulfilled by a legal entity whose tooling identifies and authenticates humans (and specifically, Human Data Consumers representing Data Consumers).</p>                                                                                                                                                                                      |
| Identity Broker        | The **Identity Broker**-role is fulfilled by a legal entity that provides Data Service Providers access to different Identity Providers, and that offers humans the option to choose with which Identity Provider to identify and authenticate themselves.                                                                                                                           |



## Implementation Considerations

&#x20;[iSHARE Trust Framework](https://framework.ishare.eu/is/functional-requirements-per-role) defines the functional requirements per role for Certified Roles.&#x20;

All mentioned iSHARE requirements must be considered as BDI requirements.&#x20;

**Components for functional implemention of Certified Roles** :

Verifiable Credentials - providing a means for Authentication&#x20;

Association Register - Trusted list&#x20;

Best practices for automated consent management, e.g. concerning GDPR

Trust Protocol and Policy Structures

Data intermediaries for implementing consent management&#x20;

## Interlinkages with other building blocks

This building block is closely associated with the building blocks on Authorisation and Digital identity.&#x20;

The implementation of this building block closely relates to the Onboarding T\&C's Association articles building block&#x20;

## Elements and their key functions

In principle with the iSHARE Trust Framework, Certified Roles :

[Support Machine to Machine (M2M) interaction](https://framework.ishare.eu/is/support-machine-to-machine-m2m-interaction)

[Support Human to Machine (H2M) interaction](https://framework.ishare.eu/is/support-human-to-machine-h2m-interaction)

[Facilitate portable identity(s) for parties and humans](https://framework.ishare.eu/is/facilitate-portable-identity-s-for-parties-and-hum)

[Facilitate flexible authorizations, applicable in any context](https://framework.ishare.eu/is/facilitate-flexible-authorizations-applicable-in-a)

[Enable data exchange based on delegations - even between unknown parties](https://framework.ishare.eu/is/enable-data-exchange-based-on-delegations-even-bet)

## Core design decisions

The iSHARE Trust Framework provides a comprehensive description for Certified Roles. Most notably :&#x20;

* [The role of an Authorisation Registry](https://framework.ishare.eu/is/framework-and-roles)
* [Facilitate portable identity(s) for parties and humans](https://framework.ishare.eu/is/facilitate-portable-identity-s-for-parties-and-hum)
* [The role of Identity Provider](https://framework.ishare.eu/is/functional-requirements-per-role#Functionalrequirementsperrole-IdentityProvider)

## Future topics

## Further reading

[https://framework.ishare.eu/is/framework-and-roles](https://framework.ishare.eu/is/framework-and-roles)

[https://dssc.eu/space/BVE/357075333/Data+Sovereignty+and+Trust](https://dssc.eu/space/BVE/357075333/Data+Sovereignty+and+Trust)

[https://framework.ishare.eu/is/functional-requirements-per-role](https://framework.ishare.eu/is/functional-requirements-per-role)

