# Digital Identity

## Summary

This building block supports trust among participants by defining how digital identies play a role in BDI. In it's implementation, BDI aligns with iSHARE's implementation of digital identities, relying on eIDAS's trusted lists of qualified Trusted Service Providers as trust anchors.

## Purpose of the building block

The purpose of this building block is to support the framework for trust among parties, by ensuring that parties can provide and receive a verified digital identity. This way all interactions within BDI (onboarding, offboarding, data exchange, service consumption, etc.) will take place between trusted parties.

## Concepts

The following concepts (from the BDI Glossary), all regarding legal entities, are particularly relevant in this building block:

<table><thead><tr><th width="262">Concept</th><th>Meaning</th></tr></thead><tbody><tr><td>Business Partners</td><td><ul><li>Members of other BDI Associations than the root BDI Association</li></ul></td></tr><tr><td>Member</td><td><ul><li>Legal entity as member of a root BDI Association</li></ul></td></tr><tr><td>Outsider</td><td><ul><li>Member of a BDI Association other than the root</li></ul></td></tr><tr><td>Preferred Business Partners</td><td><ul><li>Outsiders</li><li>Those who have agreed to the specific terms and conditions of the local BDI Association, which maintains its own Business Partner Reputation Model</li></ul></td></tr><tr><td>Visitor</td><td><ul><li>Outsider with a better reputation score than a set minimum</li></ul></td></tr></tbody></table>

Besides legal entities, identifiers for natural persons are part of BDI, as natural persons have a role as representee of a legal entity (in the [representation-register.md](../federation-kit/representation-register.md "mention") and in the [professional-qualification-register.md](../federation-kit/professional-qualification-register.md "mention")).

<figure><img src="../../.gitbook/assets/20240704 BDI Roles v03.png" alt=""><figcaption><p>How a Business Partner from another Trust Framework can join a BDI Association.</p></figcaption></figure>

## Risks

An insufficient framework for digital identity, might lead to a lower level of trust among parties and will harm the overall trust in BDI.

## Interlinkages with other building blocks

This building block describes the BDI principles for digital identity, whereas the building block on [verifiable-credentials.md](../verifiable-credentials-kit/verifiable-credentials.md "mention") describes how Verifiable Credentials are applied to exchange proof of identity between parties.

## Core design decisions

BDI uses iSHARE principles on identity management. In particular these principles are defined here:

* [Facilitate portable identity(s) for parties and humans](https://framework.ishare.eu/is/facilitate-portable-identity-s-for-parties-and-hum)
* [Identification by EORI](https://framework.ishare.eu/is/identification-by-eori)
* [The role of Identity Provider](https://framework.ishare.eu/is/functional-requirements-per-role#Functionalrequirementsperrole-IdentityProvider)
* [The acknowledgment of eIDAS](https://framework.ishare.eu/is/regulation-on-electronic-identification-and-trust-)

On the technical side the following pages are relevant:

* [The PKI standard](https://dev.ishare.eu/reference/standards.html#pki)
* [The specifications for the Identity Provider role](https://dev.ishare.eu/identity-provider/authorize.html)

BDI relies on the iSHARE governance to select eID Providers that are accepted.

## Future topics

The iSHARE framework on the topic of digital identification is subject to [RFC031](https://gitlab.com/ishare-foundation/cab/rfc/-/issues/11). This will impact the BDI as well.

## Further reading

This building block has been drafted using the following sources, that provide opportunity for further reading:

* [DSSC Blueprint building block “Identity and Attestation Management](https://dssc.eu/space/BVE/357075352/Identity+and+Attestation+Management)
* [https://www.w3.org/TR/vc-data-model-2.0/](https://www.w3.org/TR/vc-data-model-2.0/)
* [iSHARE Framework documentation](https://framework.ishare.eu/), specifically on the topic of identities
* [iSHARE Developer Portal documentation](https://dev.ishare.eu/)
