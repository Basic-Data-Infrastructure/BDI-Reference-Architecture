---
cover: >-
  https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxwb2xpY3l8ZW58MHx8fHwxNzY0NzY4MDkyfDA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 505
---

# Policy Agreements

## 1. Purpose of the building block

Policies in the BDI are common agreements about authorization of access to data elements. Friction, management costs, delays and (legal) uncertainty can be reduced by a standardization of the following elements:&#x20;

* Common roles
* Data access policies&#x20;
* “Need-to-know” limitations
* Rights and obligations on how the data may be used

## 2. Concepts

### 2.1. Common Roles

Common roles define operational responsibilities within supply chains, helping to create standardized policies — particularly **Data Access Policies**. Each specific sector (type of cargo, modality) has common roles that are well understood and recognized. The same applies to the data elements that a role needs to have access to in order to be able to perform a task.

Defining these common roles — e.g. truck driver, customs agents, inspection agent, forwarder, terminal planner, etc. — reduces the cost of interactions between entities. An undefined role needs custom definitions for the combination role-data access policy, which may be a labor-intensive action. Managing access rights is simplified by standardization.

### 2.2 Data Access policies

Data access policies define who or which role can access specific data elements  under what conditions. Common roles are linked to common data access policies, and a data access policy can be linked to a person: this is a specific authorization.

### 2.3 Data Licenses

Data licenses define the rights and responsibilities of a party that gains access to data. These licenses address whether the data can be retained, reused, or shared with third parties. For example, in the e-commerce sector a data license might stipulate that a transporter delivering packages cannot store, reuse, or resell the recipient’s personal information, including their name, address, email, phone number, or the type of goods delivered. Data licenses regulate the permissible actions and behaviors related to the use of the accessed data to ensure that control over the data is maintained even after it has left the trust boundaries of the data owner.

For a specific sector or geography one can either develop specific data licenses, or reuse common global data ones.&#x20;

## 3. Interlinkages with other building blocks

<a href="digital-identity/" class="button secondary">Digital Identity</a>  <a href="authorisation-oauth-2.0-ar-dm-+-xacml-policies.md" class="button secondary">Authorization</a>  <a href="authentication/" class="button secondary">Authentication</a>  <a href="onboarding-t-and-cs-association-articles.md" class="button secondary">Onboarding Terms and Conditions</a>

## 4. Core design decisions

When starting an association, it is advisable to establish a set of policies beforehand. These policies should be developed across three layers, all of which need to be considered:

{% stepper %}
{% step %}
### Association-specific

These agreements are tailored to meet the unique needs of the association, which may vary by sector, geographical location, or specific theme.
{% endstep %}

{% step %}
### Common

One can utilize the standardized set of edge agreements available in the BDI repository. For instance, the set of data licenses which are described by iShare.
{% endstep %}

{% step %}
### Global

It is advised to align policies with those used in other sectors and standards whenever possible, promoting convergence and consistency.
{% endstep %}
{% endstepper %}

## 5. Further reading

* [https://dev.ishare.eu/reference/delegation-mask/policy-sets](https://dev.ishare.eu/reference/delegation-mask/policy-sets)
* [https://framework.ishare.eu/detailed-descriptions/functional/licenses](https://framework.ishare.eu/detailed-descriptions/functional/licenses)
