---
cover:
  light: >-
    https://images.unsplash.com/photo-1546198632-9ef6368bef12?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxyZWdpc3RlcnxlbnwwfHx8fDE3NzM4NDE2NDd8MA&ixlib=rb-4.1.0&q=85
  dark: >-
    https://images.unsplash.com/photo-1546198632-9ef6368bef12?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxyZWdpc3RlcnxlbnwwfHx8fDE3NzM4NDE2NDd8MA&ixlib=rb-4.1.0&q=85
coverY: 0
layout:
  width: default
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
---

# Orchestration Register

## 1. Purpose of the building block

The Orchestration Registry provides a trusted, shared view of who is involved in a specific supply chain context and in what role, enabling context-aware authorization.

## 2. Concepts

The three core components; the Association Registry, the Orchestration Registry, and the BDI Connector together form a layered authentication and authorization model for both predefined and event-driven, dynamic supply chain collaboration. These components operate in a fixed sequence and collectively provide the context and trust required for controlled interactions between supply chain participants:

{% stepper %}
{% step %}
### Association Registry

**BVAD Token:** Verifies whether an organization is a member of the association and issues a BDI Verifiable Association Data (BVAD) token that confirms the organization’s membership and status.
{% endstep %}

{% step %}
### Orchestration Registry

**BVOD Token:** Verifies which parties are involved in a specific supply chain context (for example, an order or transport), including their role and level of involvement and it issues a BDI Verifiable Orchestration Data (BVOD) token. This information is used not only for predefined collaboration but also as active context to determine who should be operationally informed when events occur.
{% endstep %}

{% step %}
### BDI Connector (Server/Proxy)

**Local authorization decision and enforcement:** Validates the received BVAD and BVOD tokens and translates them into enforceable authorization inputs in accordance with BDI agreements. The Connector ensures that data exchange and the sending or receiving of events only take place within the established supply chain context and trust agreements, regardless of whether the interaction is request/response-based or event-driven. In the case of event-driven collaboration, the BDI Connector also handles the technical processing of notifications (for example, via technology-agnostic webhooks) toward local systems.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
The actual access decision can, in simple scenarios, be configured within the BDI Connector, or in more complex situations be delegated to a Local Policy Engine implemented by the data owner within their own IT ecosystem. This Local Policy Engine is not part of the BDI core components but uses the context and trust information provided by BDI as input for a local authorization decision.
{% endhint %}

***

## 3. Risks

If the Orchestration Registry contains incomplete or incorrect information about which parties are involved and in what role, it can lead to improper authorization decisions, which may ultimately result in data leaks.

## 4. Interlinkages with other building blocks

This building block has links to:

<a href="https://app.gitbook.com/s/EsnYrgeqsPPZtbALTQAj/readme/trust-kit/association-register-1" class="button secondary">Association Register</a><a href="https://app.gitbook.com/s/EsnYrgeqsPPZtbALTQAj/readme/data-set-kit/data-licenses" class="button secondary">Data Licenses</a><a href="https://app.gitbook.com/s/EsnYrgeqsPPZtbALTQAj/readme/trust-kit/policy-agreements" class="button secondary">Policy Agreements</a>



## 5. Elements and their key functions

Each component has a clearly defined responsibility.

| Element                 | Responsibility                                                                                                                                                                                                                                        | Key question                          |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| Association Register    | Membership management, verification, and issuance of membership tokens                                                                                                                                                                                | Who can be trusted?                   |
| Orchestrations Register | Registration of supply chain context and its resolution for data and event interaction through the issuance of engagement tokens                                                                                                                      | Who is involved in this supply chain? |
| BDI Connector           | Validation, translation, and enforcement of BDI context toward local authorization, including event-based interactions. PKI functionality for signing and verifying authenticated information, including support for an optional local policy engine. | Is this interaction permitted?        |

The core components are modular by design: changes in membership policies or trust information have no direct impact on supply chain context registration (Orchestration Registry), and vice versa. The Local Policy Engine combines these information sources without enforcing centralized decision-making within BDI.

### 5.1 No central orchestration beyond the components

The architecture follows the BDI principle of local decision-making: there is no central authority dictating access decisions. Instead:

* **Data owners remain in control:** Each data custodian (terminal, carrier, logistics service provider) implements its own Local Policy Engine (optionally facilitated by the BDI Connector) and determines what data is shared and under what conditions.
* **Context-scoped Orchestration Registry:** The Orchestration Registry provides a shared service for supply chain context registration, where access to context is strictly limited to parties involved in the relevant transaction. Within this boundary, visibility of other parties and the receipt of relevant events are further restricted based on role and responsibility, in accordance with the principle of least privilege. This ensures that each party only has access to the information necessary to perform its role within the chain.\
  A possible implementation is a **multi-tenant Orchestration Registry**, where the association offers the registry as a shared service. Each transport orchestrator (typically the shipper or freight forwarder) manages only its own transport dossiers within this environment. Strict tenant isolation ensures that orchestrators can access only their own data.
* **Federated trust:** The Association Registry provides a common trust foundation but does not impose operational decisions on participants.

This decentralized model eliminates single points of failure and respects the data sovereignty of all participating organizations.

## 6. Core design decisions

### **6.1** Dual-token principle and local decision-making

This dual-token model guarantees that access to operational data is only possible when both:

* the membership and status of an organization (BVAD),&#x20;
* the involvement in a specific supply chain context (BVOD)

has been established in a machine-verifiable manner.

The data owner explicitly remains “in control of their own data.” Each participant can implement their own Local Policy Engine (for example, Open Policy Agent, Cedar, Casbin, Keycloak Authorization Services, or Kyverno) and independently define policy rules. From the BDI core perspective, this role is limited to providing specifications, sample configurations, and implementation guidelines.

To enable a low-threshold implementation for a data provider, it is possible to configure the BDI Connector as a standalone Policy Engine; in this case, the Connector functions as both a Policy Decision Point (PDP) and a Policy Enforcement Point (PEP).

In situations where the data provider already has its own Policy Engine / PDP, the Connector functions as a Policy Enforcement Point (PEP).

The Association Registry and the Orchestration Registry jointly act as Policy Information Points (PIPs).

### 6.2 Component: Orchestration Registry (ORS)

The Orchestration Registry manages the context of logistics supply chains. It records which entities are involved in specific orders or transports and in which roles they operate. The registry does not contain operational data itself but functions as a Policy Information Point (PIP) for access decisions. Additionally, the Orchestration Registry acts as a central hub for detecting and distributing context changes within the chain.

### 6.3 Orchestration and validation

The registry must record orchestration information (who is involved in which order) and expose it through verifiable tokens (the “BVOD”). A key functional requirement is the validation of logical combinations, such as verifying whether a specific party is actually linked to a Bill of Lading (B/L) or container number.

Changes in this orchestration information must be recognized by the registry as relevant events.

### 6.4 Relationship management and delegation

In addition to direct involvement, the registry must support complex relationships and delegations. This makes it possible for one party (for example, a freight forwarder) to request data or perform actions on behalf of another party (for example, a BCO), provided that this relationship is authorized in the registry.

The registry must be able to detect changes in relationships and delegations and make them available as notification-worthy events.

### 6.5 JWS issuance and notifications

As a source of contextual truth, the Orchestration Registry, like the other components, must be capable of cryptographically signing tokens and messages (JWS signing).

In addition, the registry must generate automatic notifications for relevant events within a supply chain context, such as changes in involved parties, roles, delegations, or authorizations.

To support this, the Orchestration Registry must provide a subscription mechanism based on webhook-based event calls, allowing supply chain partners to subscribe to events relevant to them. Only authorized parties may receive notifications related to their role or position within the supply chain.

## 7. Future topics



## 8. Further reading

* Best practice report keycloack
