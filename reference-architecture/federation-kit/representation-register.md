# Representation Chain

**Summary**

The Representation Chain is a building block that lets other entities verifiy mandates.&#x20;

The Representation Chain is a method to show verifiable mandates given to natural persons, legal entities or governmental bodies that act on behalf of the entity that issues the mandate. A mandate is a record of representation by an [authoritative](https://en.wiktionary.org/wiki/authoritative#English) [command](https://en.wiktionary.org/wiki/command#English) (mandator) provided to whom a mandate is assigned (mandatee). The mandate transfers accountability and liability to the mandator for acts done by the mandatee.

The Representation Chain consists of a Representation Evidence (nested or embedded JWT's) that can be verified offline and/or online by a check at the issuer that the token is still valid .

**Purpose**

&#x20;

The Representation Chain is a method to show verifiable mandates given to natural persons, legal entities or governmental bodies that act on behalf of the entity that issues the mandate. A mandate is a record of representation by an [authoritative](https://en.wiktionary.org/wiki/authoritative#English) [command](https://en.wiktionary.org/wiki/command#English) (mandator) provided to whom a mandate is assigned (mandatee). The mandate transfers accountability and liability to the mandator for acts done by the mandatee.

This covers H2M and M2M (process acting on behalf of a legal entity) use cases.

The Representation Chain is the Building Block to facilitate Boundary Management, especially for Physical Acces Boundaries [https://app.gitbook.com/o/6jFQJqnMRyd4T2pZ1IBi/s/EsnYrgeqsPPZtbALTQAj/\~/changes/224/reference-architecture/boundary-management/physical-asset-boundaries](../boundary-management-kit/physical-asset-boundaries.md)

&#x20;and Legal Asset Boundaries. [https://app.gitbook.com/o/6jFQJqnMRyd4T2pZ1IBi/s/EsnYrgeqsPPZtbALTQAj/\~/changes/224/reference-architecture/boundary-management/legal-asset-boundaries](../boundary-management-kit/legal-asset-boundaries.md)

**Relationship to other Building Blocks**

The Representation Chain is (directly or indirectly) related to the following Building Blocks:

* Authentication
* Authorisation
* Digital Identity:&#x20;
* Common Roles:
* Professional Qualification Chain : this is a similar methode to show proof of the professional qualifications of Natural Persons acting on behalf of the issuing entity.
* Verifiable Credentials: (future work)

**Elements & core Functions**

A Representation Chain is not a central register but a method.&#x20;

The Representation Chain holds the relationship between&#x20;

* the (digital identity of the) mandator
* the digital identities of mandatees
* the scope of the mandate
  * role based
  * optionally order related (transient)
* other relevant data

The  Representation Evidence is in the form of a nested JWT including additional information as desired. The JWT is transferred to the mandatee (H2M use case Physical Asset Boundary Management) for temporary use. The mandatee show/transfers the JWT as Representation Evidence to third parties, online or offline. These parties can verify the (nested) JWT and optionally follow the link's in the JWT's to the respective issuers to check to validity of the tokens.

The third party does not need to be Member of an Association, lowering the barriers for implementation.



**Further Reading**

* Verifiable Credentials
* E-Herkenning
* [https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf](https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf)

