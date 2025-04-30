# Representation Chain

#### Summary

The **Representation Chain** is a  building block in the BDI framework. It enables third parties to **verify representation mandates** — confirming whether a person, legal entity, or automated process is genuinely acting on behalf of another.

A **mandate** is a formal, authoritative assignment of responsibility from a **mandator** (the assigning party) to a **mandatee** (the acting party). It transfers **accountability and liability** for actions from the mandatee back to the mandator.

To function securely and flexibly across different contexts, the Representation Chain uses **Representation Evidence** — typically implemented using **nested JSON Web Tokens (JWTs)**. These can be verified both **online** (e.g., via issuer services) and **offline** (e.g., on a warehouse floor via a QR scan).

#### Introduction

In today’s increasingly interconnected and regulated economy, businesses and authorities are facing a growing need for robust digital proof in everyday interactions. Whether it’s verifying that a subcontractor is authorized to collect a shipment, confirming a driver’s professional qualification, or demonstrating compliance with regulations during an inspection, organizations must often rely on people or systems that act on their behalf. In most cases, liability for these actions lies with the organization, not the individual. This creates a pressing demand for a mechanism that can reliably prove — both legally and practically — that the person or machine performing a task has been officially mandated to do so.

Traditional methods such as paper documents or verbal confirmations are no longer sufficient. A modern solution must be secure, flexible, scalable, and usable in low-tech environments by people with little IT training. It must also support dynamic staffing models and allow independent IT providers to build competitive solutions without vendor lock-in. The JSON Web Token (JWT) standard, originally designed for secure information exchange between systems, offers a strong foundation for such a solution. Its format allows for verifiable digital claims, time-bound validity, cryptographic integrity, and issuer authentication — all critical features for establishing trust in operational contexts.

What makes JWT particularly valuable in this setting is its ability to be embedded within other tokens. This “nesting” allows multiple layers of representation to be encapsulated in a single digital envelope — from a principal organization, through subcontractors, down to the individual or system actually performing the task. Combined with high-trust digital certificates like eIDAS, JWT-based evidence can meet the highest legal standards for electronic signatures while still being compact enough for mobile use.

The approach supports both high-security and user-friendly versions. For example, a delivery driver might receive a QR code and PIN via text, which they present at a loading dock. The system verifies their credentials — offline if necessary — with minimal friction. This combination of simplicity and cryptographic strength makes JWT-based representation not only viable but ideal for logistics, compliance, and other sectors where verifiable delegation and operational practicality must coexist.

**Purpose**

The Representation Chain supports both:

* **Human-to-Machine (H2M)** and **Machine-to-Machine (M2M)** delegation, and
* Real-time **human access or authority validation**, such as in logistics, compliance inspections, or cargo handovers.

It is crucial in:

* [Physical Asset Boundary Management](https://app.gitbook.com/o/6jFQJqnMRyd4T2pZ1IBi/s/EsnYrgeqsPPZtbALTQAj/~/changes/224/reference-architecture/boundary-management/physical-asset-boundaries)
* [Legal Asset Boundary Management](https://app.gitbook.com/o/6jFQJqnMRyd4T2pZ1IBi/s/EsnYrgeqsPPZtbALTQAj/~/changes/224/reference-architecture/boundary-management/legal-asset-boundaries)

It provides a **verifiable, decentralised mechanism** for confirming:

* Who gave the mandate
* To whom
* For what role or task
* For what duration
* With what professional qualifications (if applicable)

#### Relationship to Other Building Blocks

The Representation Chain is conceptually and operationally connected to:

* **Authentication**
* **Authorisation**
* **Digital Identity**
* **Common Roles**
* **Professional Qualification Chain**
* **Verifiable Credentials** (future support via `vc` and `vp` claims)

#### Elements & Core Functions

A Representation Chain maintains:

* The **digital identity of the mandator**
* The **digital identity of the mandatee**
* The **scope** of the mandate (role-based, order-based, or otherwise contextual)
* **Timestamps** (not-before, not-after)
* **Professional qualifications**
* Optional **links to issuers** for revocation or validation

The **Representation Evidence** is typically a nested JWT structure, passed to the mandatee. This token is then presented to a verifying party — such as a loading dock, customs authority, or inspection officer.

The verifier checks the signature chain, timestamps, and optionally contacts the issuer(s) to confirm current validity.

**The third party verifier does not need to be a member of a BDI Association**, which lowers the barrier for wide-scale adoption and integration.

***

### Business Need for Digital Representation

There is an increasing demand in business transactions for **digital proof of authority**, particularly in interactions between:

* Individual companies
* Companies and supervisory/government bodies

The most common scenarios include:

* **Proof of representation** (someone acts on behalf of an organisation)
* **Transfer of cargo** (pickup or delivery confirmation)
* **Proof of qualifications** (such as handling dangerous goods)
* **Proof of compliance** (laws and regulations)

People or systems acting on behalf of others must carry digital proof of their mandate. Traditional methods — paper slips, phone calls, or emails — are not scalable, secure, or auditable.

To meet modern requirements, we need a solution that is:

* Legally and practically robust
* Easy to use in varied operational environments
* Broadly applicable across sectors
* Open for implementation by multiple IT providers

***

### JWT as a Representation Mechanism

After 2010, JSON Web Tokens ([RFC 7519](https://datatracker.ietf.org/doc/html/rfc7519)) became a widely adopted standard for representing verifiable claims digitally.

Each JWT contains:

* A **payload** with the actual claims (who, what, when, for whom)
* A **hash** to confirm that the payload hasn’t been tampered with
* A **digital signature** by the issuing party (e.g., via eIDAS or trusted cert)

#### Nested JWTs: The Representation Chain in Action

JWTs support **wrapping (embedding)**, meaning one JWT can include another inside its payload. This enables building **multi-level chains of delegation** — for example:

There’s no formal limit to the number of layers. For legal-grade use (e.g., cross-border logistics or compliance), JWTs can be signed with **high-quality certificates** such as **eIDAS** seals.



For many real-world situations, **usability** is more critical than military-grade security. Inspired by DigiD and “Tikkie”, a lightweight version of the solution has been developed using just:

* A smartphone
* A QR code
* A PIN code

The complexity is handled behind the scenes by IT systems.

***

### Real-World Example: Chemical Pickup Using JWTs

This practical case illustrates the Representation Chain mechanism in logistics.

#### Scenario

1. **Acne Inc.** sells hydrofluoric acid and arranges pickup at Lets-B-Chemical.
2. **Van Gend & Loos** is contracted to transport the goods.
3. Van Gend subcontracts **De Snelle Visser**.
4. **Dolly Driver**, an employee of De Snelle Visser, arrives to collect the cargo.

Dolly must prove:

* Her authority (representation chain: Acne → Van Gend → Snelle Visser → Dolly)
* Her identity
* Her qualifications (e.g., ADR certification)

She presents a **JWT** on her phone, embedded with:

* Her employer’s signature
* Her personal info
* The upstream delegation tokens
* Her qualifications

The warehouse employee scans a **QR code**, verifies the JWT chain, checks her ID, and confirms the transfer.

#### Key Elements Verified

* Signature validity and token freshness (`nbf`, `exp`)
* Embedded delegation from all upstream parties
* Dolly’s ID matches the `sub` claim
* ADR qualifications included or linked
* Revocation status (optional online check)

***

### DigiDrop

BDI’s method accounts for **non-ideal environments** — e.g., no internet, broken devices, or limited IT skills. For this, the DigiDrop way of working can give viable alternatives.

{% embed url="https://github.com/Topsector-Logistiek/Digidrop" %}

#### High leven overview of DigiDrop fallback:

#### QR Code + PIN Workflow

* The driver receives a **QR code** and **PIN** via WhatsApp or SMS
* The warehouse scans the QR code using the DigiDrop app
* The driver verbally gives the PIN to authorize data viewing
* DigiDrop verifies the signature chain and displays details
* The warehouse confirms and releases the goods

This process:

* Works offline
* Prevents showing data without consent (PIN as consent barrier)
* Adds traceability

#### Short URL Fallback

If QR scanning fails:

* A short link is provided to the warehouse via text
* They can type this into a browser
* The PIN unlocks the relevant information
* Even if IT systems are temporarily down, the process continues via paper/PIN

#### No DigiDrop Provider Scenario

If a warehouse does not use DigiDrop:

* The driver presents the URL and PIN
* A trusted backend (e.g., TMSX) provides a basic web interface
* Security is reduced, but functionality is preserved

***

### Common Claims in BDI JWTs

#### Registered Claims

| Claim         | Description                           |
| ------------- | ------------------------------------- |
| `iss`         | Issuer (e.g., `_bdi.acme.com`)        |
| `sub`         | Subject of the JWT                    |
| `aud`         | Intended audience                     |
| `nbf` / `exp` | Validity timeframe                    |
| `iat`         | Issued-at timestamp                   |
| `jti`         | Unique identifier for revocation      |
| `vc` / `vp`   | Verifiable Credential or Presentation |

#### BDI-Specific Claims

| Claim  | Purpose                      |
| ------ | ---------------------------- |
| `fl`   | Freightbill reference        |
| `efti` | eFTI/eCMR integration link   |
| `ipa`  | Originating IP (IT security) |

***

### Summary

The **Representation Chain** provides a flexible, secure, and verifiable method for proving authority in business interactions — whether digital or physical. Its implementation via **JWTs** is:

* Scalable
* Legally robust
* Compatible with low-tech environments
* Designed for both machines and people

Combined with **fallback workflows** and **hybrid adoption pathways**, this method is ready for real-world logistics, compliance, and digital service chains.

***

### Learn More

* [RFC 7519 – JSON Web Token (JWT)](https://datatracker.ietf.org/doc/html/rfc7519)
* [BDI Representation Register](https://bdinetwork.org/framework/representation/)
* [VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/)
* BDI Edge Agreements
* [IANA JWT Claim Registry](https://www.iana.org/assignments/jwt/jwt.xhtml)



**Documents**



{% file src="../../.gitbook/assets/20241128_BDI-JSON-Web-Token-as-generic-proof.pdf" %}

{% file src="../../.gitbook/assets/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf" %}





