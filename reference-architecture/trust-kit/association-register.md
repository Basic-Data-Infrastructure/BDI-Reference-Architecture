# Association Register

## Summary&#x20;

An Association Register is operated by the role of an Association Administrator. The Association Register holds the registration of Associations, Members and the membership of Members of Associations. It in this way supports trust and discoverability.&#x20;

## Purpose of the building block&#x20;

The purpose of the Association Register is:&#x20;

1. To support trust in an Association by keeping a register of trusted members.&#x20;
2. To improve discoverability of Associations and members within and (optionally) across associations. &#x20;

An Association Register is considered a technological solution to facilitate the role of the Association Administrator.&#x20;

## Concepts&#x20;

The following concepts (from the BDI Glossary) are particularly relevant in this building block:&#x20;

<table><thead><tr><th width="262">Concept</th><th>Meaning</th></tr></thead><tbody><tr><td>Association </td><td><p>Legal entity that serves as trust anchor for both federated trust/authentication and local onboarding  </p><p>A BDI Association is the “root Association” for its Members. </p></td></tr><tr><td>Association Administrator </td><td>Functionary responsible for operating the services of a BDI Association. </td></tr><tr><td>Association Register </td><td>Register of onboarded Members. </td></tr><tr><td>Member </td><td>Legal entity as member of a root Association. </td></tr></tbody></table>

<figure><img src="../../.gitbook/assets/image (1).png" alt="" width="563"><figcaption><p>Schematic overview of concepts</p></figcaption></figure>

## Risks

Failure to provide an Association Register, may lead to lack of accountability and liability, reduced collaboration and, consequently, loss of trust. It can also hinder collaboration due to decreased discoverability.

The weak points in the process are:

* The humans fulfilling roles in the branche administration that execute the process
  * Errors, vulnerability for social engineering or external pressure
* The Association Register that maintains the registers on which the automated assessments of credentials (authentication phase) is based
* The correct implementation of the API’s and cryptographic protocols used for interaction with other roles

The human attack vector is considered to be the most threatening: onboarding should therefore be a one-way automated process in three separate steps (see also onboarding T\&Cs Association articles):

* Collecting information (automated and/or manual)
* Verifying information and test trust chain (automated)
* Committing to the register (manual)

## Interlinkages with other building blocks&#x20;

This building block provides the technical implementation supporting the building block “Onboarding T\&C’s and Association articles”, in which the operational processes and requirements regarding the onboarding of a BDI Association are described. &#x20;

Furthermore it particularly supports the building blocks “Authentication” and “Certified roles” (but not limited to) by providing trust about Members and their roles.

In fact most building blocks will have some form of link with this building block, since the Association Register is a core topic of the BDI.

## Elements and their key functions&#x20;

An Association Register must provide the following key functions:&#x20;

* An Association Administrator can register Members after executing the minimum BDI onboarding process.&#x20;
* An Association Administrator can register membership of a Member of its Association. &#x20;
* An Association Administrator can deregister a Member, for instance when the Member requires it to do so, when a membership expires, or when a Member is to be excluded from membership due to incompliance.&#x20;
* An Association can deregister Membership of a Member of its Association.&#x20;
* Members can use the Association Register to assess the trust of another member and to retrieve information about Members (in for instance what roles they fulfill).&#x20;
* Members can use the Association Register to discover which Association are available and which Members are Member of an Association (if the Association chooses to publish this).&#x20;

## Core design decisions&#x20;

The following design decisions form the basis for this building block:&#x20;

* All Association Registers can be connected, so that all Associations and Members are potentially available throughout the connected Association Registers.&#x20;
* Each Member is registered at a primary Association Register (usually operated by the first Association Administrator that onboards the Member).&#x20;
* When Association Administrators register a Member of an Association that is already present as Member of another Association, the existing Member is associated with the Association. The Member is therefore not registered multiple times.&#x20;
* Members are always discoverable to all other Members of Associations that make use of the BDI Framework.&#x20;
* Associations, including the membership of their Members can choose to be discoverable in the BDI Framework.&#x20;
* Association Administrators are required to use Association Registers that can provide the above-described design requirements. BDI maintains a list of compliant Association Registers and might choose to run and maintain a central Association Register.&#x20;

## Future topics&#x20;

To be discovered is how the Association Register can technically support the building block “Business Partner Reputation model”. &#x20;

## Further reading&#x20;

This building block has been drafted using the following sources, that provide opportunity for further reading:&#x20;

* [DSSC Blueprint building block “Participation Management”](https://dssc.eu/space/BVE/357074624/Participation+Management)&#x20;
* [iSHARE Framework documentation](https://framework.ishare.eu/)&#x20;
* [iSHARE Developer Portal documentation](https://dev.ishare.eu/)&#x20;
