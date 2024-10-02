# Digital Identity H2M

### Summary

This building block supports trust among participants by defining how digital identities play a role in BDI in human-to-machine (H2M) interactions.

Digital identifiers for IT-processes acting on behalf of an organization/legal entity are described in Digital Identity (M2M).

### Purpose of the building block

{% hint style="info" %}
The purpose of this building block is to support the framework for trust in Boundary Management, where humans are acting as a representative of a legal entity by means of  (digital) devices and telecommunication.
{% endhint %}

### Concepts

Boundary Management for humans relates to:

* A human, acting as representative for a legal entity desiring access to data or an application owned/controlled by another legal entity
  * _For example: login to an application_
* A human, acting as representative for a legal entity desiring access to a location owned/controlled by another legal entity
  * _For example: entering a protected zone_
* A human, acting as representative for a legal entity involved in transferring as asset (cargo) and/or liabilities for the asset between the two legal entities
  * _For example: picking up cargo by a transporter_

The building block ensures that the digital identity of the human involved in (digital) interactions can be :

* Authenticated
* Related to Representation evidence
  * _In what role and capacity, on behalf of which legal entity, with a specific mandate_
* Related to Professional Qualification evidence
  * _Evidence of professional qualifications_

The core concept is that identity is dynamically related to (potentially multiple concurrent) representations for (potentially multiple concurrent) legal entities: the legal entity assumes liability and accountability for actions of the human.

### Identity

Identity is a legal concept defined by a nation state and assigned to a human by that nation state. Nation States issue Passports and ID-cards to humans which they can use to "prove" their identity. Driving licenses are also used in some states (e.g. the Netherlands) to "prove" their identity.

Digital identities are related to that core identity by Identity Providers which are used in B2B processes.  &#x20;

Identity Providers can choose to increase the assurance level of an identity; for instance by live verification of an identity paper. This can be done face-to-face or remote. Typically, this is executed once at the initiation of a new identity.

### Authentication

Identity Providers can also provide additional assurance at the (continuous) use of the identity; e.g. when a managed boundary must be crossed. The human user can be authenticated by a username, password and an additional 2FA / MFA. More advanced devices can also use biometric identification parameters.

Biometric identification can also be used for accessing a physical location; e.g. using the Secure Logistics smart card to access a Terminal.

### Identifiers

Identity Providers typically use an internal numbering scheme for identifying users which are enriched with more public identifiers like email addresses and telephone numbers. State issued identifiers (like the Dutch BSN) are often not allowed to be used outside the Government.&#x20;

In B2B processes, business email addresses are preferred. These should be using an organizational domain name (e.g. @myorganization.com) and a personal prefix (e.g. piet.jansen@ or s.jones@). The use of shared email accounts must be avoided. Also the use of general domains (e.g. @gmail.com) should be avoided. Typically, the user must demonstrate during the setup of the account that she has access to the business email address. This provides additional trust that the user has a business relation with the organization which owns the domain name.

(Mobile) telephone numbers can also be used to identify / verify the user. During the setup the user demonstrates that she has access to the number. At a later moment, the user can demonstrate again that she still has access to this number.

The push for electronic Wallets provides a new means to store and show a digital identity that can be authenticated.&#x20;

### Representation

B2B Identity Providers identifies a human user in the context of an organization. Additionally, the role / mandate of the user can be defined at the Identity Provider so this can be used in all connected services. An alternative is that the service itself has local authorizations which must be managed by an administrator of the organization.

Users could represent more than one organization. Identity Providers differ how the deal with this situation. They could assign different identities for each of the represented organizations (e.g. applying different business email addresses or issuing separate secure cards per organization). Al alternative is that the human user can select the organization she represents in a specific use case.

### Professional Qualifications

In many cases the human needs to have adequate professional qualifications for the task at hand: professional drivers license, safety training, dangerous goods handling, etc.

The B2B Identity Provider could also store and share professional qualifications of the user. In a wallet this is typically stored as a verifiable credential.

### Risks

An insufficient framework for digital identity, might lead to a lower level of trust among parties and will harm the overall trust in BDI.

Non compliance to applicable privacy laws (e.g. GDPR, AVG) can hamper the implementation of services, the adoption of services, cause reputation risks or fines.

### Interlinkages with other building blocks

This building block describes the BDI principles for digital identity for H2M interactions.

The related building blocks are:

* Digital Identity H2M
* Authentication M2M
* Authentication H2M
* Authorization
* Association register
* Zero Trust Check
* Representation Register
* Professional Qualification Register

The most important related Kits and concepts are

* Trust Kit
* Federation Kit
* Boundary Management

### Core design decisions

Parties choose their Identity Providers fitting to the requirements.

The BDI adds the link to representation and professional qualifications.

In Europe the eIDAS regulation is a solid foundation for the identity ecosystem.

Self-signed certificates for digital identities are a low-barrier entry level solution, with serious limitations on trust, federation and scaling.

&#x20;
