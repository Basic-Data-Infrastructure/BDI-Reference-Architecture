# Policy agreements

### 1. Summary

### 2. Purpose of the building block

{% hint style="info" %}
Policies in the BDI are common agreements about authorization of access to data elements. Standardization of:

* Common roles
* Access policies for a given role to data elements
* “need to know” limitations
* Rights and obligations on how the data may be used

reduces friction costs, management costs, delays and (legal) uncertainty.
{% endhint %}

### 3. Concepts

#### 3.1. Common Roles

Common roles define operational responsibilities within supply chains, helping to create standardized policies, particularly Data Access Policies.

Each specific sector (type of cargo, modality) has common roles that are well understood and recognized. The same applies to data elements that a role needs to have access to, in order to be able to perform a task.

Defining these common roles (like truck driver, customs agents, inspection agent, forwarder, terminal planner, etc. etc.) reduces the cost of interactions between entities. An undefined role needs custom definitions for the combination role-data access policy: a labour-intensive action.

Managing access rights is simplified by standardization.

#### 3.2. Data Access policies

Data access policies define who or what role can access specific data elements and under what conditions.

Common roles are linked to common data access policies.

A data access policy can be linked to a person: this is a specific authorization.

#### 3.3. Data Licenses

Data licenses define the rights and responsibilities of a party that gains access to data.

These licenses address questions, such as whether the data can be retained, reused, or shared with third parties. For example, in the e-commerce sector, a data license might stipulate that a transporter delivering packages cannot store, reuse, or resell the recipient’s personal information, including their name, address, email, phone number, or the type of goods delivered. Data licenses, including regulate the permissible actions and behaviours related to the use of the accessed data, ensuring that control over the data is maintained even after it has left the trust boundaries of the data owner.

Common global data licenses may be re-used, or local specific data licenses may be developed that are specific for a sector or geography.

### 4. Interlinkages with other building blocks

* Digital Identity
* Authorization
* Authentication
* Onboarding, Terms and conditions

### 5. Core design decisions

When starting an association, it is advisable to establish a set of policies beforehand. These policies should be developed across three layers, all of which need to be considered:

* _Association-Specific_: These agreements are tailored to meet the unique needs of the association, which may vary by sector, geographical location, or specific theme.
* _Common_: Utilize a standardized set of edge agreements available in the BDI repository. For instance, the set of data licenses which are described by iShare.
* _Global_: Seek to align these policies with those used in other sectors and standards whenever possible, promoting convergence and consistency.

### 6. Further reading

* [https://dev.ishare.eu/reference/delegation-mask/policy-sets](https://dev.ishare.eu/reference/delegation-mask/policy-sets)
* [https://framework.ishare.eu/detailed-descriptions/functional/licenses](https://framework.ishare.eu/detailed-descriptions/functional/licenses)

\\
