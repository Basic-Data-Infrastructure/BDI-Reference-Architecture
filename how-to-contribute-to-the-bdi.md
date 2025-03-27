---
layout:
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
---

# How to contribute to the BDI

## Introduction

This document describes the BDI Change and Release Management Process for maintaining the BDI Architecture Documentation. As BDI transitions into a maintenance phase, a thorough process for change and release management is becoming increasingly important. With iSHARE's experience maintaining a standard together with a community, BDI has requested iSHARE's support to draft an initial version of a change and release process. This document is the result of that request.

\
This document was prepared on the basis of:

* The Change Management and Release Management processes as defined by iSHARE ([here](https://framework.ishare.eu/detailed-descriptions/operational/operational-processes/change-management#changemanagement-versioningguidelines) and [here](https://changes.ishare.eu/change-management-process))
* An [comparison](https://docs.google.com/document/d/1SlMCAng7Bw1j4XV4tgYxfapdefET5T9YWY0wy7rI9A4/edit?usp=sharing) of the iSHARE processes with BOMOS

\
The processes described in this document are applicable from the date mentioned under [versioning](https://docs.google.com/document/d/1so5MEHZOqBE6Ly3hfvKviYATuM_RmuTj9d3hrhKE8bM/edit?tab=t.0#heading=h.3g7536yxkmr5).

### Relationship between Change and Release Management

The Change Management process describes how changes are formalised and accepted together with the community. This leads to a list of approved changes that have to be implemented and released in the documentation. The Release Management process details how these changes are implemented and released.

### Scope

This procedure applies to the following assets:

* [The BDI Framework documentation](https://bdi.gitbook.io/public)
* [The BDI Developer Portal](https://dev.bdinetwork.org/), including example IT components provided by BDI

Explicitly out of scope are any third party IT components mentioned in the BDI Framework documentation or BDI Developer Portal. These components are subject to their own change and release management processes.

### Core principles

This Change and Release Management Process is defined with the following core principles in mind:

| Title                  | Transparent                                                                                                                                                                                                                               |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Statement              | Everything that happens regarding (potential) changes, decisions and releases is well documented and publicly visible.                                                                                                                    |
| Rationale              | By using a transparent process, stakeholders are expected to have a better trust in the outcome of the process and the involvement of the community & stakeholders throughout the process. This should lead to wider adoption of the BDI. |
| Example implementation | Maintaining all RFCs and MCs in a public Github repository ensures that all stakeholders are able to track progress.                                                                                                                      |

| Title                  | Predictable                                                                                                                                                                                                                                                                               |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Statement              | Careful planning and execution of releases and version deprecation should lead to a predictable situation for stakeholders.                                                                                                                                                               |
| Rationale              | Adoption of the BDI means implementation in technical products, contracts and possibly other assets. Maintaining these assets is costly for stakeholders. A predictable version, release and version deprecation process should lead to a manageable impact of changes for stakeholders.  |
| Example implementation | Designing and holding to a release schedule of a certain amount of major releases per year ensures that stakeholders are able to plan required capacity ahead.                                                                                                                            |

### Change Management

A change can be either a Request for Change (RFC) or a Minor Change, the difference being the impact of the change to the community.

### Request for Changes

The Change Management Process is designed around Request For Changes (RFCs). RFCs and the Change Management Process are only relevant for changes that have an impact on the community. Other changes that have no impact on the community are treated as Minor Change (MC).

### Process for RFCs

The following diagram describes the process for managing RFCs.

<figure><img src=".gitbook/assets/BDI Change and Release Management.jpg" alt=""><figcaption></figcaption></figure>

Roughly the RFC transitions through the following phases:

\


1. Identification: a stakeholder (could be the BDI Product Owner itself) identifies a required change or opportunity for improvement, altering legislation requires changes, technological advancements require changes, etc..
2. Registration: the stakeholder (if required, supported by the Product Owner) describes the RFC and registers it.
3. Discuss: the Product Owner discusses the RFC with the Expert Group. The Expert Group and Product Owner formulate an advice on the RFC for the Architecture Board.
4. Decision: the Architecture Board decides whether or not to start impact analysis, using the advice received from the Expert Group and Product Owner.
5. Schedule for impact analysis: the Product Owner schedules the RFC for impact analysis.
6. Impact analysis: the Product Owner, supported by the community and the BDI organisation, performs an impact analysis.
7. Discuss: the RFC and the impact analysis are discussed with the Expert Group. The Expert Group and Product owner formulate an advice on the RFC and the impact analysis for the Architecture Board.
8. Decision: the Architecture Board decides whether or not to accept the RFC and schedule it for implementation.
9. Schedule for implementation: the Product Owner schedules the RFC for implementation.

\


The result of the process is an accepted RFC, with a clearly described impact on the framework.

#### Documents for RFCs

The RFC process is supported by the following templates:

\


* RFC Description Template \[to be drafted]
* RFC Impact Analysis Template \[to be drafted]

\


The decision making process is supported by:

\


* RFC Decision Guidelines \[to be drafted]

### Minor Changes

Minor Changes (MCs) are defined as changes in the managed assets that do not impact the community. These changes can for example be:

\


* Spelling mistakes
* Text improvements
* Reordering of information
* Minor other improvements

#### Process for Minor Changes

The following diagram describes the process for Minor Changes (MCs).

<figure><img src=".gitbook/assets/BDI Change and Release Management (1).jpg" alt=""><figcaption></figcaption></figure>

Roughly the MC transitions through the following phases:

\


1. Identification: a stakeholder identifies a potential change and notifies the Product Owner.
2. Describe and register: the stakeholder registers and describes the required MC.
3. Decision: the Product Owner decides whether or not to accept or reject the MC. An MC could be rejected for example because it does not meet the criteria for an MC and should be considered as RFC.
4. Schedule for implementation: the Product Owner schedules the MC for implementation.

#### Templates for MCs

The MC process is supported by the following templates:



* MC Description \[to be drafted]

## Release Management

The Change Management Process results in a backlog of RFCs and MCs that require implementation.



&#x20;The Release Management Process is about selecting changes for implementation and bundling those in releases, called versions.

### Version types

The following two types of versions are defined:

\


* Major new version: a version that contains changes with potential impact on stakeholders.
* Minor new version: a version that contains changes with no or very minimum impact on stakeholders.

### Release process for major versions

The following diagram describes the process for scoping and producing a major version.

\


<figure><img src=".gitbook/assets/BDI Change and Release Management (2).jpg" alt=""><figcaption></figcaption></figure>

The release process for major versions is as follows:

\


1. Scoping: the Product Owner selects the initial scope for the major version, by selecting RFCs and MCs from the backlog. The product strategy and/or product roadmap are guidelines for selection.
2. Inform: the Product Owner informs stakeholders and the Expert Group and schedules the release scope as a topic for the Architecture Board agenda.
3. Final scoping: based on feedback from stakeholders, the Expert Group and the Architecture Board, the Product Owner selects the final release scope for the version and informs stakeholders and the Expert group about the scope.
4. Implement: the selected RFCs and MCs are implemented in the assets, leading to a staging version for the next release.
5. Decision: the staging version is scheduled for discussion in the Architecture Board. The Architecture Board decides to release the new major version, or decides that the release needs more work.
6. Release: The major version is released.

\


Timing requirements:

\


* The minimum time between step 3 (final scoping) and 6 (release) must be 3 months.
* In special circumstances the Product Owner can decide to follow a fast track process in which this minimum time requirement is not applicable. The Architecture Board must approve this fast track process.

### Release process for minor releases

The following diagram describes the process for scoping and producing a minor version.

\


The release process for minor versions is as follows:

\


{% file src=".gitbook/assets/BDI Change and Release Management (3).jpg" %}

1. Scoping: the Product Owner selects the initial scope for the minor version, by selecting MCs from the backlog.
2. Implement: the selected RFCs and MCs are implemented in the assets.
3. Release: The major version is released.
4. Inform: the Product Owner informs stakeholders about the release.

### Release schedule guidelines

The release schedule guidelines for releases of major versions is:

\


* Maximum release frequency: quarterly
* A quarterly release may be skipped if there are no changes with potential impact on stakeholders are selected and implemented

\


In special circumstances the Product Owner can decide to create an extra major version release using a fast track release process.

\


The release schedule guidelines for minor versions is:

\


* The Product Owner can decide to release minor versions whenever deemed necessary

### Version numbering

Versions are numbered as follows: x.y.z.

\


* With every major version, x or y is updated. Updates of x are reserved for major versions that touch the complete or most of the framework. Updates of y are used for other major versions.
* With every minor version, z is updated.

## Version Deprecation Process

* Each major version is marked as deprecated upon the release of a new major version.
* During the 6-month deprecation period, the deprecated version remains available but is no longer actively maintained, except for critical security fixes if necessary.
* After 6 months, the deprecated version reaches End-of-Life (EOL) and is no longer supported.
* Users are encouraged to migrate to the latest major version as soon as possible to ensure continued support and compliance with the standard.
* The Product Owner is responsible for organising the Version Deprecation Process.

## Roles and responsibilities

The following roles are recognised in the Change and Release Management processes:

\


| Role               | Description                                                                                                        | Responsibilities                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Stakeholder        | Any party involved in BDI as a member, user, IT service provider, or in any other role.                            | <ul><li>Raise RFCs and MCs</li><li>Provide input on RFCs and MCs</li><li>Support in impact analysis</li><li>Implement new versions of the BDI</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Expert Group       | A group of experts, appointed by the Product Owner.                                                                | <ul><li>Provide input on RFCs and MCs</li><li>Support the Product Owner in preparing advice for the Architecture Board about RFCs and impact analysis</li><li>Provide feedback on selected major version scope</li></ul>                                                                                                                                                                                                                                                                                                                                                                               |
| Architecture Board | A group of experts responsible for the BDI assets maintained with this Change and Release Management Processes.    | <ul><li>Decide on incoming RFC requests</li><li>Decide on prepared RFC impact analysis</li><li>Provide feedback on selected major version scope</li><li>Decide on implementation of a prepared major version</li></ul>                                                                                                                                                                                                                                                                                                                                                                                 |
| Product Owner      | Person responsible for the management of the BDI and the execution of the Change and Release Management Processes. | <ul><li>Raise RFCs and MCs</li><li>Support stakeholders in registering and describing RFCs and MCs</li><li>Register RFCs and MCs</li><li>Organise and prepare Expert Group meetings</li><li>Organise and prepare Architecture Board meetings</li><li>Organise RFC impact analysis</li><li>Organise implementation of RFCs and MCs</li><li>Scope major and minor versions</li><li>Inform stakeholders about version scoping and process feedback</li><li>Decide on scoping and timing of minor releases</li><li>Organise version release process</li><li>Organise version deprecation process</li></ul> |
