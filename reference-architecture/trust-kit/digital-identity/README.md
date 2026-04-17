---
cover: >-
  https://images.unsplash.com/photo-1483478550801-ceba5fe50e8e?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxkaWdpdGFsJTIwaWRlbnRpdHl8ZW58MHx8fHwxNzY1MzYwODc0fDA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 328
---

# Digital Identity Framework: Framing the Triple Identity

See [Digital Identity M2M](digital-identity.md) and [Digital Identity H2M](digital-identity-h2m.md)

## 1. Introduction

The Triple Identity model is a key concept in the Digital Identity building block. As can be seen in the triangle in the figure bellow, this model consists of 3 elements. Each one of these elements is required in order to verify a digital identity.&#x20;

<figure><img src="../../../.gitbook/assets/Gitbook files - Triple Identity.drawio.png" alt=""><figcaption></figcaption></figure>

BDI does not introduce a strict “triple identity model” as a universal rule. Instead, it describes three types of entities that appear in real-world interactions and clarifies how their relationships can be authenticated using established trust frameworks.\
The goal is to emulate real-world business practice in a digital ecosystem: legal entities transact, individuals and systems carry out the actions, and trust derives from verifiable relationships anchored in authoritative sources.

## 2. Purpose

BDI requires a reliable way to identify who or what is acting, on whose behalf, and in which context. The aim isn’t to create a new identity model, but to clearly describe the relationships that enable trustworthy digital interactions between organizations.

\
BDI adopts established international identity and trust frameworks (ISO/IEC 29115, ISO/IEC 18013, ISO/IEC 29146, eIDAS ARF) and expresses their relevant components in a form usable by non-specialists.

BDI interactions take place between legal entities. In practice, the actions underpinning these interactions are performed by natural persons and systems. Trustworthy digital exchange requires clarity about these relationship

## 3. Concepts

BDI identifies three entities that appear in most real-world interactions:

{% stepper %}
{% step %}
#### Legal Entity

<details>

<summary><strong>A legal entity is defined as an organization recognized in law.</strong> </summary>

Digital trust depends on verifying the existence of the legal entity and linking it to the digital credentials it controls.

Registries such as KvK, vLEI, DUNS, or DNS provide existence and attribute data. Digital authentication requires cryptographic credentials (eIDAS QWAC/QSeal, vLEI credentials, or verifiable credentials derived from authoritative sources such as the BDI Association).

</details>
{% endstep %}

{% step %}
#### Natural Person

<details>

<summary><strong>A natural person is defined as a human individual.</strong></summary>

This category includes employees, representatives, and other individuals acting on behalf of an organization. The digital ecosystem must be able to authenticate such individuals when their involvement forms part of a transaction’s trust requirements.

BDI relies on digital authentication mechanisms tied to authoritative sources (eIDAS identity providers, verifiable credentials for personhood or role, national identity instruments where applicable).

{% hint style="warning" %}
E-mail addresses or phone numbers are not identity instruments; they can only serve as contact aliases unless validated by an authoritative registry.
{% endhint %}

</details>
{% endstep %}

{% step %}
#### Applications

<details>

<summary><strong>An application is an IT system providing value to it owner.</strong></summary>

A system is defined as a digital agent, software application, API client, automated workflow, scheduled process or machine, that performs actions in a transaction. A system can act autonomously once configured by a human. A system may be exclusive to one organization or used by many organizations (e.g., SaaS platforms, port community systems).

\
BDI concerns itself with the system’s link to the legal entity: which organization controls the system, and under what authorization regime. Digital authentication is achieved using cryptographic credentials, signed software statements, or verifiable credentials representing system attributes.

</details>
{% endstep %}
{% endstepper %}

## 4. Core Design Principles

As shown in the triangle above BDI recognizes three verifiable relationships.

{% stepper %}
{% step %}
<details>

<summary><strong>Natural Person ↔ Legal Entity</strong></summary>

Proves that a specific individual is authorized to act for the organization. Mechanisms include:

* eHerkenning (in the Netherlands)
* vLEI Role Credential
* organizational Affiliation Verifiable Credentials
* eIDAS and related standards and technical specifications

</details>
{% endstep %}

{% step %}
<details>

<summary><strong>System ↔ Legal Entity</strong></summary>

Proves that a system is operated, owned, or contractually controlled by the organization. Mechanisms include:

* eIDAS QWAC/QSeal used for server or API authentication
* vLEI Legal Entity credentials bound to a system credential
* Signed software statements with organizational binding
* Verifiable credentials representing system attributes or control

</details>
{% endstep %}

{% step %}
<details>

<summary><strong>Natural Person ↔ System</strong></summary>

Proves that an authenticated user session corresponds to a particular individual using a particular system. Mechanisms include:

* Strong user authentication (eIDAS / national eID) tied to an application session
* Authorization assertions issued by the system following authenticated login
* Device or client certificate associated with the authenticated user

This linkage is required only where the transaction demands attribution to a particular human (e.g., granting consent, creating binding commitments, administering organizational settings)

</details>
{% endstep %}
{% endstepper %}

## 4. Interlinkages with other building blocks

<a href="https://app.gitbook.com/s/EsnYrgeqsPPZtbALTQAj/readme/trust-kit/digital-identity/digital-identity" class="button secondary">Digital Identity M2M</a><a href="https://app.gitbook.com/s/EsnYrgeqsPPZtbALTQAj/readme/trust-kit/digital-identity/digital-identity-h2m" class="button secondary">Digital Identity H2M</a><a href="https://app.gitbook.com/s/EsnYrgeqsPPZtbALTQAj/readme/trust-kit/authorisation-oauth-2.0-ar-dm-+-xacml-policies" class="button secondary">Authorization</a><a href="../authentication/" class="button secondary">Authentication</a>

## 5. Future Work

For future work, the nuance in the relationship between a natural person and a legal entity will be considered. In some cases, the natural person acts as a representative of the legal entity. In other cases, the natural person is only granted access to its resources.

The European Business Wallet proposal (COM(2025) 838 final) already distinguishes between these situations. It defines technical mandates, where a natural person acts as an authorized representative of the legal entity and uses systems on its behalf. It also defines administrative mandates, where a user is assigned roles and responsibilities that enable access to the legal entity’s resources.

