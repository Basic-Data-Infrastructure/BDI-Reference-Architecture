---
cover: >-
  https://images.unsplash.com/photo-1697490251905-d7abdf8436ca?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxtYWludGVuYW5jZSUyMGFuZCUyMGNvbW11bml0eSUyMGNvbnRyaWJ1dGlvbnxlbnwwfHx8fDE3NjQwNzk4NTR8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 517
---

# 🔧 BDI Maintenance and Community Contributions (Suus)

{% hint style="info" %}
**To file a change request, submit an issue** **here**: [https://github.com/Basic-Data-Infrastructure/BDI-change-requests](https://github.com/Basic-Data-Infrastructure/BDI-change-requests)
{% endhint %}

## 1. Introduction

This page describes the BDI Change and Release Management Process for maintaining the BDI Architecture Documentation. As BDI transitions into a maintenance phase, a thorough process for change and release management is becoming increasingly important.

Both the associations that follow the BDI and the BDI itself exist in an environment subject to continuous change due to:

* Legislative and regulatory changes
* Technological advances
* Emergence of new application areas
* Previous experience and lessons learned from previous projects
* Changes in business processes

Such environmental changes may call for changes in the BDI Reference Architecture. However, as these changes could impact many stakeholders, careful change management is important. The **BDI Change Management and Release Management Processes** are introduced for this purpose.

## 1.2 Scope

The Change and Release Management applies to the following assets:

* [The BDI Framework documentation](https://bdi.gitbook.io/public)
* [The BDI Developer Portal](https://dev.bdinetwork.org/), including example IT components provided by BDI

Explicitly out of scope are any third party IT components mentioned in the BDI Framework documentation or BDI Developer Portal. These components are subject to their own change and release management processes.

## 1.3 Core principles

The Change and Release Management Process must be **transparent**, **predictable** and **fair**. Each of these principles is discussed below.&#x20;

### Transparency

<table data-card-size="large" data-view="cards" data-full-width="false"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Transparency Principle</strong></td><td>The Change and Release Management Process must be <em>transparent</em></td><td><a href="https://images.unsplash.com/photo-1615279113483-82e6693dab8f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHx0cmFuc3BhcmVuY3l8ZW58MHx8fHwxNzY0MDgwNjAzfDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1615279113483-82e6693dab8f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHx0cmFuc3BhcmVuY3l8ZW58MHx8fHwxNzY0MDgwNjAzfDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

<table data-header-hidden><thead><tr><th width="171"></th><th></th></tr></thead><tbody><tr><td><strong>Statement</strong></td><td>Everything that happens regarding (potential) changes, decisions and releases is well documented and publicly visible.</td></tr><tr><td><strong>Rationale</strong></td><td>By using a transparent process, stakeholders are expected to have a better trust in the outcome of the process and the involvement of the community &#x26; stakeholders throughout the process, resulting in wider adoption of the BDI.</td></tr><tr><td><strong>Example implementation</strong></td><td>Maintaining all RfCs and MCs in a public GitHub repository ensures that all stakeholders are able to track progress.</td></tr></tbody></table>

### Predictability

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Predictability</strong></td><td>The Change and Release Management Process must be <em>predictable</em></td><td data-object-fit="cover"><a href="https://images.unsplash.com/photo-1509048191080-d2984bad6ae5?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxjbG9ja3xlbnwwfHx8fDE3NjQwODEzNzh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1509048191080-d2984bad6ae5?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxjbG9ja3xlbnwwfHx8fDE3NjQwODEzNzh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

<table><thead><tr><th width="173"></th><th></th></tr></thead><tbody><tr><td><strong>Statement</strong></td><td>Careful planning and execution of releases and version deprecation should lead to a predictable situation for stakeholders.</td></tr><tr><td><strong>Rationale</strong></td><td>Adoption of the BDI means implementation in technical products, contracts and possibly other assets. Maintaining these assets is costly for stakeholders. A predictable version, release and version deprecation process should lead to a manageable impact of changes for stakeholders.</td></tr><tr><td><strong>Example implementation</strong></td><td>Designing and adhering to a release schedule of a certain amount of major releases per year ensures that stakeholders are able to plan the required capacity in advance.</td></tr></tbody></table>

### Fairness

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Fairness principle</strong></td><td>The Change and Release Management Process must be <em>fair</em></td><td><a href="https://images.unsplash.com/photo-1589578527966-fdac0f44566c?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxmYWlybmVzc3xlbnwwfHx8fDE3NjQwODEyMDh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1589578527966-fdac0f44566c?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxmYWlybmVzc3xlbnwwfHx8fDE3NjQwODEyMDh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

<table data-header-hidden><thead><tr><th width="173"></th><th></th></tr></thead><tbody><tr><td><strong>Statement</strong></td><td>All decisions must be made carefully, respecting and weighing the interests of involved stakeholders, through a clear decision making process.</td></tr><tr><td><strong>Rationale</strong></td><td>By making sure that decisions are made carefully, stakeholders will have a better trust in the outcome of the decision making process.</td></tr><tr><td><strong>Example implementation</strong></td><td>A well-designed governance structure, incorporating defined escalation paths, ensures that stakeholders have a process to challenge decisions. This builds trust and prevents any single individual (such as the Product Owner) from having absolute, unchecked authority.</td></tr></tbody></table>

## 1.4 Change management process

A change can be either a **Request for Change (RfC)** or a **Minor Change**, the difference being the impact of the change to the community. An accepted RfC requires BDI-based associations to take action to remain compliant with the new BDI version, whereas Minor Changes do not. However, associations, at their discretion, can decide not to comply with the new BDI version but rather follow the old one.&#x20;

### 1.4.1 RfCs

#### 1.4.1.1 Process for RfCs

The following diagram describes the process for managing RfCs.

<div data-full-width="true"><figure><img src="../.gitbook/assets/Schermafbeelding 2025-09-19 Final.png" alt=""><figcaption></figcaption></figure></div>

Roughly the RfC transitions through the following phases:

{% stepper %}
{% step %}
**Identification**

A stakeholder — such as the BDI Product Owner — identifies a required change or opportunity for improvement.
{% endstep %}

{% step %}
**Registration**

The stakeholder  — possibly supported by the Product Owner — describes the RfC and registers it.
{% endstep %}

{% step %}
**Discussion**

The Product Owner discusses the RfC with the Expert Group. The Expert Group and Product Owner formulate an advice on the RfC for the Architecture Board.
{% endstep %}

{% step %}
**Decision**&#x20;

The Architecture Board decides whether or not to start impact analysis, taking into account the advice from the Expert Group and Product Owner.
{% endstep %}

{% step %}
**Scheduling**

The Product Owner schedules the RfC for impact analysis.
{% endstep %}

{% step %}
**Impact analysis**

The Product Owner, supported by the community and the BDI organization, performs an impact analysis.
{% endstep %}

{% step %}
**Discussion**

The RfC and the impact analysis are discussed with the Expert Group. The Expert Group and Product owner formulate an advice on the RfC and the impact analysis for the Architecture Board.
{% endstep %}

{% step %}
**Decision**&#x20;

The Architecture Board decides whether or not to accept the RfC and schedule it for implementation.
{% endstep %}

{% step %}
**Implementation scheduling**

The Product Owner schedules the RfC for implementation.
{% endstep %}
{% endstepper %}

The result of this process is an accepted RfC, with a clearly described impact on the reference architecture.

#### 1.4.1.2 Templates&#x20;

The RfC process is supported by the following templates:

* RfC Description Template \[to be drafted]
* RfC Impact Analysis Template \[to be drafted]

The decision making process is supported by:

* RfC Decision Guidelines \[to be drafted]

### 1.4.2 Minor Changes

Minor Changes (MCs) are defined as changes in the managed assets that do not impact the community. These changes can for example be:

* Spelling mistakes
* Text improvements
* Reordering of information
* Other minor improvements

#### 1.4.2.1 Process for Minor Changes

The following diagram describes the process for Minor Changes (MCs).

<figure><picture><source srcset="../.gitbook/assets/251117 drawio - security rfc-Minor changes dark mode.drawio (2).svg" media="(prefers-color-scheme: dark)"><img src="../.gitbook/assets/251117 drawio - security rfc-Minor changes.drawio (3).svg" alt=""></picture><figcaption></figcaption></figure>

Roughly the MC transitions through the following phases:

{% stepper %}
{% step %}
**Identification**

A stakeholder identifies a potential change and notifies the Product Owner.
{% endstep %}

{% step %}
**Description & Registration**

The stakeholder registers and describes the required MC.
{% endstep %}

{% step %}
**Decision**

The Product Owner decides whether to accept or reject the MC. An MC can be rejected if it does not meet the required criteria and is more appropriately handled as an RfC.&#x20;
{% endstep %}

{% step %}
**Implementation scheduling**

The Product Owner schedules the MC for implementation.
{% endstep %}
{% endstepper %}

#### 1.4.1.2 Templates&#x20;

The MC process is supported by the following templates:

* MC Description \[to be drafted]

### 1.4.3 Release management

The Change Management Process results in a backlog of RfCs and MCs that require implementation. To process this this backlog efficiently, the Release Management Process was created. This process defines the procedures for selecting changes to be implemented and for consolidating those changes into releases (versions).

{% hint style="info" %}
**Version types**&#x20;

The Release Management Process results in two types of version:&#x20;

* **Major new version**: a version that contains changes with potential impact on stakeholders.
* **Minor new version**: a version that contains changes with no or very minimum impact on stakeholders.
{% endhint %}

#### 1.4.3.1 Release process for major versions

The following diagram describes the process for scoping and producing a major version.

<div data-full-width="true"><figure><picture><source srcset="../.gitbook/assets/251117 drawio - security rfc-Release process major versions dark mode.drawio (3).svg" media="(prefers-color-scheme: dark)"><img src="../.gitbook/assets/251117 drawio - security rfc-Release process major versions light mode.drawio (1).svg" alt=""></picture><figcaption></figcaption></figure></div>

The release process for major versions is as follows:

{% stepper %}
{% step %}
**Scoping**

The Product Owner selects the initial scope for the major version by selecting RfCs and MCs from the backlog. The product strategy and/or product roadmap are guidelines for selection.
{% endstep %}

{% step %}
**Informing**

The Product Owner informs stakeholders and the Expert Group and schedules the release scope as a topic for the Architecture Board agenda.
{% endstep %}

{% step %}
**Final scoping**

Based on feedback from the stakeholders, Expert Group and Architecture Board, the Product Owner selects the final release scope for the version and informs the stakeholders and Expert group about the selected scope.
{% endstep %}

{% step %}
**Implementation**

The selected RfCs and MCs are implemented in the assets, leading to a staging version for the next release.
{% endstep %}

{% step %}
**Decision**

The staging version is scheduled for discussion in the Architecture Board. The Architecture Board either decides whether the new major needs more work or whether it can be released. &#x20;
{% endstep %}

{% step %}
**Release**

The major version is released.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
**Timing requirements**

* The minimum time between step 3 (final scoping) and 6 (release) must be **3 months.**
* In special circumstances the Product Owner can decide to follow a fast-track process in which this minimum time requirement is not applicable. The Architecture Board must approve this fast-track process.
{% endhint %}

#### 1.4.3.2 Release process for minor releases

The following diagram describes the process for scoping and producing a minor version.

<div data-full-width="true"><figure><picture><source srcset="../.gitbook/assets/251117 drawio - security rfc-Release process minor releases dark mode.drawio.svg" media="(prefers-color-scheme: dark)"><img src="../.gitbook/assets/251117 drawio - security rfc-Release process minor releases light mode.drawio.svg" alt=""></picture><figcaption></figcaption></figure></div>

The release process for minor versions is as follows:

{% stepper %}
{% step %}
#### Scoping

The Product Owner selects the initial scope for the minor version, by selecting MCs from the backlog.
{% endstep %}

{% step %}
#### Implementation

The selected RfCs and MCs are implemented in the assets.
{% endstep %}

{% step %}
#### Releasing

The major version is released.
{% endstep %}

{% step %}
#### Informing

The Product Owner informs stakeholders about the release.
{% endstep %}
{% endstepper %}

#### 1.4.3.3 Release and version guidelines

{% tabs %}
{% tab title="Release schedule guidelines" %}
The release schedule guidelines for releases of major versions is as follows:

* Maximum release frequency: **quarterly**
* A quarterly release may be skipped if there are no changes with potential impact on stakeholders are selected and implemented

In special circumstances the Product Owner can decide to create an extra major version release using a fast-track release process.

The release schedule guidelines for minor versions is as follows:

* The Product Owner can decide to release minor versions whenever deemed necessary
{% endtab %}

{% tab title="Version numbering" %}
Versions are numbered as follows: x.y.z.

* With every major version, x or y is updated. Updates of x are reserved for major versions that touch the complete or most of the framework. Updates of y are used for other major versions.
* With every minor version, z is updated.
{% endtab %}

{% tab title="Version Deprecation Process" %}
The version deprecation process can be described as follows:&#x20;

* Each major version is marked as _deprecated_ upon the release of a new major version.
* During the 6-month deprecation period, the deprecated version remains available but is no longer actively maintained, except for critical security fixes if necessary.
* After 6 months, the deprecated version reaches End-of-Life (EOL) and is no longer supported.
* Users are encouraged to migrate to the latest major version as soon as possible to ensure continued support and compliance with the standard.
* The Product Owner is responsible for organizing the Version Deprecation Process.
{% endtab %}
{% endtabs %}

### 1.4.4 Roles and responsibilities

The following roles are recognized in the Change and Release Management processes:

<table data-view="cards" data-full-width="true"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><h4>Stakeholder</h4></td><td><p><strong>Description</strong></p><p>Any party involved in BDI as a member, user, IT service provider, or in any other role. </p></td><td><p></p><p><strong>Responsibilities</strong></p><ul><li>Raise RfCs and MCs</li><li>Provide input on RfCs and MCs</li><li>Support in impact analysis</li><li>Implement new versions of the BDI</li></ul></td><td><a href="https://images.unsplash.com/photo-1739298061740-5ed03045b280?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxzdGFrZWhvbGRlcnxlbnwwfHx8fDE3NjQxNDM5ODZ8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1739298061740-5ed03045b280?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxzdGFrZWhvbGRlcnxlbnwwfHx8fDE3NjQxNDM5ODZ8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><h4>Expert Group</h4></td><td><p><strong>Description</strong></p><p>A group of experts, appointed by the Product Owner.</p></td><td><p></p><p><strong>Responsibilities</strong></p><ul><li>Provide input on RfCs and MCs</li><li>Support the Product Owner in preparing advice for the Architecture Board about RfCs and impact analysis</li><li>Provide feedback on selected major version scope</li></ul></td><td><a href="https://images.unsplash.com/photo-1507679799987-c73779587ccf?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxleHBlcnR8ZW58MHx8fHwxNzY0MTQ0MDk0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1507679799987-c73779587ccf?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxleHBlcnR8ZW58MHx8fHwxNzY0MTQ0MDk0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><h4>Architecture Board</h4></td><td><p><strong>Description</strong></p><p>A group of experts responsible for the BDI assets maintained with this Change and Release Management Processes.</p></td><td><p></p><p><strong>Responsibilities</strong></p><ul><li>Decide on incoming RfC requests</li><li>Decide on prepared RfC impact analysis</li><li>Provide feedback on selected major version scope</li><li>Decide on implementation of a prepared major version</li></ul></td><td><a href="https://images.unsplash.com/photo-1431576901776-e539bd916ba2?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxhcmNoaXRlY3R1cmV8ZW58MHx8fHwxNzY0MTQ0MTgxfDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1431576901776-e539bd916ba2?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxhcmNoaXRlY3R1cmV8ZW58MHx8fHwxNzY0MTQ0MTgxfDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><h4>Product Owner</h4></td><td><p><strong>Description</strong></p><p>Person responsible for the management of the BDI and the execution of the Change and Release Management Processes.</p></td><td><p></p><p><strong>Responsibilities</strong></p><ul><li>Raise RfCs and MCs</li><li>Support stakeholders in registering and describing RfCs and MCs</li><li>Register RfCs and MCs</li><li>Organize and prepare Expert Group meetings</li><li>Organize and prepare Architecture Board meetings</li><li>Organize RfC impact analysis</li><li>Organize implementation of RfCs and MCs</li><li>Scope major and minor versions</li><li>Inform stakeholders about version scoping and process feedback</li><li>Decide on scoping and timing of minor releases</li><li>Organize version release process</li><li>Organize version deprecation process</li></ul></td><td><a href="https://images.unsplash.com/flagged/photo-1550946107-8842ae9426db?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxwcm9kdWN0JTIwb3duZXJ8ZW58MHx8fHwxNzY0MTQ0MzI5fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/flagged/photo-1550946107-8842ae9426db?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxwcm9kdWN0JTIwb3duZXJ8ZW58MHx8fHwxNzY0MTQ0MzI5fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

