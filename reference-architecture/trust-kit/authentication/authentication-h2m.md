# Authentication H2M

### Summary&#x20;

Authentication is the process of proving that the user (human or IT process) with a digital identity is the rightful owner of that identity (definition from IDpro).

Authentication is required in both H2M (Human to Machine) and M2M (Machine to Machine) use cases. In this page  we focus on H2M use cases: the human interacts with a machine by means of an IT-process under its direct control (device, IT-process, wallet etc.), or by digital data (e.g. QR code). Authentication precedes verification of Representation and subsequent Authorization.

The complexity of H2M authentication is increased by privacy regulations: authenticating a human reveals his/hers identity.

### Purpose of the building block&#x20;

Ensure that BDI users (H2M) are recognized,  identified  as a person and in a specific role on behalf of a legal entity: to prevent misuse, fraud, theft of data, services and physical goods. Enable smooth,  efficient and secure Boundary Management.

Ensure that privacy leaks as a result of authentication are limited.

### Concepts&#x20;

The use cases relate to Boundary Management:

\-          A human, acting as representative for a legal entity desiring access to data or an application owned/controlled by another legal entity

&#x20;             o  For example: login to an application

\-          A human, acting as representative for a legal entity desiring access to a location owned/controlled by another legal entity

&#x20;             o   For example: entering a protected zone

\-          A human, acting as representative for a legal entity involved in transferring as asset (cargo) and/or liabilities for the asset between the two legal entities

&#x20;             o   For example: picking up cargo by a transporter

The building block ensures that the digital identity of the human involved in (digital) interactions can be  authenticated: authentication precedes verification of Representation. In the context of the BDI, the human is a representative of a legal entity  (organization): the legal entity assumes accountability and liability for the actions of the representative, limited to the mandate of the representative. A human can have multiple roles for multiple legal entities simultaneously.

The Identity Provider chosen by the parties/Association provides authentication. A local cache of trusted identities may be operated by an Association as a register.

Representation evidence may be stored in a register by an Association, or transmitted between parties in a nested Jason Web Token.

### Risks&#x20;

### Interlinkages with other building blocks&#x20;

This building block interlinks with:

·         Digital Identity & Identifiers

·         Authorizations

·         Discovery

·         Federation



### Core design decisions&#x20;

#### Certificate based authentication

### Future topics

&#x20;

### Further reading
