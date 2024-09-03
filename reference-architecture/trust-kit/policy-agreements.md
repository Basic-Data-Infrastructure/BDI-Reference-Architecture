# Policy agreements

### Summary

### Purpose of the building block

Policies in the BDI are common agreements about authorization of access to data elements. Standardization of:&#x20;

* Roles &#x20;
* Access policies for a given role to data elements&#x20;
* “need to know” limitations&#x20;
* &#x20;Rights and obligations on how the data may be used&#x20;

reduces friction costs, management costs, delays and (legal) uncertainty.&#x20;

### Concepts

#### Roles&#x20;

Roles define operational responsibilities within supply chains, helping to create standardized policies, particularly Data Access Policies. &#x20;

Each specific sector (type of cargo, modality) has common roles that are well understood and recognized. The same applies to data elements that a role needs to have access to, in order to be able to perform a task.&#x20;

Defining these common roles (like truck driver, customs agents, inspection agent, forwarder, terminal planner, etc. etc.) reduces the cost of interactions between entities. An undefined role needs custom definitions for the combination role-data access policy: a labour-intensive action. &#x20;

Managing access rights is simplified by standardization.&#x20;

#### Data Access policies&#x20;

Data access policies define who or what role can access specific data elements and under what conditions. &#x20;

Common roles are linked to common data access policies.&#x20;

A data access policy can be linked to a person: this is a specific authorization.&#x20;

#### Data Licenses&#x20;

Data licenses define the rights and responsibilities of a party that gains access to data. &#x20;

These licenses address questions, such as whether the data can be retained, reused, or shared with third parties. For example, in the e-commerce sector, a data license might stipulate that a transporter delivering packages cannot store, reuse, or resell the recipient’s personal information, including their name, address, email, phone number, or the type of goods delivered. Data licenses, including regulate the permissible actions and behaviours related to the use of the accessed data, ensuring that control over the data is maintained even after it has left the trust boundaries of the data owner.&#x20;

Common global data licenses may be re-used, or local specific data licenses may be developed that are specific for a sector or geography.&#x20;

### Interlinkages with other building blocks&#x20;

* Digital Identity&#x20;
* Authorization&#x20;
* Authentication&#x20;
* Onboarding, Terms and conditions&#x20;

### Core design decisions&#x20;

When starting an association, it is advisable to establish a set of policies beforehand. These policies should be developed across three layers, all of which need to be considered:&#x20;

* _Association-Specific_: These agreements are tailored to meet the unique needs of the association, which may vary by sector, geographical location, or specific theme. &#x20;
* _Common_: Utilize a standardized set of edge agreements available in the BDI repository. For instance, the set of data licenses which are described by iShare. &#x20;
* _Global_: Seek to align these policies with those used in other sectors and standards whenever possible, promoting convergence and consistency.

### Further reading&#x20;

* [https://dev.ishare.eu/reference/delegation-mask/policy-sets](https://dev.ishare.eu/reference/delegation-mask/policy-sets)&#x20;
* [https://framework.ishare.eu/detailed-descriptions/functional/licenses](https://framework.ishare.eu/detailed-descriptions/functional/licenses) &#x20;

\
