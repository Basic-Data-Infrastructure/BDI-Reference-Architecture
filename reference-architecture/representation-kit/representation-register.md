# Representation Register

**Summary**

The Representation Register is a building block that lets other entities verifiy mandates.&#x20;

The Representation Register registers mandates given to natural persons, legal entities or governmental bodies that act on behalf of the entity that issues the mandate. A mandate is a record of representation by an [authoritative](https://en.wiktionary.org/wiki/authoritative#English) [command](https://en.wiktionary.org/wiki/command#English) (mandator) provided to whom a mandate is assigned (mandatee). The mandate transfers accountability and liability to the mandator for acts done by the mandatee.

The Representation Register can issue  a Representation Evidence (JWT) that can be verified offline and/or by a check that the token is still valid at the Representation Register.

**Purpose**

The Representation Register registers mandates in the form of Representation Evidence given to natural persons, legal entities or governmental bodies that act on behalf of the legal entity owning or controlling the Representation Register. This covers H2M and M2M (process acting on behalf of a legal entity) use cases.

The Representation Register registers mandates given to natural persons, legal entities or governmental bodies that act on behalf of the entity that issues the mandate. A mandate is a record of representation by an [authoritative](https://en.wiktionary.org/wiki/authoritative#English) [command](https://en.wiktionary.org/wiki/command#English) (mandator) provided to whom a mandate is assigned (mandatee). The mandate transfers accountability and liability to the mandator for acts done by the mandatee.

Examples of existing Representation Registers include:

* Internal Representation Registers within a Legal Person related to IAM processes. Office 365 is widely used which uses Microsoft Entra (AAD) as a “Directory” of natural persons with email addresses, etc.&#x20;
* E-Herkenning which is the Dutch B2B eIDAS Framework. Note that most other European countries don’t have a similar Framework

The Representation Register is the Building Block to facilitate Boundary Management, especially for Physical Acces Boundaries [https://app.gitbook.com/o/6jFQJqnMRyd4T2pZ1IBi/s/EsnYrgeqsPPZtbALTQAj/\~/changes/224/reference-architecture/boundary-management/physical-asset-boundaries](../boundary-management/physical-asset-boundaries.md)

&#x20;and Legal Asset Boundaries. [https://app.gitbook.com/o/6jFQJqnMRyd4T2pZ1IBi/s/EsnYrgeqsPPZtbALTQAj/\~/changes/224/reference-architecture/boundary-management/legal-asset-boundaries](../boundary-management/legal-asset-boundaries.md)

**Relationship to other Building Blocks**

The Representation Register is (directly or indirectly) related to the following Building Blocks:

* Authentication
* Authorisation
* Digital Identity:&#x20;
* Common Roles:
* Professional Qualification Register: this registers the professional qualifications of Natural Persons.
* Verifiable Credentials: (future work)

**Elements & core Functions**

A Representation Register is quite similar but not identical to an Autorization Register.

The Register records the relationship between&#x20;

* the (digital identity of the) mandator
* the digital identities of mandatees
* the scope of the mandate
  * role based
  * optionally order related (transient)

The Representation Register can issue a Representation Evidence, for example in the form of a nested JWT including additional information as desired. The JWT is transferred to the mandatee (H2M use case P{hysical Asset Boundary Management) for temporary use. The mandatee show/transfers the JWT as Representation Evidence to third parties, online or offline. These parties can verify the JWT and optionally follow the link in the JWT to the Representation Register to check to validity of the token.

The third party does not need to be Member of an Association, lowering the barriers for implementation.

The Representation Register can interact with Autorization Registers for M2M use.

**Further Reading**

* Verifiable Credentials
* E-Herkenning
* [https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf](https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf)

