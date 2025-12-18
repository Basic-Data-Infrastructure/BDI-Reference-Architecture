---
cover: >-
  https://images.unsplash.com/photo-1515378960530-7c0da6231fb1?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxjb21wdXRlcnxlbnwwfHx8fDE3NjU0NjU2NDF8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 236
---

# Professional Qualification Chain

## 1. Summary

The Professional Qualification Chain is a method that lets other entities verifiy if representatives of the entity that isses the evidence have the required qualifications.

The Professional Qualification Chain registers the relationship between

* the digital identity of the owner/controller
* the proof of relevant professional qualifications of humans or legal entities
  * for instance verifiable representations of verifiable credentials
* the digital identities of these humans or legal entities

The relationship is transient: as long as it is relevant, and only for relevant qualifications.

The legal implication is that the owner/controlling party assumes accountability and liability for the existence and verification of the relevant Professional Qailification of its representatvies.

## 2. Purpose of the building block

The purpose of the building block is to specify:

* the interface and structure to issue claims of Professional Qualification (Evidence)
* to allow automated verifications of the claim in the Evidence.

The building block is used in Boundary Management, especially Physical Asset Boundaries and Digital Asset Boundaries, for example:

* access to a location where specific safety training is required
* delivering services that require professional qualifications
* use of certified processes (ISO certifications of tools)

## 3. Concepts

[**Personal qualifications**](https://www.lawinsider.com/dictionary/personal-qualifications) means criteria related to an individual's background, including completion of an approved educational program, satisfactory performance on an examination, work experience, testimonials and completion of continuing education.

Personal qualifications are issued by competent organizations to natural person. Examples include universities (education courses), former employers (work experience), governments (VOG statements, driving license), and terminals & chemical plants (health and safety courses).

**Process qualifications** means criteria related to a process, such as certification of compliance to an ISO standard.

## 4. Implementation Considerations

The traditional paper based approach is to collect and store a physical file of the professional qualifications and to present the applicable qualifications when required. This is a cumbersome process and sensitive to fraud as many copies are kept at multiple sources of which varying levels of controls are applied to validate authenticity and validity of the evidence.

A modern approach is to collect the qualifications in an mobile app or a secure card. On request the employee can share the qualifications. Examples include the [Vakpaspoort of the Centraal Register Techniek](https://centraalregistertechniek.nl/app-vakpaspoort-techniek) and the [XS-ID of Secure Logistics](https://www.secure-logistics.nl/en/xs-key/).

The drawback of the app approach is that the different implementations are not interoperable. For example the protocols for retrieving the qualifications from the sources are not standardized. Also the protocols for presenting the qualifications are not standardized.

The (open) European Wallet is an enticing prospect because it will standardize both the retrieving and the presentment of the qualifications as verifiable credentials in the personal wallet of the employee.

The Professional Qaulification Chain transmits only the verificanle representations of specific relevant qualifications.

The following is to be considered:

* the personal qualifications are personal data and most likely privacy sensitive. Sharing this data with other organizations is limited to its purpose meaning that anything else not trivial is to be masked.
* It requires clear authorization conditions to be provided to the association to ensure that the data is only made available to the organizations that can present clear evidence of the need need to access the data.

## 5. Interlinkages with other building blocks

<a href="../trust-kit/digital-identity/" class="button secondary">Digital Identity</a>  <a href="../trust-kit/authentication/" class="button secondary">Authentication</a>  <a href="../trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a> &#x20;

<a href="representation-register.md" class="button secondary">Representation Chain</a>  <a href="../boundary-management-kit/" class="button secondary">Boundary Management</a>

## 6. Core design decisions

[(EU) Wallets](https://ec.europa.eu/digital-building-blocks/sites/display/EUDIGITALIDENTITYWALLET) are under development. Large scale pilots have started, however focus initially has been on the natural person as civillian in relation to it's state authority and lesser on the 'role' of a natural person as a employee / staff in relation to a Legal Entity / business.

Relevant standards to consider or adopt for the BDI are:

* The Verifiable Credential Data Model ([current v2.0](https://www.w3.org/TR/vc-data-model-2.0/)). This defines the 'shape' of the claims and belonging metadata that cryptographically prove who issued it. Not the content of the credential itself. This is to be defined in large-scale pilots to strike consensus and find adoption.
* The VC can be stored in a Wallet. The BDI supports an exchange is through tokens (JWT's) where [_embedddd JWTs with VCs_](https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf) for representation evidence to provide a[ Chain of Trust](https://en.wikipedia.org/wiki/Chain_of_trust). _Specification of the application of the protocol and interfacing is work in progress_

## 7. Future topics & Future reading
