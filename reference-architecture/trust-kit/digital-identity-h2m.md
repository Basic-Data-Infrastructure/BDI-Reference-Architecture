# Digital Identity H2M

**Summary**

This building block supports trust among participants by defining how digital identities play a role in BDI in human-to-machine (H2M) interactions.

Digital identifiers for IT-processes acting on behalf of an organization/legal entity are described in Digital Identity (M2M).

**Purpose of the building block**

The purpose of this building block is to support the framework for trust in Boundary Management, where humans are acting as a representative of a legal entity by means of  (digital) devices and telecommunication.

**Concepts**

Boundary Management for humans relates to:

\-          A human, acting as representative for a legal entity desiring access to data or an application owned/controlled by another legal entity

&#x20;           _o   For example: login to an application_

\-          A human, acting as representative for a legal entity desiring access to a location owned/controlled by another legal entity

&#x20;  _o   For example: entering a protected zone_

\-          A human, acting as representative for a legal entity involved in transferring as asset (cargo) and/or liabilities for the asset between the two legal entities

&#x20;  _o   For example: picking up cargo by a transporter_

The building block ensures that the digital identity of the human involved in (digital) interactions can be :

\-          Authenticated

\-          Related to Representation evidence

&#x20;         _o   In what role and capacity, on behalf of which legal entity, with a specific mandate_

\-          Related to Professional Qualification evidence

&#x20;       _o   Evidence of professional qualifications_

The core concept is that identity is dynamically related to (potentially multiple concurrent) representations for (potentially multiple concurrent) legal entities: the legal entity assumes liability and accountability for actions of the human.

**Identity**

Identity is a legal concept defined by a nation state and assigned to a human by that nation state. Digital identities are related to that core identity by Identity Providers.

A very common but relatively weak method is an email-address (optionally combined with a password and/or 2FA): the organization issuing the email-address acts as Identity Provider. The mobile phone number is another very common method: the Mobile Operator issuing SIM-cards acts as Identity Provider.

Identity Providers can choose to increase the level of proof that the nation-state identity and the digital identity they assign are uniquely connected: for instance live verification of identity papers and signatures (such as eIDAS E-herkenning) , or adding biometric identification parameters (such as Secure Logistics) on a smart card.

The push for electronic Wallets provides a new means to store and show a digital identity that can be authenticated.

Authentication of  the digital identity delivers proof of the nation-state identity. The chosen Identity Provider and level or proof should match the business requirements.

**Representation**

Once the identity has been authenticated, the next question is what legal entity is represented by the human in  this specific instance/moment, in the context of a specific order/contract.

A human may have multiple roles for multiple legal entities, at the same time. A human may be sent by a subcontractor of a main contractor: the representation chain has to be verified.

Once the representation has been established, the mandate can be verified.

In many cases the human needs to have adequate professional qualifications for the task at hand: professional drivers license, safety training, dangerous goods handling, etc.

Verifiable credentials of Professional Qualifications and verifiable presentations of the specific qualification are a new method for digital verification.

**Risks**

An insufficient framework for digital identity, might lead to a lower level of trust among parties and will harm the overall trust in BDI.

**Interlinkages with other building blocks**

This building block describes the BDI principles for digital identity for H2M interactions.

The related building blocks are:

\-          Digital Identity H2M

\-          Authentication M2M

\-          Authentication H2M

\-          Authorization

\-          Association register

\-          Zero Trust Check

\-          Representation Register

\-          Professional Qualification Register

The most important related Kits are

\-          Trust Kit

\-          Federation Kit

\-          Boundary Management Kit

&#x20;

**Core design decisions**

Parties choose their Identity Providers fitting to the requirements.

The BDI adds the link to representation and professional qualifications.

In Europe the eIDAS regulation is a solid foundation for the identity ecosystem.

Selfsigned certificates for digital identities are a low-barrier entry level solution, with serious limitations on trust, federation and scaling.

&#x20;

* **​Future topics**

&#x20;

**Further reading**

&#x20;

&#x20;
