---
cover:
  light: >-
    https://images.unsplash.com/photo-1521791055366-0d553872125f?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxhZ3JlZW1lbnR8ZW58MHx8fHwxNzY0MTQ4MzM2fDA&ixlib=rb-4.1.0&q=85
  dark: >-
    https://images.unsplash.com/photo-1450101499163-c8848c66ca85?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxhZ3JlZW1lbnR8ZW58MHx8fHwxNzY0MTQ4MzM2fDA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 488
---

# 📄 Onboarding Terms and Conditions (Suus)

## 1. Introduction

### 1.1 Purpose&#x20;

This building block guides organizations to establish a form of governance for their data exchange activities in accordance with the BDI framework. This building block provides reasons and options to establish this governance.

## 3. Concepts

Some relevant concepts for the BDI onboarding are given below.&#x20;

<details>

<summary>Perimeterless trust</summary>

The BDI framework emphasizes perimeterless trust, allowing each data owner to determine who they trust. Trust registers and identity mechanisms are both local and adaptable, offering flexibility in interoperability and endpoint discovery.

</details>

<details>

<summary>No overarching authority</summary>

There is no overarching authority to enforce the certification of interfaces, manage onboarding processes, or ensure adherence to data licenses. Compliance within the BDI framework is entirely voluntary, motivated by the practical benefits and business value it offers. The framework supports varying global and local adaptations in identity verification and trust levels.

</details>

<details>

<summary>Registers of trusted entities</summary>

Registers of trusted entities are typically local or individual. For example, a platform or company may maintain its own register of trusted partners. If the need for interoperability within a group grows, a common register can be established, often through a BDI Association. (Association Register).

</details>

<details>

<summary>Federated identity mechanism</summary>

The BDI framework provides a federated mechanism for previously unknown entities to identify themselves to a data-owning party. This allows the data owner to verify the entity’s claims and decide whether sufficient trust exists to proceed with the interaction.

</details>

<details>

<summary>Governance recommendations</summary>

Although it is possible to start without any governance structure, it is recommended but not required to develop a formal governance structure per group of entities that share common agreements, terms and conditions, policies, data licenses, semantics of events, trust scores and so on.

A “Group of groups” as an overarching governance structure may also be a beneficial option to consider.&#x20;

</details>

### 3.1 BDI Association

A BDI Association is a local entity formed by a group of participants within the framework. The legal structure of an Association can vary, as it could for example be a foundation or cooperative. Irrespective of its legal structure, the Association serves as the operational anchor for both federated trust/authentication and local onboarding within the BDI Framework. Members of a BDI Association can engage in multiple sectors and data exchanges, participating in dynamic virtual networks composed of members from different Associations. These networks operate on zero-trust principles (see ...), treating members from other Associations as untrusted by default until trust is established.

#### **Local nature**

The local nature of BDI Associations is important, but associations are not by definition local. Some arguments for the importance of this local nature are the following:&#x20;

* Trust and reputation are often tied to proximity and frequency of interaction. The economic gravity-effect shows that geographical proximity has a causal relationship with the level of trade.
* Legal systems tend to be **national or trade-bloc dependent,** making localized Associations more effective in managing trust and reputation within these frameworks.
* The local BDI Association can be the foundation of effective and efficient trust management in a perimeterless, zero-trust environment.&#x20;

#### BDI Framework

* The BDI Framework assumes that many associations are formed and changed, split or merged in a natural manner, as their members see fit.
* The BDI framework defines how federated trust, federated reputation and federated authentication are created spanning multiple associations.

### 3.2 Efficient trust management

{% hint style="warning" %}
**Zero-trust principles** mean that BDI Associations do not trust anyone outside their own members and use all four pillars of trust to assess interactions with others outside of their community.
{% endhint %}

The strong social control pillar is supported by a reputation scheme:

* Members of the same association are considered trusted insiders.
* Members of other associations are considered untrusted outsiders at the outset, but that position can change when:
  * a shared reputation scheme builds experience with outsiders,
  * outsiders that commit themselves to specific legally enforceable rules set by the association become preferred partners,
  * other (sister-)associations can have a trust score, starting with verification of public key ownership of the sister-association.&#x20;

### 3.3 Onboarding

It is recommended that an onboarding mechanism is introduced for new members, if the Association desires to raise the standards for its members.

The following aspects can be taken into consideration:

* vetting the member
* checking roles the member wants to fulfil
* verifying credentials and certificates (trust chain)
* verifying that legal contracts are signed by functionaries with a mandate
* verifying the compliance and security of the IT applications they use (conformity tests)

The result of onboarding is an entry in the local Association Register.

### 3.4 Coherent security

The registrations stored in the Association Register need to be secured against tampering. The process outlined in this section reduces the possibility of attack vectors directed to the staff of the Association Administration (social engineering, blackmail etc.), the most common attack vector in these cases.

The following steps apply to new registrations, updates to registrations and depreciation.

{% stepper %}
{% step %}
#### Prepare

A complete set of attributes is prepared; for updates, this includes all data in the registration (including any attributes that haven't changed).

During preparation attributes can be added, removed and modified freely. Ideally, there is a way to validate the dataset during preparation, but it must be possible to work with intermediate/incomplete data until submitting for verification
{% endstep %}

{% step %}
#### Verify

Verification is an automated process.

Once submitted for verification the dataset is kept immutable; it must not be possible to change datasets during or after verification. If changes have to be made they will be fully re-submitted and follow the full prepare/verify/commit process.

Once the verification stage is completed, it can be queued for commit.
{% endstep %}

{% step %}
#### Commit & sign

Once verified, the Association Functionary will also do any non-automated checks, for instance checking the (digital) signature on any signed documents provided.

The Association Functionary cannot change the submission. The only possible actions are "reject" or "commit" or “deprecate” an already committed submission.

It is a requirement that non-repudiation of the action taken by the Association Functionary is supported.

Only a commit will add, update or modify the registration in the Association Register. If changes are not committed, they do not affect the Register.
{% endstep %}
{% endstepper %}

Shared terms and conditions, data access policies, and data licenses are essential for enhancing interoperability within the BDI Framework.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Terms and Conditions</strong></td><td>These define standardized contractual clauses, such as Edge Agreements, which are localized terms that improve operational efficiency.</td><td><a href="https://images.unsplash.com/photo-1562654501-a0ccc0fc3fb1?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxydWxlc3xlbnwwfHx8fDE3NjQxMjUyMjV8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1562654501-a0ccc0fc3fb1?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxydWxlc3xlbnwwfHx8fDE3NjQxMjUyMjV8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Policies</strong></td><td>Data access is authorized by the Data Owner based on the role of the requesting party. Standardizing these policies within a sector can reduce the management burden.</td><td><a href="https://images.unsplash.com/photo-1564189218077-da13d6c81f25?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxwb2xpY2llc3xlbnwwfHx8fDE3NjQxNTkwMjZ8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1564189218077-da13d6c81f25?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxwb2xpY2llc3xlbnwwfHx8fDE3NjQxNTkwMjZ8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Data licenses</strong></td><td>These define the rights and responsibilities of parties accessing data. For example, an e-commerce transporter may be prohibited from retaining or reusing receiver data. Data licenses can be legally enforceable if included in the onboarding process.</td><td><a href="https://images.unsplash.com/photo-1593871097805-09627f52f4bb?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw4fHxsaWNlbnNlfGVufDB8fHx8MTc2NDE1OTA1Mnww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1593871097805-09627f52f4bb?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw4fHxsaWNlbnNlfGVufDB8fHx8MTc2NDE1OTA1Mnww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

## 4. Core design decisions

The implementation of the BDI Framework should consider existing sector-specific terms, conditions, and practices. Many trade and standardization organizations are transitioning from paper-based practices to digital ones. It is recommended to build upon the existing body of knowledge and trade practices, per sector.

## 5. Interactions with other building blocks&#x20;

* Terms and Conditions
* Policies
* Edge Agreements
* Data Licenses
