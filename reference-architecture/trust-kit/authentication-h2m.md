# Authentication H2M

### 1. Summary&#x20;

Authentication is the process of proving that the user (human or IT process) with a digital identity is the rightful owner of that identity (definition from IDpro).

Authentication is required in both H2M (Human to Machine) and M2M (Machine to Machine) use cases. In this page  we focus on H2M use cases: the human interacts with a machine by means of an IT-process under its direct control (device, IT-process, wallet etc.), or by digital data (e.g. QR code). Authentication precedes verification of Representation and subsequent Authorization.

The complexity of H2M authentication is increased by privacy regulations: authenticating a human reveals his/hers identity.

### 2. Purpose of the building block&#x20;

{% hint style="info" %}
Ensure that BDI users (H2M) are recognized,  identified  as a person and in a specific role on behalf of a legal entity: to prevent misuse, fraud, theft of data, services and physical goods. Enable smooth,  efficient and secure Boundary Management.

Ensure that privacy leaks as a result of authentication are limited.
{% endhint %}

### 3. Concepts&#x20;

The use cases relate to Boundary Management:

* A human, acting as representative for a legal entity desiring access to data or an application owned/controlled by another legal entity
  * For example: login to an application
* A human, acting as representative for a legal entity desiring access to a location owned/controlled by another legal entity
  * For example: entering a protected zone
* A human, acting as representative for a legal entity involved in transferring as asset (cargo) and/or liabilities for the asset between the two legal entities
  * For example: picking up cargo by a transporter

The building block ensures that the digital identity of the human involved in (digital) interactions can be  authenticated: authentication precedes verification of Representation. In the context of the BDI, the human is a representative of a legal entity  (organization): the legal entity assumes accountability and liability for the actions of the representative, limited to the mandate of the representative. A human can have multiple roles for multiple legal entities simultaneously.

The Identity Provider chosen by the parties/Association provides authentication. A local cache of trusted identities may be operated by an Association as a register.

Representation evidence may be stored in a register by an Association, or transmitted between parties in a nested Jason Web Token or a Verifiable Presentation of Credentials.

### 4. Core design decisions&#x20;

#### 4.1. OAuth2 & OpenID Connect

The BDI uses the OAuth2 protocol and OpenID Connect protocol for H2M interactions. Identities are managed by an Identity Provider (also called an OpenID Provider).&#x20;

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

The OpenID Connect protocol, in abstract, follows these steps:

1. End user **navigates to a website or web application** via a browser.
2. End user **clicks sign-in** and types their username and password.
3. The RP (Client) **sends a request** to the OpenID Provider (OP).
4. The OP **authenticates the User** and obtains authorization.
5. The OP **responds with an Identity Token** and usually an **Access Token**.
6. The RP can **send a request** with the Access Token to the User device.
7. The UserInfo Endpoint **returns Claims** about the End-User.

Source: [https://openid.net/developers/how-connect-works/](https://openid.net/developers/how-connect-works/)

Organization can use (a) an internal Identity Provider (b) an exclusive external Identity Provider (c) a mix of an internal Identity Provider and (federated) external Service Provider (see the Federation Kit).

In the BDI users are typically acting as a representative for a legal entity and not as an individual person. Therefore, the OpenID Connect userinfo endpoint must contain a organizational identifier of the legal entity.

#### 4.2. eIDAS

eIDAS is short for ‘Electronic Identification, Authentication and Trust Services’. eIDAS was launched to help remove digital borders between countries in the EEA, while ensuring the security of digital systems and protecting people’s privacy.

There are various national eID schemes. In the Netherlands the national eID for persons is called DigiD and eHerkenning is used for persons representing a legal entity.

There are strict regulations on the use of eDIAS. DigiD can't be used for most private use cases. There are less limitations for eHerkenning however a very limited set of European countries have a similar B2B eID scheme.

Once a national electronic identification scheme has been recognised at European level, it can be used in other EEA countries. This is set out in the EU’s eIDAS Regulation.&#x20;

**4.3. Smart Cards / Pyhisical Access Passes**

These can be used for access to a location and/or transferring assets.&#x20;

### 5. Future Work

eIDAS2 introduces new trust services and EU Digital Identity Wallets (EDIW) for the use by citizens in both public and private domains. eIDAS2 also includes Organisational Digital Identity Wallets (ODIWs).

Source: [https://coe-dsc.nl/wp-content/uploads/2024/01/CoE-DSC-eIDAS-impact-on-data-spaces.pdf](https://coe-dsc.nl/wp-content/uploads/2024/01/CoE-DSC-eIDAS-impact-on-data-spaces.pdf)

### 6. Interlinkages with other building blocks&#x20;

This building block interlinks with:

* Digital Identity & Identifiers
* Authorizations
* Discovery
* Federation



