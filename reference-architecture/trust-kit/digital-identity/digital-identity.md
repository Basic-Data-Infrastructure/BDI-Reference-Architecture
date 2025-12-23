---
cover: >-
  https://images.unsplash.com/photo-1634322259580-4441b0dd5f81?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxpZGVudGl0eXxlbnwwfHx8fDE3NjQ3NDc5NTF8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 360
---

# Digital Identity M2M

## 1. Summary

This building block supports trust among participants by defining how digital identities play a role in BDI in machine-to-machine (M2M) interactions. The digital identifiers for natural persons are described in [Digital Identity (H2M)](digital-identity-h2m.md).

In its implementation, BDI aligns with iSHARE's implementation of digital identities, preferring PKI (public key infrastructure) certificates issued by a reputable identity provider as digital identity of parties like Service Providers. In Europe the eIDAS regulation is a solid foundation for the identity ecosystem.

## 2. Purpose of the building block

The purpose of this building block is to support the framework for trust among parties, by ensuring that parties can provide and receive a verified digital identity. An authenticated digital identity is the prerequisite for determining trust and subsequent authorization.

The building block ensures that interactions within BDI (onboarding, offboarding, data exchange, service consumption, etc.) will take place between identified and authenticated parties.

## 3. Concepts

The following concepts (from the BDI Glossary), all regarding legal entities, are particularly relevant in this building block:

| Member                          | Legal entity as member of its “home” BDI Association                                                                                                   |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Business Partners**           | Members of other BDI Associations than the “home” BDI Association                                                                                      |
| **Preferred Business Partners** | Outsiders who have agreed to the specific terms and conditions of the local BDI Association, which maintains its own Business Partner Reputation Model |
| **Outsider**                    | Anyone who is not a member of a BDI Association                                                                                                        |
| **Visitor**                     | Outsider with a better reputation score than a set minimum                                                                                             |

The figure below shows how a business partner from another BDI association can become a preferred Business partner of a BDI association.

<figure><picture><source srcset="../../../.gitbook/assets/251126 Maintenance_community_minor_changes_darkmode-digital identity m2m.drawio (2).png" media="(prefers-color-scheme: dark)"><img src="../../../.gitbook/assets/251126 Maintenance_community_minor_changes_darkmode-digital identity m2m.drawio (3).png" alt="" width="563"></picture><figcaption><p>Figure 1: BDI's trust framework</p></figcaption></figure>

## 4. Risks

An insufficient framework for digital identity might lead to a lower level of trust among parties and will harm the overall trust in BDI.

## 5. Interlinkages with other building blocks

This building block describes the BDI principles for digital identity for M2M interactions.

The related building blocks are:

<a href="digital-identity-h2m.md" class="button secondary">Digital Identity H2M</a> <a href="../authentication.md" class="button secondary">Authentication M2M</a> <a href="../authentication-h2m.md" class="button secondary">Authentication H2M</a>

<a href="../authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a> <a href="../../../readme/trust-kit/association-register-1.md" class="button secondary">Association Register</a>

The most important related Kits and concepts are:

<a href="../" class="button secondary">Trust KIT</a> <a href="../../federation-kit/" class="button secondary">Federation KIT</a> <a href="../../boundary-management-kit/" class="button secondary">Boundary Management</a>

## 6. Core design decisions

{% hint style="warning" %}
A digital identity has to be linked with the legal identifier of the legal entity that controls and takes responsibility and accountability for the IT-process that uses the digital identity in interactions with other IT processes.
{% endhint %}

A digital identity has to be linked with the legal identifier of the legal entity that controls and takes responsibility and accountability for the IT-process that uses the digital identity in interactions with other IT processes. For more details about possible identifiers, view the information below.

<details>

<summary>EORI-identifier</summary>

The EORI-identifier is the standard defined by the EC Customs for European entities. EORI stands for “Economic Operators Registration and Identification”. Not all European entities are required to register an EORI. Therefore, only a subset have registered an EORI.

</details>

<details>

<summary>EUID</summary>

Europe has also introduced an "EUID". This identifier is based on the local European Business Registries and will be used for the eIDAS 2 European Wallet.

</details>

<details>

<summary>VAT-numbers</summary>

VAT-numbers can also be used to identify organizations. European VAT-numbers can validated on a central site.

</details>

<details>

<summary>Others</summary>

Other identifier standards that are in use worldwide are:

* LEI
* DUNS (Dunn and Bradstreet Unique Number System)

</details>

{% hint style="info" %}
In practice it may be necessary for a party or an association to create a cross-reference register that relates an internal (unique) identifier with multiple external identifiers of a legal entity. One legal entity may have an EORI, LEI and DUNS identifier, or more.
{% endhint %}

The following should be noted regarding identifiers in the BDI:

* The BDI prefers PKI certificates issued by a reputable identity provider as digital identity of parties like Service Providers.
* In Europe the eIDAS regulation is a solid foundation for the identity ecosystem.
* Self-signed certificates for digital identities are a low-barrier entry level solution, with serious limitations on trust, federation and scaling

## 7. Further reading

<details>

<summary>Consider the following links for further reading</summary>

* [DSSC Blueprint building block “Identity and Attestation Management](https://dssc.eu/space/BVE/357075352/Identity+and+Attestation+Management)
* [https://taxation-customs.ec.europa.eu/customs-4/customs-procedures-import-and-export-0/customs-procedures/economic-operators-registration-and-identification-number-eori\_en](https://taxation-customs.ec.europa.eu/customs-4/customs-procedures-import-and-export-0/customs-procedures/economic-operators-registration-and-identification-number-eori_en)
* ​[https://e-justice.europa.eu/489/EN/business\_registers\_\_search\_for\_a\_company\_in\_the\_eu](https://e-justice.europa.eu/489/EN/business_registers__search_for_a_company_in_the_eu)
* [https://ec.europa.eu/taxation\_customs/vies/#/vat-validation-result](https://ec.europa.eu/taxation_customs/vies/#/vat-validation-result)
* [D-U-N-S Number Navigation Home – Dun & Bradstreet (dnb.com)](https://www.dnb.com/duns.html)
* [https://www.gleif.org/en/about-lei/introducing-the-legal-entity-identifier-lei](https://www.gleif.org/en/about-lei/introducing-the-legal-entity-identifier-lei)
* ​[https://www.w3.org/TR/vc-data-model-2.0/](https://www.w3.org/TR/vc-data-model-2.0/)​
* ​[iSHARE Framework documentation](https://framework.ishare.eu/), specifically on the topic of identities
* [Identification by EORI](https://framework.ishare.eu/is/identification-by-eori)​
* ​[The role of Identity Provider](https://framework.ishare.eu/is/functional-requirements-per-role#Functionalrequirementsperrole-IdentityProvider)​
* ​[The acknowledgment of eIDAS](https://framework.ishare.eu/is/regulation-on-electronic-identification-and-trust-)
* [The specifications for the Identity Provider role](https://dev.ishare.eu/identity-provider/authorize.html)​
* ​[iSHARE Developer Portal documentation](https://dev.ishare.eu/)

</details>
