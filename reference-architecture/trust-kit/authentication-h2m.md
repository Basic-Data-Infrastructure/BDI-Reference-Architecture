---
cover: >-
  https://images.unsplash.com/photo-1667453466805-75bbf36e8707?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxhdXRoZW50aWNhdGlvbnxlbnwwfHx8fDE3NjU0MzU4NTl8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 253
---

# Authentication H2M

## 1. Summary

Authentication is the process of proving that the user (human or IT process) with a digital identity is the rightful owner of that identity (definition from IDpro).

Authentication is required in both H2M (Human to Machine) and M2M (Machine to Machine) use cases. In this page, the focus is on H2M use cases: the human interacts with a machine by means of an IT-process under its direct control (device, IT-process, wallet etc.), or by digital data (e.g. QR code). Authentication precedes verification of Representation and subsequent Authorization.

{% hint style="warning" %}
The complexity of H2M Authentication is increased by **privacy regulations**: authenticating a human reveals their identity.
{% endhint %}

## 2. Purpose of the building block

The purpose of this building block is the following:&#x20;

* Ensure that BDI users (H2M) are recognized, identified as a person and in a specific role on behalf of a legal entity in order to prevent misuse, fraud, theft of data, services and physical goods.&#x20;
* Enable smooth, efficient and secure Boundary Management.
* Ensure that privacy leaks as a result of authentication are limited.

## 3. Concepts

The use cases relate to Boundary Management:

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td>A human, acting as representative for a legal entity desiring access to data or an application owned/controlled by another legal entity</td><td><p></p><p>For example: <em>login to an application</em></p></td><td><a href="https://images.unsplash.com/photo-1762330474120-71b4057a8b40?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxsb2dpbiUyMHNjcmVlbnxlbnwwfHx8fDE3NjU0MzYxNTh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1762330474120-71b4057a8b40?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxsb2dpbiUyMHNjcmVlbnxlbnwwfHx8fDE3NjU0MzYxNTh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td>A human, acting as representative for a legal entity desiring access to a location owned/controlled by another legal entity</td><td><p></p><p></p><p>For example: <em>entering a protected zone</em></p></td><td><a href="https://images.unsplash.com/photo-1759990251935-7483bec337ac?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxwcm90ZWN0ZWQlMjB6b25lfGVufDB8fHx8MTc2NTQzNjIzM3ww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1759990251935-7483bec337ac?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxwcm90ZWN0ZWQlMjB6b25lfGVufDB8fHx8MTc2NTQzNjIzM3ww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td>A human, acting as representative for a legal entity involved in transferring as asset (cargo) and/or liabilities for the asset between the two legal entities</td><td><em>For example: picking up cargo by a transporter</em></td><td><a href="https://images.unsplash.com/photo-1605732562742-3023a888e56e?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxjYXJnb3xlbnwwfHx8fDE3NjU0MzYyODJ8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1605732562742-3023a888e56e?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxjYXJnb3xlbnwwfHx8fDE3NjU0MzYyODJ8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

The building block ensures that the digital identity of the **human** **involved in (digital) interactions** can be authenticated. This authentication precedes verification of Representation. In the context of the BDI, the human is a representative of a **legal entity** (organization): the legal entity assumes accountability and liability for the actions of the representative, limited to the mandate of the representative. A human can have multiple roles for multiple legal entities simultaneously.

The Identity Provider chosen by the parties/Association provides the authentication. A local cache of trusted identities may be operated by an Association as a register.

Representation evidence may be stored in a register by an Association, or transmitted between parties in a nested Jason Web Token or a Verifiable Presentation of Credentials.

## 4. Core design decisions

### 4.1. OAuth2 & OpenID Connect

The BDI uses the OAuth2 protocol and OpenID Connect protocol for H2M interactions. Identities are managed by an Identity Provider (also called an OpenID Provider).

<figure><picture><source srcset="../../.gitbook/assets/251126 Maintenance_community_minor_changes_darkmode-Page-13.drawio.png" media="(prefers-color-scheme: dark)"><img src="../../.gitbook/assets/251126 Maintenance_community_minor_changes_darkmode-Page-13.drawio.png" alt=""></picture><figcaption></figcaption></figure>

The [OpenID Connect protocol](https://openid.net/developers/how-connect-works/), in abstract, follows these steps:

1. End user **navigates to a website or web application** via a browser.
2. End user **clicks sign-in** and types their username and password.
3. The RP (Client) **sends a request** to the OpenID Provider (OP).
4. The OP **authenticates the User** and obtains authorization.
5. The OP **responds with an Identity Token** and usually an **Access Token**.
6. The RP can **send a request** with the Access Token to the User device.
7. The UserInfo Endpoint **returns Claims** about the End-User.

Organization can use (1) an internal Identity Provider, (2) an exclusive external Identity Provider and (3) a mix of an internal Identity Provider and (federated) external Service Provider (see the Federation Kit).

In the BDI users are typically acting as a representative for a legal entity and not as an individual person. Therefore, the OpenID Connect UserInfo endpoint must contain a organizational identifier of the legal entity.

### 4.2. eIDAS

eIDAS is short for ‘_Electronic Identification, Authentication and Trust Services_’ and was launched to help remove digital borders between countries in the EEA. eIDAS ensures the security of digital systems and protects people’s privacy. Besides eIDAS, there are also various _national_ eID schemes. For example, in the Netherlands the national eID for persons is called DigiD and  the eID for persons representing a legal entity is called eHerkenning.&#x20;

There are strict regulations on the use of eIDAS. DigiD cannot be used for most private use cases. There are less limitations for eHerkenning. However, a very limited set of European countries have a similar B2B eID scheme.

Once a national electronic identification scheme has been recognized at European level, it can be used in other EEA countries. This is set out in the EU’s eIDAS Regulation.

### **4.3. Smart Cards / Physical Access Passes**

These can be used for access to a location and/or transferring assets.

## 5. Future Work

eIDAS2 introduces new trust services and EU Digital Identity Wallets (EDIW) for the use by citizens in both public and private domains. eIDAS2 also includes Organizational Digital Identity Wallets (ODIWs) \[[eIDAS, 2024](https://coe-dsc.nl/wp-content/uploads/2024/01/CoE-DSC-eIDAS-impact-on-data-spaces.pdf)].&#x20;

## 6. Interlinkages with other building blocks

This building block interlinks with:

<a href="digital-identity/" class="button secondary">Digital Identity</a>  <a href="authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a>  <a href="discovery.md" class="button secondary">Discovery</a>  <a href="../federation-kit/" class="button secondary">Federation KIT</a>
