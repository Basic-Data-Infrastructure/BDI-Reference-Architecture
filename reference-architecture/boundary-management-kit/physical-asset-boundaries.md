# Physical Asset Boundaries

The BDI framework includes support for the authentication of a representative (human or machine) and verification of their mandate,  safeguarding the non-repudiation of the liability their principal ( the entity who is represented) takes for their actions.

In the physical operation of our economy many activities are outsourced. Supplying services on-premise reauires access to a guarded location. For example: a maintenance sub-contractor for a vendor of video security systems is commissioned to perform maintenance at a customer's site. The subcontractor is contracted to perform regular maintenance . At regular intervals a maintenance engineer shows up at the gate of the premises and claims access to the premises,  to perform preventive maintenance on a security video system on behalf of the vendor that delivered the security system.

The security guard of the company where the security system is installed needs to verify: has he/she indeed been sent by the OEM? And can he/she indeed be authenticated and verified as being mandated by the sub-contractor, and does he/she have the required professional qualifications? And can that mandate be verified in a non-repudiable manner?

**User Journey**

In the example of the engineer of the maintenance sub-contractor, the user journey starts when the engineer shows up to the gate. The security guard needs to be able to authenticate the person and verify the representation claim.

The approach is that the engineer presents an ID (proof for authentication) and a Representation Evidence.

The ID can be standard, fitted with additional safeguards such as biometrics, or digital (Wallet).

The Representation Evidence should be able to show:

\-          The chain of subcontracting, up to a level that is suitable for security reasons

&#x20;It may be necessary to stop at an intermediate level, to protect the identity of the main principal on top of the chain from leaking

\-          The confirmation of the identity of the engineer, as a representative

\-          Time limitations on the validity of the representation (not before, not after)

\-          Links to issuers of subcontracting orders, to validate real-time is the representation is still valid and not revoked

\-          The non-repudiable evidence of the representation

For real-life applications it is necessary to be able to operate (temporarily) offline: the check of the Representation Evidence with delayed  validation at the issuers should be possible. If a delayed verification is acceptable is up to the parties involved: in many cases this might be acceptable, for instance if a pre-notification is done to the party that is checking the Representation Evidence. The pre-notification data can be matched with the data in de Evidence.

**Nested JWT as carrier of claims**

JSON Web Token (JWT, RFC 7519) is a compact, URL-safe means of representing _claim sets_ to be transferred between two parties.  A claim set is just a set of _claims_, where each claim is a piece of information asserted about a subject.  A claim is represented as a name/value pair consisting of a claim name (always a string) and a claim value (can be any JSON value).

The use of JWT is ubiquitous: the support in tools and knowhow is well developed.

_Unsecured_ JWTs are just standardized claim sets. However, many if not most JWTs need to be signed and encrypted. The claim set in a JWT can be used as the payload of a JSON Web Signature (JWS, RFC 7515) structure or as the plaintext of a JSON Web Encryption (JWE, RFC 7516) structure, enabling the claims to be digitally signed or integrity protected with a Message Authentication Code (MAC) and/or encrypted.

&#x20;The result nesting of a JWT in a JWS or in a JWE (or both!) is called a _Nested JWT_. (Note that this is a _different kind of nesting than the nesting/embedding_ of representation evidences that are the topic of this note). The resulting JSON object is encoded using a Base64URL encoding, which produces a URL-safe plain ASCII string.

Because JWTs are in the end just ASCII strings, they can be used as the value of a claim in another JWT. We will designate this kind of nesting as _embedded_ JWTs. This feature is the basis for representation hierarchies, where a representation is based on another representation.

A draft JWT specification [https://datatracker.ietf.org/doc/draft-ietf-oauth-selective-disclosure-jwt/](https://datatracker.ietf.org/doc/draft-ietf-oauth-selective-disclosure-jwt/) defines how to implement selective disclosure of information. Selective disclosure would be a excellent feature in business environments.

**JWT claims**

There are two types of JWT claims:

·         Registered: standard claims registered with the [Internet Assigned Numbers Authority (IANA)](https://www.iana.org/assignments/jwt/jwt.xhtml) and defined by the [JWT specification](https://tools.ietf.org/html/rfc7519) to ensure interoperability with third-party, or external, applications.

·         Custom:  consists of non-registered public or private claims. Public claims are collision-resistant while private claims are subject to possible collisions

The  IANA "JSON Web Token Claims" registry [https://www.iana.org/assignments/jwt/jwt.xhtml#claims](https://www.iana.org/assignments/jwt/jwt.xhtml#claims) lists the registered claims.

Verifiable Credentials [https://www.w3.org/TR/vc-data-model-2.0/](https://www.w3.org/TR/vc-data-model-2.0/)  (Claim Name “vc”) and Verifiable Presentations (Claim Name “vp”) are registered claims.

The use of nested JWTs supports the future use of VC’s and VP’s.

The JWT structure makes it therefore possible to include claims of Professional Qualifications.

**Application in practice**

An embedded JWT claim can be created recursively by each layer of the (subcontracting) chain, starting with a Principal. The human requesting access can carry the JWT  (for instance in a Wallet), or a link to an online API that can transfer the JWT. The security guards can use a service to evaluate the JWT and its claims.
