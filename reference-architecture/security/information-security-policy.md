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

# 🔐 BDI Security Framework

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

The BDI Security Framework delivers a common reference model for coordinated security across distributed actors. It is based on [NIST Cybersecurity Framework (CSF) 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20), providing coordinated, outcome-oriented security guidelines. The security framework ensures the protection of digital interactions between independent actors. The basics of this framework are visualized in the figure below.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

***

#### 3.1 Features of the BDI Security Framework&#x20;

The framework&#x20;

* Aligns with BDI's federated, role-based architectural model
* Supports multi-party risk governance across diverse maturity levels
* Will be extended with minimum requirements per role and example implementation controls
* Functions as a living framework, continuously refined based on operational feedback and practical adoption

_See “Profiles and Risk Assessment” and “Roles and Profiles: Separation and Mapping” for current definitions and mappings._



### 4. Enforcement and Local Implementation Autonomy

The BDI Security Framework is neither a compliance baseline nor a certification mechanism. Instead, it acts as a _practical guide_, while the actual enforcement decisions remain the responsibility of each association or federation.&#x20;

* Associations may mandate profiles or specific requirements.
* Additional controls may be applied depending on risk classification.&#x20;
* Coordination with the agreement framework ensures that trust enforcement and security execution remain aligned.&#x20;

This model preserves interoperability while allowing flexibility in local adoption and scaling.

{% file src="../../.gitbook/assets/BDI Security Framework Register.xlsx" %}

