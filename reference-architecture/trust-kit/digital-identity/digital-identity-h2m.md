---
cover: >-
  https://images.unsplash.com/photo-1608499337372-2fea1e07da37?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxodW1hbiUyMG1hY2hpbmUlMjBpbnRlcmFjdGlvbnxlbnwwfHx8fDE3NjQ3NDkwODN8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 374
---

# Digital Identity H2M

## 1. Summary

This building block supports trust among participants by defining how digital identities play a role in BDI in human-to-machine (H2M) interactions.

Digital identifiers for IT-processes acting on behalf of an organization/legal entity are described in Digital Identity (M2M).

## 2. Purpose of the building block

The purpose of this building block is to support the framework for trust in Boundary Management, where humans are acting as a representative of a legal entity by means of (digital) devices and telecommunication.

## 3. Concepts

Boundary Management for humans relates to:

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td>A <strong>human</strong>, acting as <strong>representative</strong> for a <strong>legal entity</strong> desiring access to <strong>data</strong> or an <strong>application</strong> owned/controlled by another legal entity</td><td><em>For example: login to an application</em></td><td><a href="https://images.unsplash.com/photo-1535451801241-b5395e1d4a1b?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxsb2clMjBpbnxlbnwwfHx8fDE3NjQ3NDkyNjF8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1535451801241-b5395e1d4a1b?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxsb2clMjBpbnxlbnwwfHx8fDE3NjQ3NDkyNjF8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td>A <strong>human</strong>, acting as <strong>representative</strong> for a <strong>legal entity</strong> desiring access to a <strong>location</strong> owned/controlled by another legal entity</td><td><em>For example: entering a protected zone</em></td><td><a href="https://images.unsplash.com/photo-1535556572967-276cd0ad5cba?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw4fHxlbnRyYW5jZXxlbnwwfHx8fDE3NjQ3NDkyOTB8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1535556572967-276cd0ad5cba?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw4fHxlbnRyYW5jZXxlbnwwfHx8fDE3NjQ3NDkyOTB8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td>A <strong>human</strong>, acting as <strong>representative</strong> for a <strong>legal entity</strong> involved in <strong>transferring</strong> an asset (cargo) and/or liabilities for the asset between the two legal entities</td><td><em>For example: picking up cargo by a transporter</em></td><td><a href="https://images.unsplash.com/photo-1559297434-fae8a1916a79?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHx0cmFuc3BvcnR8ZW58MHx8fHwxNzY0NzQ5NDE0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1559297434-fae8a1916a79?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHx0cmFuc3BvcnR8ZW58MHx8fHwxNzY0NzQ5NDE0fDA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

This building block ensures that the digital identity of the human involved in (digital) interactions can be authenticated. In addition, it ensures a relation between the digital identity and

* the **Representation evidence**, i.e. _in what role and capacity, on behalf of which legal entity, with a specific mandate_
* the **Professional Qualification** evidence, i.e. _evidence of professional qualifications_

{% hint style="info" %}
The core concept is that **identity** is dynamically related to (potentially multiple concurrent) **representations** for (potentially multiple concurrent) **legal entities**. The legal entity assumes **liability** and **accountability** for actions of the human.
{% endhint %}

### 3.1 Identity

Identity is a legal concept defined by a nation state and assigned to a human by that nation state. Nation States issue Passports and ID-cards to humans which they can use to "prove" their identity. Driving licenses are also used in some states (e.g. the Netherlands) as a proof of identity.

Digital identities are related to that core identity by Identity Providers which are used in B2B processes.

Identity Providers can choose to increase the assurance level of an identity, for example by requesting live verification of an identity paper. This can be done face-to-face or remote. Typically, this is executed once at the initiation of a new identity.

### 3.2 Authentication

Identity Providers can also provide additional assurance at the (continuous) use of the identity, e.g. when a managed boundary must be crossed. The human user can be authenticated by a username, password and an additional 2FA / MFA. More advanced devices can also use biometric identification parameters. Biometric identification can also be used for accessing a physical location. One such example is using the Secure Logistics smart card to access a Terminal.

### 3.3 Identifiers

Identity Providers typically use an internal numbering scheme for identifying users which are enriched with more public identifiers like email addresses and telephone numbers. Some details regarding different identifiers are given below.

{% tabs %}
{% tab title="State-issued identifiers" %}
As mentioned, identity is a legal concept defined by a nation state and assigned to a human by that nation state. State issued identifiers (e.g. the Dutch BSN) are often not allowed to be used outside the Government.
{% endtab %}

{% tab title="Email " %}
In B2B processes, business email addresses are preferred. These should be using an organizational domain name (e.g. @myorganization.com) and a personal prefix (e.g. piet.jansen@ or s.jones@). The use of shared email accounts must be avoided. Also the use of general domains (e.g. @gmail.com) should be avoided. Typically, the user must demonstrate during the setup of the account that she has access to the business email address. This provides additional trust that the user has a business relation with the organization which owns the domain name.
{% endtab %}

{% tab title="Phone numbers" %}
(Mobile) telephone numbers can also be used to identify / verify the user. During the setup the user demonstrates that they have access to the number. At a later moment, the user can once again demonstrate the access to this number.
{% endtab %}

{% tab title="Electronic Wallets" %}
The push for electronic Wallets provides a new means to store and show a digital identity that can be authenticated.
{% endtab %}
{% endtabs %}

### 3.4 Representation

B2B Identity Providers identifies a human user in the context of an organization. Additionally, the role/mandate of the user can be defined at the Identity Provider so it can be used in all connected services. An alternative is that the service itself has local authorizations which must be managed by an administrator of the organization.

Users could represent more than one organization, and there are several approaches Identity Providers can take to manage this scenario. They could for example assign different identities for each of the represented organizations (e.g. applying different business email addresses or issuing separate secure cards per organization). An alternative is that the human user selects the represented organization in each specific use case.

### 3.5 Professional Qualifications

In many cases the human needs to have adequate professional qualifications for the task at hand, such as a professional drivers license, safety training or dangerous goods handling. The B2B Identity Provider could store and share these professional qualifications of the user, for example in an electronic wallet. The qualifications are typically represented as verifiable credentials.

## 4. Risks

Some possible risks that are important to consider for this building block, are the following:

* An insufficient framework for digital identity might lead to a lower level of trust among parties and will harm the overall trust in BDI.
* Non-compliance to applicable privacy laws (e.g. GDPR, AVG) can hamper the implementation or adoption of services and can cause reputation risks or fines.

## 5. Interlinkages with other building blocks

The related building blocks are:

<a href="digital-identity.md" class="button secondary">Digital Identity M2M</a> <a href="../authentication.md" class="button secondary">Authentication M2M</a> <a href="../authentication-h2m.md" class="button secondary">Authentication H2M</a>

<a href="../authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a> <a href="../../../readme/trust-kit/association-register-1.md" class="button secondary">Association Register</a> <a href="../../federation-kit/professional-qualification-register.md" class="button secondary">Professional Qualification Register</a>

<a href="../../federation-kit/representation-register.md" class="button secondary">Representation Chain</a>&#x20;

The most important related Kits and concepts are:

<a href="../" class="button secondary">Trust KIT</a> <a href="../../federation-kit/" class="button secondary">Federation KIT</a> <a href="../../boundary-management-kit/" class="button secondary">Boundary Management</a>

## 6. Core design decisions

Please note the following design decisions:

* Parties choose their Identity Providers fitting to the requirements.
* The BDI adds the link to representation and professional qualifications.
* In Europe the eIDAS regulation is a solid foundation for the identity ecosystem.
* Self-signed certificates for digital identities are a low-barrier entry level solution, with serious limitations on trust, federation and scaling.
