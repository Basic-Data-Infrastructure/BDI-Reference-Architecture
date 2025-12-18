---
cover: >-
  https://images.unsplash.com/photo-1633848827861-c01f5142d73b?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxyb2FkJTIwYm91bmRhcnl8ZW58MHx8fHwxNzY1OTAwMjYwfDA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 354
---

# Physical Asset Boundaries

## 1. Introduction

The BDI framework includes support for the authentication of a representative (human or machine) and verification of their mandate, safeguarding the non-repudiation of the liability their principal (the entity who is represented) takes for their actions.

In the physical operation of our economy many activities are outsourced. Supplying services on-premise requires access to a guarded location. For example: a maintenance sub-contractor for a vendor of video security systems is commissioned to perform maintenance at a customer's site. The subcontractor is contracted to perform regular maintenance . At regular intervals a maintenance engineer shows up at the gate of the premises and claims access to the premises, to perform preventive maintenance on a security video system on behalf of the vendor that delivered the security system.

The security guard of the company where the security system is installed needs to verify the following:

1. Has this person indeed been sent by the OEM (original equipment manufacturer)?
2. Can this person be authenticated and verified as being mandated by the sub-contractor>
3. Does this person have the required professional qualifications?
4. Can the mandate be verified in a non-repudiable manner?

## **2. User Journey**

In the example of the engineer of the maintenance sub-contractor, the user journey starts when the engineer shows up to the gate. The security guard needs to be able to authenticate the person and verify the representation claim. The approach for this check is as follows:

{% stepper %}
{% step %}
#### Authentication

The engineer presents a form of ID (proof for authentication). The ID can be standard, fitted with additional safeguards such as biometrics, or digital (Wallet).
{% endstep %}

{% step %}
#### Representation Evidence

The engineer presents a Representation Evidence. This evidence should show:<br>

* the chain of subcontracting, up to a level that is suitable for security reasons. Note that it may be necessary to stop at an intermediate level, to protect the identity of the main principal on top of the chain from leaking
* the confirmation of the identity of the engineer, as a representative.
* time limitations on the validity of the representation (not before, not after).
* links to issuers of subcontracting orders, to validate in real-time whether the representation is still valid and not revoked.
* the non-repudiable evidence of the representation
{% endstep %}
{% endstepper %}

For real-life applications it is necessary to be able to operate (temporarily) offline. It should be possible to verify the Representation Evidence, even when validation by the issuer is delayed. Whether a delayed verification is acceptable, depends on the involved parties. This could for example be acceptable when the party checking the Representation Evidence has already received a prior notification. The data in this pre-notification can then be matched with the data in the actual evidence.

## **3. Nested JWT as carrier of claims**

The use of JSON Web Tokens (JWT, RFC 7519) is ubiquitous: the support in tools and knowhow is well developed. Expand the following elements to learn more about the different uses of JWTs.

<details>

<summary>JWTs for claim sets</summary>

A JWT is a compact, URL-safe way to represent **claim sets** which are to be transferred between two parties. A claim set is a set of **claims**, where each claim is a piece of information asserted about a subject. A claim is represented as a name/value pair consisting of a claim name (always a string) and a claim value (can be any JSON value).

</details>

<details>

<summary>Unsecured JWTs</summary>

**Unsecured JWTs** are standardized claim sets. However, many if not most JWTs need to be signed and encrypted. The claim set in a JWT can be used as the payload of a JSON Web Signature (JWS, RFC 7515) structure or as the plaintext of a JSON Web Encryption (JWE, RFC 7516) structure, enabling the claims to be digitally signed or integrity protected with a Message Authentication Code (MAC) and/or encrypted.

</details>

<details>

<summary>Nested JWTs</summary>

The result nesting of a JWT in a JWS or in a JWE (or both!) is called a _Nested JWT_. (Note that this is a _different kind of nesting than the nesting/embedding_ of representation evidences that are the topic of this note). The resulting JSON object is encoded using a Base64URL encoding, which produces a URL-safe plain ASCII string.

</details>

<details>

<summary>Embedded JWTs</summary>

Because JWTs are in the end just ASCII strings, they can be used as the value of a claim in another JWT. This kind of nesting can be referred to as **embedded JWTs**. This feature is the basis for representation hierarchies, where a representation is based on another representation.

A [draft JWT specification](https://datatracker.ietf.org/doc/draft-ietf-oauth-selective-disclosure-jwt/) defines how to implement selective disclosure of information. Selective disclosure would be a excellent feature in business environments.

</details>

### **3.1 JWT types of claims**

There are two types of JWT claims:

1. **Registered**: standard claims registered with the [Internet Assigned Numbers Authority (IANA)](https://www.iana.org/assignments/jwt/jwt.xhtml) and defined by the [JWT specification](https://tools.ietf.org/html/rfc7519) to ensure interoperability with third-party, or external, applications.
2. **Custom**: non-registered public or private claims. Public claims are collision-resistant while private claims are subject to possible collisions.

The [IANA "JSON Web Token Claims" registry](https://www.iana.org/assignments/jwt/jwt.xhtml#claims) lists the registered claims. [Verifiable Credentials](https://www.w3.org/TR/vc-data-model-2.0/) (Claim Name “vc”) and Verifiable Presentations (Claim Name “vp”) are registered claims. The use of nested JWTs supports the future use of VC’s and VP’s. The JWT structure makes it therefore possible to include claims of Professional Qualifications.

### **3.2 Using JWT's as carrier of Representation claims**

The most simple approach is that the Principal issues the JWT. The payload of the JWT is:

* identity information of the human (ID #, name, digital identity etc.)
* identity information of the Principal
* order information (order reference, type of activity, location, data)
* additional information (time limits, specific instructions, link to issuer)

The issuer of the JWT (Principal) can add a link to the payload. The link allows for a real-time confirmation that the claims in the JWT are still valid.

When the Principal commissions a subcontractor, the identity of the human is replaced by the identity of the subcontractor. The subcontractor creates a new JWT, with the payload:

* the JWT as sent by the Principal
* identity information of the human (ID #, name, digital identity etc.)
* identity information of the Subcontractor)
* order information (subcontractor order reference, type of activity, location, data)
* additional information (time limits, specific instructions, link to issuer)

## **4. Application in practice**

An embedded JWT claim can be created recursively by each layer of the (subcontracting) chain, starting with a Principal. This show the Representation chain.

The human requesting access can carry the JWT (for instance in a Wallet), or carry a link to an online API that can transfer the JWT to an evaluation service/application. The security guards use the service or application to evaluate the JWT, verify the signing of its claims and show the content to the guard. The guard can authenticate the human and verify the representation chain.

## **5. Further reading**

[https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf](https://bdinetwork.org/wp-content/uploads/2024/05/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf)
