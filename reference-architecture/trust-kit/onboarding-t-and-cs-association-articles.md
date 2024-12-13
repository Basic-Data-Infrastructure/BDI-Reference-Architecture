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

# Onboarding Terms and Conditions

### 1. Summary

### 2. Purpose of the building block

{% hint style="info" %}
This building block guides organizations to establish a form of governance for their data exchange activities in accordance with the BDI framework. This building block provides reasons and options to establish this governance.
{% endhint %}

### 3. Concepts

The BDI framework emphasizes perimeterless trust, allowing each data owner to determine whom they trust. Trust registers and identity mechanisms are local and adaptable, offering flexibility in interoperability and endpoint discovery.&#x20;

There is no overarching Authority to enforce the certification of interfaces, manage onboarding processes, or ensure adherence to data licenses. Compliance within the BDI framework is entirely voluntary, motivated by the practical benefits and business value it offers. The framework supports varying global and local adaptations in identity verification and trust levels.&#x20;

Registers of trusted entities are typically local or individual. For example, a platform or company may maintain its own register of trusted partners. If the need for interoperability within a group grows, a common register can be established, often through a BDI Association. (Association Register).&#x20;

The BDI framework provides a federated mechanism for previously unknown entities to identify themselves to a data-owning party. This allows the data owner to verify the entity’s claims and decide whether sufficient trust exists to proceed with the interaction.&#x20;

Although it is possible to start without any governance structure, it is recommended but not required to develop a formal governance structure per group of entities that share common agreements, terms and conditions, policies, data licenses, semantics of events, trust scores and so on.&#x20;

A “Group of groups” as an overarching governance structure may also be beneficial, as an option.&#x20;

#### 3.1. BDI Association&#x20;

A BDI Association is a local entity formed by a group of participants within the framework. The specific legal structure of an Association can vary—it might be a foundation, cooperative, or any other form. The Association serves as the operational anchor for both federated trust/authentication and local onboarding within the BDI Framework.&#x20;

Members of a BDI Association can engage in multiple sectors and data exchanges, participating in dynamic virtual networks composed of members from different Associations. These networks operate on zero-trust principles, treating members from other Associations as untrusted by default until trust is established.&#x20;

The local nature of BDI Associations is important because trust and reputation are often tied to proximity and frequency of interaction. Additionally, legal systems tend to be national or trade-bloc dependent, making localized Associations more effective in managing trust and reputation within these frameworks.&#x20;

The association is most likely (but not by definition) local because :&#x20;

* Trust and reputation are quite sensitive to close proximity and a high frequency of interaction. The economic gravity-effect shows that geographical proximity has a causal relationship with the level of trade.&#x20;
* Legal systems are national and/or trade-bloc dependent&#x20;
  * UK Law and NL/EU law as an example&#x20;

The BDI Framework assumes that many associations are formed and changed, split or merged in a natural manner, as their members see fit.&#x20;

The BDI framework defines how federated trust, federated reputation and federated authentication are created spanning multiple associations.&#x20;

#### 3.2. Efficient trust management&#x20;

The local BDI Association can be the foundation of effective and efficient trust management in a perimeterless, zero-trust environment. Zero-trust principles mean that BDI Associations do not trust anyone outside their own members and use all four pillars of trust to assess interactions with others outside of their community.&#x20;

The strong social control pillar is supported by a reputation scheme:&#x20;

* Members of the same association are considered trusted insiders.&#x20;
* Members of other associations are considered untrusted outsiders at the outset, but that position can change when: &#x20;
  * a shared reputation scheme builds experience with outsiders;&#x20;
  * outsiders that commit themselves to specific legally enforceable rules set by the association become preferred partners&#x20;
  * other (sister-)Associations can have a trust score, starting with verification of public key ownership of the sister Association&#x20;

#### 3.3 Onboarding&#x20;

It is recommended that an onboarding mechanism is introduced for new members, if the Association desires to raise the standards for its members.&#x20;

The following aspects can be taken into consideration:&#x20;

* vetting the member
* checking roles the member wants to fulfil&#x20;
* verifying credentials and certificates (trust chain)&#x20;
* verifying that legal contracts are signed by functionaries with a mandate &#x20;
* verifying the compliance and security of the IT applications they use (conformity tests)&#x20;

The result of onboarding is an entry in the local Association Register.&#x20;

#### &#x20;3.4. Coherent Security&#x20;

The registrations stored in the Association Register need to be secured against tampering. The process outlined in this section reduces the possibility of attack vectors directed to the staff of the Association Administration (social engineering, blackmail etc.), the most common attack vector in these cases.

The following steps apply to new registrations, updates to registrations and depreciation.

<table data-header-hidden><thead><tr><th width="153">Step</th><th>Action</th></tr></thead><tbody><tr><td><strong>Step</strong></td><td><strong>Action</strong></td></tr><tr><td>Prepare </td><td><p>A complete set of attributes is prepared; for updates, this includes all data in the registration (including any attributes that haven't changed). </p><p>During preparation attributes can be added, removed and modified freely. Ideally, there is a way to validate the dataset during preparation, but it must be possible to work with intermediate/incomplete data until submitting for verification </p></td></tr><tr><td>Verify </td><td><p>Verification is an automated process. </p><p>Once submitted for verification the dataset is kept immutable; it must not be possible to change datasets during or after verification. If changes have to be made they will be fully re-submitted and follow the full prepare/verify/commit process. </p><p>Once the verification stage is completed, it can be queued for commit. </p></td></tr><tr><td>Commit &#x26; Sign </td><td><p>Once verified, the Association Functionary will also do any non-automated checks, for instance checking the (digital) signature on any signed documents provided. </p><p>The Association Functionary cannot change the submission. The only possible actions are "reject" or "commit" or “deprecate” an already committed submission. </p><p>It is a requirement that non-repudiation of the action taken by the Association Functionary is supported. </p><p>Only a commit will add, update or modify the registration in the Association Register. If changes are not committed, they do not affect the Register. </p></td></tr></tbody></table>

Shared terms and conditions, data access policies, and data licenses are essential for enhancing interoperability within the BDI Framework.&#x20;

* _Terms and Conditions_: These define standardized contractual clauses, such as Edge Agreements, which are localized terms that improve operational efficiency.&#x20;
* _Policies_: Data access is authorized by the Data Owner based on the role of the requesting party. Standardizing these policies within a sector can reduce the management burden.&#x20;
* _Data Licenses_: These define the rights and responsibilities of parties accessing data. For example, an e-commerce transporter may be prohibited from retaining or reusing receiver data. Data licenses can be legally enforceable if included in the onboarding process.&#x20;

### 5. Core design  decisions

The implementation of the BDI Framework should consider existing sector-specific terms, conditions, and practices. Many trade and standardization organizations are transitioning from paper-based practices to digital ones. It is recommended to build upon the existing body of knowledge and trade practices, per sector.&#x20;

### 6. Interlinkages with other building blocks&#x20;

* Terms and Conditions &#x20;
* Policies&#x20;
* Edge Agreements&#x20;
* Data Licenses

