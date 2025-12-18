---
cover: >-
  https://images.unsplash.com/photo-1618044619888-009e412ff12a?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxhdXRoZW50aWNhdGlvbnxlbnwwfHx8fDE3NjU4OTg1NDl8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 286
---

# Authentication M2M

## 1. Summary

Authentication is the process of proving that the user (human or IT process) with a digital identity who is requesting access is the rightful owner of that identity (definition from IDpro). In the context of the BDI, the user is a representative of a legal entity (organization).

Authentication is required in both H2M (Human to Machine) and M2M (Machine to Machine) use cases.

In this page we will focus on M2M use cases where data is requested by a Data Consumer (e.g. another organization) via an API.

## 2. Purpose of the building block

{% hint style="info" %}
Ensure that BDI users (M2M) are recognized and identified to prevent misuse of services and data. The automatic authentication of a BDI user in a federated perimeter-less architecture (see DNS-based Discovery as option) relies on a (delegated) Trust Anchor for Identity.
{% endhint %}

## 3. Concepts

The Data Service Provider is responsible for authenticating the user; this is prerequisite for authorization, which will determine if the user can access the requested data.

## 4. Risks

Incorrect authentication could result in data breaches and / or the unavailability to data for legitimate data consumers.

## 5. Interlinkages with other building blocks

<a href="digital-identity/" class="button secondary">Digital Identity</a>  <a href="authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a>  <a href="discovery.md" class="button secondary">Discovery</a>  <a href="../federation-kit/" class="button secondary">Federation KIT</a>

## 6. Core design decisions

### 6.1. OAuth2

The BDI uses the OAuth2 protocol. OAuth2 supports two types of client credentials for authentication:

* Shared secrets
* Private keys (certificates).

The use of private keys is preferred within the BDI.

A BDI association could decide to issue certificates itself as an association, or as a group of associations. The consequence is that the Association is its own Trust Anchor, making federation with other Associations harder or less trustworthy.

### 6.2. eIDAS

The European eIDAS regulation is a trust framework which (also) governs the issuance of certificates within Europe. Certificates can be used for:

* Mutual TLS - Qualified Web Application Certificate (QWAC)
* Digital Sealing of the message - Qualified Seal (QSEAL)

QWAC and QSEAL are different types of eIDAS certificates.The sealing provides the legal binding of the exchanged data.

The use of eIDAS digital certificates as private keys is recommended. The recommendation is to use eIDAS QWACs as well.

### 6.3. Non-European trust anchors

The eIDAS regulation and infrastructure is EU-specific. Outside of Europe other trust anchors could be used (to be investigated).

### 6.4. Drawbacks of certificates

* Certificates are quite expensive
* Certificates need frequently to be rotated
* The procurement, setup, testing and acceptance of certificates is not trivial.

### 6.5. Certificate based authentication

Guidance on (to be done):

* Mapping certificates to identifiers (within the association)
* Mapping to a well known identifier within the Data Service Provider
* Note on Mutual Authentication; also relevant for the Data Consumer

## 7. Future topics

1. Non-EU trust anchors (outside of eIDAS).
2. The use of association issued certificates instead of eIDAS certificates
3. Alignment with DSSC. The DSSC Blueprint v1.0 is referring to “Identity and Attestation Management” which is based of verifiable credentials, DID’s and OpenID for verifiable credentials. These has been defined out of scope for the current release of DIL / BDI.
4. Alignment with IDSA. To be defined.
5. The use of (other) PKI schemes.
6. The use of Decentral Identifiers.
7. Federated Authentication through [OAuth 2.0 Attestation-Based Client Authentication](https://datatracker.ietf.org/doc/draft-ietf-oauth-attestation-based-client-auth/03/)

In the BDI network, a [reputation system](../federation-kit/business-partner-reputation-model.md) within a BDI Association is integral for assessing the trustworthiness of visitors or outsiders: members of another BDI Association. While the BDI facilitates digital communication among a network of BDI Associations, establishing trust within a BDI Association through mutual agreements is relatively straightforward. However, evaluating the trustworthiness of participants in other BDI Associations can pose a challenge.

A federation trust is designed to enable efficient and secure online transactions between business partners. Trust to engage between parties is most often based on more attestations agreed between parties and/or assocation they are member of. The service provider can then make [authorization ](../../readme/technology/broken-reference/)decisions based on te information on behalf of the data owner.

When a requests from a member of association A is directed to access data of a member of association B the request is redirected to the association's B attestation service to validate the federated trust artifacts available with the requestor association. These attestations help decide the authentication response of the data provider and authorization conditions applied on behalf the data owner. Note: Emphasizing '_helps decide_' as the Trust Sovereignty principle is kept by allowing the assessment against the policies of the data owner to determine authorization. The owner might want to provide the data service as requested even if the Identity does not provide all the required attestations or limit the authorization provided by the assessment policies of the presented attestations.

The concept for the [association ](../federation-kit/federation-of-associations.md)is to adopt the framework standards with it's members to achieve a goal (benefits outweigh the costs). Add local specifics, ratify common standards across associations, evolve and so on.

Above options could be combined; e.g. [https://dhs-svip.github.io/requirements-for-decentralized-identity/TrustArchitecture/](https://dhs-svip.github.io/requirements-for-decentralized-identity/TrustArchitecture/).

## 8. Further reading

OAuth2: [IETF RFC 6749](https://datatracker.ietf.org/doc/html/rfc6749)

OAuth 2.0 Mutual-TLS: [IETF RFC 8705](https://datatracker.ietf.org/doc/html/rfc8705)

iSHARE: [Authentication](https://dev.ishare.eu/reference/authentication)
