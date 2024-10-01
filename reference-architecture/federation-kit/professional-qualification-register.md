# Professional Qualification Register

## Summary

The Professional Qualification Register is a building block that lets other entities verifiy  if representatives of the owner/controlling party of the Professional Qualification Register have the required qualifications.

The Professional Qualification Register registers the relationship between&#x20;

* the digital identity of the owner/controller&#x20;
* the proof of relevant professional qualifications of humans or legal entities
  * for instance verifiable representations of verifiable credentials
* the digital identities of these humans or legal entities

The relationship is transient: as long as it is relevant, and only for relevant qualifications.

The legal implication is that the owner/controlling party assumes accountability and liability for the existence and verification of the relevant Professional Qailification of its representatvies.

## Purpose of the building block

The purpose of the building block is to specify:

* &#x20;the interface and structure for storing and validating proof of selected and relevant professional qualifications.&#x20;
* the interface and structure to issue claims of Professional Qualification (Evidence)&#x20;
* to allow automated verifications of the claim in the Evidence.

The building block is used in Boundary Management, especially Physical Asset Boundaries and Digital Asset Boundaries, for example:

* access to a location where specific safety training is required
* delivering services that require professional qualifications
* use of certified processes (ISO certifications of tools)

## Concepts

[**Personal qualifications**](https://www.lawinsider.com/dictionary/personal-qualifications) means criteria related to an individual's background, including completion of an approved educational program, satisfactory performance on an examination, work experience, testimonials and completion of continuing education.

Personal qualifications are issued by competent organizations to natural person. Examples include universities (education courses), former employers (work experience), governments (VOG statements, driving license), and terminals & chemical plants (health and safety courses).

**Process qualifications** means criteria related to a process, such as certification of compliance to an ISO standard.&#x20;

## Implementation Considerations

The traditional paper based approach is to collect and store a physical file of the professional qualifications and to present the applicable qualifications when required. This is a cumbersome process and sensitive to fraud as many copies are kept at multiple sources of which varying levels of controls are applied to validate authenticity and validity of the evidence.

A modern approach is to collect the qualifications in an mobile app or a secure card. On request the employee can share the qualifications. Examples include the [Vakpaspoort of the Centraal Register Techniek](https://centraalregistertechniek.nl/app-vakpaspoort-techniek) and the [XS-ID of Secure Logistics](https://www.secure-logistics.nl/en/xs-key/).

The drawback of the app approach is that the different implementations are not interoperable. For example the protocols for retrieving the qualifications from the sources are not standardized. Also the protocols for presenting the qualifications are not standardized.

The (open) European Wallet is an enticing prospect because it will standardize both the retrieving and the presentment of the qualifications as verifiable credentials in the personal wallet of the employee.&#x20;

The Professional Qaulification Register stores only the verificanle representations of specific relevant qualifications.

&#x20;The following is to be considered:

* the personal qualifications are personal data and most likely privacy sensitive. Sharing this data with other organizations is limited to its purpose meaning that anything else not trivial is to be masked.
* It requires clear authorization conditions to be provided to the association to ensure that the data is only made available to the organizations that can present clear evidence of the need need to access the data.

## Interlinkages with other building blocks

This Building Block is linked with

* Trust KIT
  * Digital Identity
  * Authentication
  * Authorization
* Representation Register
* Boundary Management

## Elements and their key functions

## Core design decisions

[(EU) Wallets](https://ec.europa.eu/digital-building-blocks/sites/display/EUDIGITALIDENTITYWALLET) are under development. Large scale pilots have started, however focus initially has been on the natural person as civillian in relation to it's state authority and lesser on the 'role' of a natural person as a employee / staff in relation to a Legal Entity / business.

Irrespectivly certain developments and initial adoption show the way towards which standards to adopt for the BDI:

* The Verifiable Credential Data Model ([current v2.0](https://www.w3.org/TR/vc-data-model-2.0/)) is to be adhered to. This defines the 'shape' of the claims and belonging metadata that cryptographically prove who issued it. Not the content of the credential itself. This is to be defined in large-scale pilots to strike consensus and find adoption.
* The VC can be stored in a Wallet, however also BDI supports the more centralized register where the credential with a claim is stored on behalf of the subject. Exchange is through tokens (JWT's) where [_embedddd JWTs with VCs_](https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf) for representation evidence to provide a[ Chain of Trust](https://en.wikipedia.org/wiki/Chain\_of\_trust). _Specification of the application of the protocol and interfacing is work in progress_

## Future topics

## Further reading
