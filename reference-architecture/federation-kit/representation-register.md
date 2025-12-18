---
cover: >-
  https://images.unsplash.com/photo-1498050108023-c5249f4df085?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxsYXB0b3AlMjBjb2RlfGVufDB8fHx8MTc2NTQ2Mzk5MXww&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 345
---

# Representation Chain

## 1. Summary

The **Representation Chain** is a building block in the BDI framework. It enables third parties to **verify representation mandates** — confirming whether a person, legal entity, or automated process is genuinely acting on behalf of another.

A **mandate** is a formal, authoritative assignment of responsibility from a **mandator** (the assigning party) to a **mandatee** (the acting party). It transfers **accountability and liability** for actions from the mandatee back to the mandator.

To function securely and flexibly across different contexts, the Representation Chain uses **Representation Evidence** — typically implemented using **nested JSON Web Tokens (JWTs)**. These can be verified both **online** (e.g., via issuer services) and **offline** (e.g., on a warehouse floor via a QR scan).

## 2. Introduction

In today’s increasingly interconnected and regulated economy, businesses and authorities are facing a growing need for robust digital proof in everyday interactions. Whether it’s verifying that a subcontractor is authorized to collect a shipment, confirming a driver’s professional qualification, or demonstrating compliance with regulations during an inspection, organizations must often rely on people or systems that act on their behalf. In most cases, liability for these actions lies with the organization, not the individual. This creates a pressing demand for a mechanism that can reliably prove — both legally and practically — that the person or machine performing a task has been officially mandated to do so.

Traditional methods such as paper documents or verbal confirmations are no longer sufficient. A modern solution must be secure, flexible, scalable, and usable in low-tech environments by people with little IT training. It must also support dynamic staffing models and allow independent IT providers to build competitive solutions without vendor lock-in. The JSON Web Token (JWT) standard, originally designed for secure information exchange between systems, offers a strong foundation for such a solution. Its format allows for verifiable digital claims, time-bound validity, cryptographic integrity, and issuer authentication — all critical features for establishing trust in operational contexts.

What makes JWT particularly valuable in this setting is its ability to be embedded within other tokens. This “nesting” allows multiple layers of representation to be encapsulated in a single digital envelope — from a principal organization, through subcontractors, down to the individual or system actually performing the task. Combined with high-trust digital certificates like eIDAS, JWT-based evidence can meet the highest legal standards for electronic signatures while still being compact enough for mobile use.

The approach supports both high-security and user-friendly versions. For example, a delivery driver might receive a QR code and PIN via text, which they present at a loading dock. The system verifies their credentials — offline if necessary — with minimal friction. This combination of simplicity and cryptographic strength makes JWT-based representation not only viable but ideal for logistics, compliance, and other sectors where verifiable delegation and operational practicality must coexist.

## **3. Purpose of the building block**

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

## 4. Interactions with other building blocks

The Representation Chain is conceptually and operationally connected to:

<a href="../trust-kit/authentication/" class="button secondary">Authentication</a> <a href="../trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a> <a href="../trust-kit/digital-identity/" class="button secondary">Digital Identity</a>

<a href="professional-qualification-register.md" class="button secondary">Professional Qualification Chain</a> <a href="../verifiable-credentials-kit/verifiable-credentials.md" class="button secondary">Verifiable Credentials</a>

## 5. Elements & Core Functions

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

## 6. Business Need for Digital Representation

Supporting business interactions digitally, requires **digital proof of authority**, particularly in interactions between:

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

## 7. JWT as a Representation Mechanism

After 2010, JSON Web Tokens ([RFC 7519](https://datatracker.ietf.org/doc/html/rfc7519)) became a widely adopted standard for representing verifiable claims digitally.

Each JWT contains:

* A **payload** with the actual claims (who, what, when, for whom)
* A **hash** to confirm that the payload hasn’t been tampered with
* A **digital signature** by the issuing party (e.g., via eIDAS or trusted cert)

#### Nested JWTs: The Representation Chain in Action

JWTs support **wrapping (embedding)**, meaning one JWT can include another inside its payload. This enables building **multi-level chains of delegation** — for example:

There’s no formal limit to the number of layers. For legal-grade use (e.g., cross-border logistics or compliance), JWTs can be signed with **high-quality certificates** such as **eIDAS** seals.

***

### Example: Machine-to-Machine Access to Sensitive Operational Data

This example demonstrates how a chain of representation and delegation is managed digitally when data, is the asset being accessed — and when systems, not people, are the ones performing the action.

#### Scenario: Delegated Data Access via a Subcontractor System

A company called **SmartWater Solutions** manages water quality sensors across industrial facilities. A major client, **ChemCo Industries**, contracts SmartWater to monitor chemical runoff levels at their facilities. However, SmartWater does not have a data analysis platform robust enough for ChemCo's specific requirements. To meet the SLA, SmartWater subcontracts **DeepSignal Analytics**, a specialized AI firm, to process and analyze the raw data streams.

Now, DeepSignal’s automated system (an API client) must retrieve sensitive sensor data from **ChemCo’s secure telemetry endpoint**. However, ChemCo’s API is configured to only accept requests from authorized systems — specifically those acting on behalf of contractual parties.

To make this delegation verifiable and non-repudiable, SmartWater issues a **Representation JWT** to DeepSignal. This token proves that DeepSignal has been delegated the right to act on SmartWater’s behalf. It includes an embedded JWT from ChemCo to SmartWater, establishing the upstream mandate.

#### JWT Chain Construction (M2M)

1. **ChemCo Industries** issues a JWT authorizing **SmartWater Solutions** to retrieve and process sensor data on its behalf. The token includes:
   * Scope (sensor IDs, data types)
   * Validity window (`nbf`, `exp`)
   * A `jti` (token ID) for revocation checks
2. **SmartWater Solutions** issues a second JWT to **DeepSignal Analytics**, embedding the ChemCo JWT. It contains:
   * DeepSignal’s system identifier (API client ID or server public key reference)
   * Constraints on data types, endpoints, or frequency
   * A clear mandate scope (e.g. "read-only access to zone A sensor logs")

The JWT is cryptographically signed by SmartWater and includes ChemCo’s original JWT inside its payload.

#### Machine Request and Verification

When DeepSignal’s system sends a request to ChemCo’s API, it attaches the nested JWT as its **digital proof of mandate**. ChemCo’s API performs the following checks:

* Validates both signatures (SmartWater and ChemCo)
* Verifies token expiry and start time
* Confirms that DeepSignal's system is the intended subject
* Parses the embedded JWT from ChemCo to SmartWater to confirm original authority
* Optionally, looks up the token's `jti` in ChemCo’s revocation list or representation register

If all checks succeed, the API grants access and returns the requested sensor data.

This JWT-based method ensures that:

* **SmartWater retains liability** for DeepSignal’s actions
* **DeepSignal cannot misuse or forward the token**, as the claims are specific and signed
* ChemCo has an **audit trail** of who requested what data and on whose authority
* Delegation can be revoked or changed with minimal friction

***

### Example: Transporting Hazardous Materials Using JWT Representation Evidence

This example illustrates how a chain of representation is securely and digitally established using embedded JWTs in a real-world logistics setting.

#### Scenario: Chemical Pickup by a Subcontracted Driver

A large industrial buyer has purchased hydrofluoric acid and the supplier — **Acne Inc.** — arranges for the pickup to occur at **Lets-B-Chemical**. However, Acne does not have its own transport capacity and therefore contracts the trusted logistics firm **Van Gend & Loos** to execute the pickup and delivery.

Van Gend & Loos does not have a truck available on the required date. Instead, it chooses to subcontract the pickup task to **De Snelle Visser**, a regional carrier already scheduled to pass by Lets-B-Chemical. **Dolly Driver**, an employee of De Snelle Visser, is tasked with executing the collection.

Now Dolly must be able to prove the following:

* That she has a valid, authorized assignment from her employer De Snelle Visser.
* That De Snelle Visser was subcontracted by Van Gend & Loos.
* That Van Gend & Loos was originally contracted by Acne Inc.
* That she holds the correct qualifications to handle hazardous goods.

At the pickup location, Lets-B-Chemical needs to verify her mandate and qualifications **before releasing the acid**. This must be done quickly, securely, and ideally without needing complex systems or manual calls. To enable this, a **chain of JWTs** is created and passed down from Acne Inc. to Dolly Driver.

#### JWT Chain Construction

1. **Acne Inc.** issues a signed JWT that authorizes **Van Gend & Loos** to collect the hydrofluoric acid.
2. **Van Gend & Loos** issues a JWT to **De Snelle Visser**, embedding Acne's original JWT inside. This proves that Van Gend had authority to subcontract and passes the responsibility trace.
3. **De Snelle Visser** creates a JWT embedding both upstream tokens and includes Dolly's:
   * Identity details
   * Employment role
   * ADR (dangerous goods) certification
   * Device-specific metadata (e.g. IP address, vehicle license)

#### Field Presentation and Validation

Dolly arrives at Lets-B-Chemical and presents a **QR code** on her mobile phone. This QR code contains the fully nested JWT. The security officer scans it using a standard or BDI-enabled app.

The system:

* Verifies the cryptographic signature chain
* Checks timestamps (validity, expiry, issuance)
* Confirms Dolly’s identity and employer
* Detects ADR certification
* Optionally contacts the issuer (e.g., Acne or Van Gend) to verify token revocation status

If all criteria are met, the acid is released.

This chain-of-proof allows the liability and mandate to be **fully tracked and provable**, including post-facto audits. The information can be viewed via a link (e.g., "bdidrop.link/124V") or through integration with back-office systems.

The structure is robust enough for secure transport of sensitive cargo and simple enough to be used by temporary staff with minimal digital training.

***

### Representation for transactions by IT-applications : DigiDrop

The most common transaction in logistics is the handover of goods (cargo on its way through the supply chain) between entities. Part of the handover is associated with trade (buyer-seller), part of the handover is about liability (transporter taking cargo on board of a vessel, plane, railcarriage or truck).

The "Digidrop" approach to executing transactions (such as transfer of goods) shifts the legal "signing" of a transaction to IT-systems on behalf of the companies involved. The human involvement is supportive and indirect, instead of acting as a representative of the entity. The IT-systems involved act as the representatives of the legal entities involved.

This approach circumvents the issues and obstacles that rise if humans need digitally "sign" a transaction. The Digidrop document outlines the approach.

{% embed url="https://github.com/Topsector-Logistiek/Digidrop" %}

#### Fallback

BDI’s method accounts for **non-ideal environments** — e.g., no internet, broken devices, or limited IT skills. Many (SME) actors in logistics are not yet able to integrate themselves in a more advanced IT-interaction framework such as the BDI.

In such a case the most valuable piece of information that needs to be digitally available is the visbility of a handover event. A fallback methode has been designed for such use cases, minimizing the requirements. Such a method is not a replacement of the traditional "paper-based" processes: it only creates more visbility in the supply chain.

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

## 8. Summary

The **Representation Chain** provides a flexible, secure, and verifiable method for proving authority in business interactions — whether digital or physical. Its implementation via **JWTs** is:

* Scalable
* Legally robust
* Compatible with low-tech environments
* Designed for both machines and people

Combined with **fallback workflows** and **hybrid adoption pathways**, this method is ready for real-world logistics, compliance, and digital service chains.

***

## 9. Further Reading

* [RFC 7519 – JSON Web Token (JWT)](https://datatracker.ietf.org/doc/html/rfc7519)
* [VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/)
* BDI Edge Agreements
* [IANA JWT Claim Registry](https://www.iana.org/assignments/jwt/jwt.xhtml)

**Documents**

{% file src="../../.gitbook/assets/20241128_BDI-JSON-Web-Token-as-generic-proof.pdf" %}

{% file src="../../.gitbook/assets/2024-BDI-Embedded-JWT-as-Representation-Evidence.pdf" %}

{% file src="../../.gitbook/assets/BDI DigiDrop Transport documents.pdf" %}

{% file src="../../.gitbook/assets/20241119 - Proof of Concept Implementatie DigiDrop UltraLite.pages.pdf" %}
