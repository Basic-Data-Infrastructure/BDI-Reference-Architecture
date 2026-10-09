---
cover:
  light: >-
    https://images.unsplash.com/photo-1603725500773-9c78db8a914a?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxhdXRob3JpemF0aW9ufGVufDB8fHx8MTc3NDUyODI0MHww&ixlib=rb-4.1.0&q=85
  dark: >-
    https://images.unsplash.com/photo-1603725500773-9c78db8a914a?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxhdXRob3JpemF0aW9ufGVufDB8fHx8MTc3NDUyODI0MHww&ixlib=rb-4.1.0&q=85
coverY: 0
---

# Authorization Models

## 1. Introduction

Within BDI, authorization is not implemented as a single mechanism but as two distinct patterns that can also be combined. These patterns differ in when and how access decisions are made

## 2. Predefined Access

### 2.1 Concept

Predefined access is a model in which permissions are established before the system is used. Authorization rights are granted through predefined structures such as roles, scopes, or groups.

In this model, authorization decisions are largely deterministic. Once a participant or application has been assigned a specific role or scope, the system can grant access without evaluating complex runtime context.

OAuth scopes are a typical example of this approach. Scopes represent permissions that are granted in advance and define which APIs or datasets a client may access.

### 2.2 When to use&#x20;

Predefined access is particularly suitable in the following situations.&#x20;

<details>

<summary>Stable roles and predictable operational processes</summary>

Organizations often operate with clearly defined user groups and responsibilities. Roles rarely change, and access patterns remain consistent. Example: maintenance personnel are granted access to technical rooms between 08:00 and 17:00 based on their role.

\
In such environments, authorization can be managed efficiently through static privileges without evaluating policy logic for each request.

</details>

<details>

<summary>Scope-based access to services for real-time decisions</summary>

Applications frequently exchange data through APIs under predefined usage conditions. The right to access a dataset or service is granted beforehand and does not depend heavily on contextual conditions.\
Example: a building management API exposes sensor data to dashboards using a predefined scope such as read: sensors.

\
This model is efficient when usage patterns are well understood and the need for contextual authorization is limited.

</details>

<details>

<summary>Compliance and audit-driven environments</summary>

Certain systems require predictable and reproducible authorization behavior to meet regulatory and audit requirements.\
Example: access to regulatory documentation is restricted to the role permit\_officer.

</details>

<details>

<summary>Static privilege assignment</summary>

Static privilege assignment simplifies auditing and certification because the authorization logic remains stable and transparent.

</details>



### 2.3 OAuth 2.0

OAuth 2.0 is used to issue access tokens that carry predefined permissions.

These tokens:

* Represent the identity of the client
* Contain scopes defining allowed operations
* Are used by services to validate access without additional decision logic

### 2.4 Authorization Registry

The Authorization Registry maintains which participants are allowed to access which services.

It provides:

* A shared source of truth for access rights
* Registration of participants and their permissions
* Support for interoperability across the ecosystem

### 2.5 Delegation Model (DM)

The Delegation Model allows participants to delegate predefined rights to other actors.

This enables:

* Controlled delegation of access
* Representation of organisational relationships
* Reuse of permissions across services

## 3. Real-Time Authorization

### 3.1 Concept

In contrast to predefined access, real-time authorization evaluates access as an action is performed. Decisions are made dynamically using contextual information and policy rules. This model is commonly associated with the way of working in supply chain operations, also referred to as policy-based authorization systems. Instead of relying solely on predefined rights, access decisions consider attributes, relationships, and environmental conditions.

### 3.2 When to Use

Real-time authorization is particularly appropriate in the following situations;

<details>

<summary>Context-sensitive access in dynamic environments</summary>

Access may depend on factors such as time, location, device status, or the operational state of a facility.\
Example: a cleaning contractor receives access only when the assigned shift is active, the person is physically located inside the building, and no alarm state is active.&#x20;

{% hint style="info" %}
In such cases, static roles alone are insufficient. Access must be determined using dynamic contextual attributes.
{% endhint %}

</details>

<details>

<summary>Fine-grained authorization per action</summary>

Authorization decisions may need to evaluate not only who the actor is, but also what specific action is being performed and under which conditions.

Example: a technician may configure a machine only if safety checks are completed, no maintenance alerts are active, and the task falls within the authorized scope of work.

{% hint style="info" %}
This level of granularity requires policy evaluation for each request
{% endhint %}

</details>

<details>

<summary>Cross-organizational collaboration</summary>

In federated ecosystems, multiple organizations interact without sharing a single centralized authorization structure.\
Example: external inspectors may receive temporary operational access at a facility, while authorization decisions are enforced according to the building’s policies and trusted contextual signals.

{% hint style="info" %}
In such scenarios, predefined roles within a single organization cannot represent all authorization conditions.
{% endhint %}



</details>

<details>

<summary>Zero Trust and continuous risk evaluation</summary>

Modern security architectures increasingly require that every request be evaluated dynamically using risk signals.\
Example: an employee accessing services through an untrusted network may receive restricted permissions even if they normally have broader access rights.

{% hint style="info" %}
Real-time authorization enables such adaptive security policies.
{% endhint %}



</details>

### 3.3 XACML Policies

BDI uses XACML to define and evaluate authorization policies.

XACML enables:

* Definition of fine-grained access rules
* Evaluation based on attributes (subject, resource, action, environment)
* Separation between policy definition and enforcement

Policies determine whether a specific action is allowed under specific conditions.

### 3.4 PDP and PEP

Real-time authorization is enforced through:

* Policy Decision Point (PDP)\
  Evaluates policies and returns an allow/deny decision.
* Policy Enforcement Point (PEP)\
  Intercepts incoming requests and enforces the decision from the PDP.

This architecture ensures that every request can be evaluated in its full context.

## 4. Combining both patterns

Combining both patterns in BDI means they are applied in sequence. First, predefined access mechanisms such as OAuth, AR, and DM establish who is allowed to access which resources in general. Next, real-time authorization using XACML determines whether a specific action is allowed under the current conditions.

In practice, the interaction follows a clear flow. A participant first obtains an OAuth 2.0 access token. This token contains predefined scopes and delegated rights. The participant then makes a request to a service. The Policy Enforcement Point (PEP) intercepts this request and forwards it for evaluation. The Policy Decision Point (PDP) evaluates the applicable policies using relevant contextual data. Based on this evaluation, a final decision is made and enforced.

In this model, OAuth, AR, and DM are responsible for the distribution of access rights, while XACML evaluates those rights within a specific context. This separation allows for scalable interoperability across participants and enables fine-grained control within services. It also aligns with Zero Trust principles.

Overall, this structure ensures that authorization remains both manageable and adaptable in federated environments.
