---
cover:
  light: ../../.gitbook/assets/shutterstock_2139978403-scaled.webp
  dark: >-
    https://images.unsplash.com/photo-1548092372-0d1bd40894a3?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxzZWN1cml0eXxlbnwwfHx8fDE3NjI5NTIyMzN8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 462
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
---

# BDI Security Framework

### 1. Introduction

{% hint style="info" %}
Security is a prerequisite for trust in the BDI. Without **verifiable**, **enforceable**, and **context-aware** protection measures, data exchange between actors loses its integrity, availability, and confidentiality.&#x20;
{% endhint %}

The BDI Security Framework defines a structured approach to cybersecurity within BDI’s federated, many-to-many architecture. The framework provides the following functionality:&#x20;



<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th><th data-hidden data-type="image">Cover image (dark)</th><th data-hidden data-card-cover-dark data-type="image">Cover image (dark)</th></tr></thead><tbody><tr><td><strong>Participation</strong></td><td>The framework enables participants - regardless of their maturity - to organize security coherently across roles, organizations, and technology boundaries.</td><td><a href="https://images.unsplash.com/photo-1516321497487-e288fb19713f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxwYXJ0aWNpcGF0ZXxlbnwwfHx8fDE3NjI5NTI5MDV8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1516321497487-e288fb19713f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxwYXJ0aWNpcGF0ZXxlbnwwfHx8fDE3NjI5NTI5MDV8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td><td></td><td><a href="https://images.unsplash.com/photo-1530811761207-8d9d22f0a141?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxwYXJ0aWNpcGF0ZXxlbnwwfHx8fDE3NjI5NTI5MDV8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1530811761207-8d9d22f0a141?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxwYXJ0aWNpcGF0ZXxlbnwwfHx8fDE3NjI5NTI5MDV8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Security</strong></td><td>The framework covers the full scope of security including technical controls, behavioral practices, governance processes, and recommended operational workflows.</td><td><a href="https://images.unsplash.com/photo-1590065707046-4fde65275b2e?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxzZWN1cmV8ZW58MHx8fHwxNzYyOTUyODc0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1590065707046-4fde65275b2e?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxzZWN1cmV8ZW58MHx8fHwxNzYyOTUyODc0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td><td><a href="https://images.unsplash.com/photo-1614064641938-3bbee52942c7?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxzZWN1cml0eXxlbnwwfHx8fDE3NjI5NTIyMzN8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1614064641938-3bbee52942c7?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxzZWN1cml0eXxlbnwwfHx8fDE3NjI5NTIyMzN8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td><td><a href="https://images.unsplash.com/photo-1614064641938-3bbee52942c7?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxzZWN1cml0eXxlbnwwfHx8fDE3NjI5NTIyMzN8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1614064641938-3bbee52942c7?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxzZWN1cml0eXxlbnwwfHx8fDE3NjI5NTIyMzN8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Responsibility and Trust</strong></td><td>The framework focuses on the enforceable layer between participants, while outlining continued responsibilities once data enters internal domains where trust obligations apply.</td><td><a href="../../.gitbook/assets/bdi website images 3.webp">bdi website images 3.webp</a></td><td><a href="https://images.unsplash.com/photo-1534484489997-0a40568864d0?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxoYW5kJTIwcmFpc2V8ZW58MHx8fHwxNzYyOTUyNzYzfDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1534484489997-0a40568864d0?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxoYW5kJTIwcmFpc2V8ZW58MHx8fHwxNzYyOTUyNzYzfDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td><td><a href="https://images.unsplash.com/photo-1498192467103-290f567eb3a3?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxyZXNwb25zaWJpbGl0eXxlbnwwfHx8fDE3NjI5NTI5NzF8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1498192467103-290f567eb3a3?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxyZXNwb25zaWJpbGl0eXxlbnwwfHx8fDE3NjI5NTI5NzF8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>



### 2. Security in relation to Trust

It is important to note the difference between **security** and **trust**. Trust serves as the foundation for recognition and mandate within the BDI, while security safeguards these relationships by ensuring systems execute them safely. The current building block focuses on the **Security** framework. The table below highlights the distinct focus of the Trust and Security frameworks.&#x20;

{% hint style="warning" %}
Without security, trust erodes. Without trust, security cannot scale.
{% endhint %}

{% columns %}
{% column width="50%" valign="middle" %}
**Trust framework**

* is defined through governance agreements, roles, mandates, and ecosystem-wide business rules.&#x20;
* organizes trust between parties through business rules, governance, agreements, and audits.
{% endcolumn %}

{% column width="50%" %}
**Security framework**

* is the enforcement and operational execution of the trust agreements via protective and assurance mechanisms.&#x20;
* manages risks and prevents undesirable behavior through technical and organizational measures.
{% endcolumn %}
{% endcolumns %}

While the domains Trust and Security are closely related and mutually reinforcing, a deliberate distinction should be made. The agreements and business rules defined in the trust framework influence the security architecture, but the Security framework focuses purely on the execution and assurance side.

_For enforcement across internal and external domains, see “Delegated Implementation vs. Retained Accountability.”_&#x20;



### 3. Purpose

The BDI Security Framework delivers a common reference model for coordinated security across distributed actors. It is based on [NIST Cybersecurity Framework (CSF) 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20), providing coordinated, outcome-oriented security guidelines. The security framework ensures the protection of digital interactions between independent actors.&#x20;

***

#### 3.1 Features of the BDI Security Framework&#x20;

The framework&#x20;

* Aligns with BDI's federated, role-based architectural model
* Supports multi-party risk governance across diverse maturity levels
* Will be extended with minimum requirements per role and example implementation controls
* Functions as a living framework, continuously refined based on operational feedback and practical adoption

_See “Profiles and Risk Assessment” and “Roles and Profiles: Separation and Mapping” for current definitions and mappings._



### 4. Enforcement and local implementation autonomy

The BDI Security Framework is neither a compliance baseline nor a certification mechanism. Instead, it acts as a _practical guide_, while the actual enforcement decisions remain the responsibility of each association or federation.&#x20;

* Associations may mandate profiles or specific requirements.
* Additional controls may be applied depending on risk classification.&#x20;
* Coordination with the agreement framework ensures that trust enforcement and security execution remain aligned.&#x20;

This model preserves interoperability while allowing flexibility in local adoption and scaling.



### 5. Why NIST CSF 2.0?

This security framework is built on NIST CSF 2.0 to meet the operational realities and governance needs of BDI. Rather than introducing a new model, the framework intentionally leverages an established and adaptable framework that aligns with existing organizational practices.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Federated Applicability</strong></td><td>CSF 2.0 is suitable for ecosystems of multiple, independent actors operating under a shared but non-centralized governance model.</td><td><a href="https://images.unsplash.com/photo-1545987796-200677ee1011?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxuZXR3b3JrfGVufDB8fHx8MTc2MzExMDUxMXww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1545987796-200677ee1011?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxuZXR3b3JrfGVufDB8fHx8MTc2MzExMDUxMXww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Compatibility with Legal Standards</strong></td><td>It allows integration and mapping with <a href="https://eur-lex.europa.eu/eli/dir/2022/2555/oj">NIS2</a>, <a href="https://www.iso.org/standard/27001">ISO/IEC 27001/2</a>, <a href="https://www.informatiebeveiligingsdienst.nl/onderwerpen/bio/">BIO</a> (Baseline Informatiebeveiliging Overheid), <a href="https://eur-lex.europa.eu/eli/reg/2016/679/oj">GDPR / AVG</a>, and other frameworks used for compliance or internal policy.</td><td><a href="https://images.unsplash.com/photo-1589391886645-d51941baf7fb?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxsZWdhbHxlbnwwfHx8fDE3NjMxMTA1MjF8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1589391886645-d51941baf7fb?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxsZWdhbHxlbnwwfHx8fDE3NjMxMTA1MjF8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Operational and Strategic Usability</strong></td><td>The structure supports practical use in day-to-day security operations as well as in board-level and governance contexts.</td><td><a href="https://images.unsplash.com/photo-1532635042-a6f6ad4745f9?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxsb2dpc3RpY3N8ZW58MHx8fHwxNzYzMTEwNzcwfDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1532635042-a6f6ad4745f9?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxsb2dpc3RpY3N8ZW58MHx8fHwxNzYzMTEwNzcwfDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Role-based Extensibility</strong></td><td>The framework is designed to be expanded with role-specific minimum requirements and example control sets.</td><td><a href="https://images.unsplash.com/photo-1524292423711-59aa650d2cf2?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxmcmFtZXdvcmt8ZW58MHx8fHwxNzYzMTEwODQwfDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1524292423711-59aa650d2cf2?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxmcmFtZXdvcmt8ZW58MHx8fHwxNzYzMTEwODQwfDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Support for Staged Maturity</strong></td><td>Built-in maturity levels and outcome-oriented design allow structured capability growth over time.</td><td><a href="https://images.unsplash.com/photo-1543286386-2e659306cd6c?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw4fHxncm93dGh8ZW58MHx8fHwxNzYzMTEwODA2fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1543286386-2e659306cd6c?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw4fHxncm93dGh8ZW58MHx8fHwxNzYzMTEwODA2fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

### 6. Structure of the Security Framework

This framework is organized around the six core functions of [NIST CSF 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20):&#x20;

* **Govern:** Establish and monitor cybersecurity risk governance, accountability, and strategic alignment.
* **Identify:** Develop an understanding of assets, systems, data, and risks across the ecosystem.
* **Protect:** Implement safeguards to ensure service continuity, data protection, and access control.
* **Detect:** Establish capabilities to identify the occurrence of cybersecurity events in real time or retrospectively.
* **Respond:** Coordinate actions during and after a detected incident to contain impact and communicate effectively.
* **Recover:** Maintain plans for restoring assets and services and improving future resilience.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Each function is further elaborated per profile with relevant subcategories, implementation tiers, and control examples. These are provided as part of the Coherent Security Register, which can be found at the end of this page.&#x20;

Role-specific mappings and associated responsibilities are elaborated in “_Roles and Profiles: Separation and Mapping_".&#x20;

### 7. Scope

This security framework provides a common foundation for cybersecurity across the BDI ecosystem, enabling secure, scalable, and trust-based data interaction between independent participants. The system

* focuses on the enforceable interface between participants in the BDI ecosystem (roles, systems, interfaces).&#x20;
* extends into internal domains only where trust agreements impose obligations on processing or safeguarding received data.
* allows for enforceable controls if trust agreements call for it.
* is aligned with the BDI agreement framework.
* complements trust governance with enforceable security execution.



### 8. Design principles and capabilities

The design principles and capabilities of the security framework are specified as follows:&#x20;

* Covers technical controls, governance processes, behavioral practices, and/or operational workflows
* Provides a role-based structure with minimum and maturity-based requirements, enabling capability growth over time
* Supports interoperable and auditable trust decisions across organizations, using a shared language of controls



### 9. Security profiles and risk assessment

Profiles define the minimum set of security outcomes required to fulfill responsibilities associated with **BDI Security Framework Profiles**. They represent coherent bundles of responsibilities aligned to ecosystem needs.

Each association implementing BDI must assess whether the “_Minimum_” Profile requirements are sufficient for their respective use cases, based on risk classification (e.g., information sensitivity or business impact). A practical approach is to use classification schemes such as **CIA** (Confidentiality, Integrity, Availability). If risks exceed the Minimum baseline, additional controls should be selected.

Profiles are based on real-world usage scenarios. For guidance on creating and using profiles, please refer to [NIST SP 1301](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.1301.pdf). They ensure that actors in similar roles apply comparable protection levels and contribute to ecosystem-wide assurance.

{% hint style="warning" %}
_Detailed subcategories, required outcomes, and implementation examples per profile are maintained in the separate **BDI Coherent Security implementation register**._
{% endhint %}

### 10. BDI roles and profiles: separation and mapping

Profiles do not define what technology to use. They define the responsibilities of a role, regardless of implementation. For BDI-specific implementation examples, refer to the Coherent Security Register documentation (See the attached document at the bottom of this page).&#x20;

Each [BDI role](../introduction/bdi-technical-roles.md) maps to a **BDI CSF Profile** as follows:

<table><thead><tr><th width="144" valign="top">BDI Roles</th><th width="198" valign="top">BDI CSF Profile</th><th valign="top">Rationale for Profile</th></tr></thead><tbody><tr><td valign="top">Data owner</td><td valign="top">Data Provisioning Profile</td><td valign="top">Covers the provisioning of data or event access. Organizations implementing this profile might delegate responsibilities (but not accountability) to others.</td></tr><tr><td valign="top">Data Consumer</td><td valign="top">Data Access Requesting Profile</td><td valign="top">Covers the requesting of data or event access. Organizations implementing this profile might delegate responsibilities (but not accountability) to others.</td></tr><tr><td valign="top">Identity Provider, Identity Broker &#x26; Association Administrator</td><td valign="top">Trust Services Profile</td><td valign="top">Provides foundational trust services through authentication and federation for digital actors, and maintains oversight via registry, role, and mandate governance at the ecosystem level.</td></tr><tr><td valign="top">Data Service Provider</td><td valign="top">Policy Enforcement Profile</td><td valign="top">Executes technical implementation of data access and security policies defined by the Data Owner.</td></tr></tbody></table>

\
An organization may assume multiple roles and thus implement multiple profiles. The security requirements that follow depend on which profiles are fulfilled.

### 11. Delegated implementation vs. retained accountability

{% hint style="warning" %}
BDI acknowledges that many organizations, especially smaller ones, may outsource or delegate parts of their technical implementation to software vendors or ICT service providers.&#x20;

Note that outsourcing does **not** shift accountability.
{% endhint %}

Each profile assigns accountability for meeting its associated security outcomes. Delegated responsibilities must be traceable, enforced contractually if needed, and auditable where required. This allows vendors and partners to understand what is expected of them, even if they are not directly bound by trust agreements.

{% file src="../../.gitbook/assets/Coherent Security Register.xlsx" %}

&#x20;
