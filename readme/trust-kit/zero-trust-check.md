# Zero Trust Check & Association Registers

**1 Summary**

The local BDI Association is the foundation of effective and efficient trust management in a perimeter-less, zero-trust environment. Zero-trust principles require that BDI Associations do not trust anyone outside their own members and use all four pillars of trust to assess interactions with others outside of their community:

1\.      Strong social control.

2\.      Legal enforcement.

3\.      Neutral parties.

4\.      Government authorities.

The strong social control pillar is supported by a reputation scheme:

·       Members of the same association are considered trusted insiders.

·       Members of other associations are considered untrusted outsiders at the outset, but that position can change when:

·       A shared reputation scheme builds experience with outsiders.

·       Outsiders that commit themselves to specific legally enforceable rules set by the association, become preferred partners.



**2 Purpose of the building block**

Purpose of this building block is to show where and how, during BDI event transactions and data sharing, a Data Owner can exercise his right for data and trust sovereignty.



**3 Concepts**

The roles of Owner and Consumer are not fixed but are only valid during a single transaction and switch back and forth as the data flows between the parties.

&#x20;In the BDI implementation the Data Owner can set the specific access rights the Data Consumer has according to several principles:

·       The Data Owner decides which identification, authentication and authorization is needed for the Data Consumer to access the Owners data.

·       A Data Owner can set his authorizations as broad access rights at the beginning of joining the Data Space. Or he can use a much more fine-grained approach by setting and testing those rights for every transaction, per Consumer, per data element. This is up to the Data Owner. The BDI only supplies the mechanisms for these settings.

·       For the Data Owner to authorize a Data Consumer, the Data Consumer needs to be an identified member of the Association.

·       There can be an established level of trust between members of the same Association. Still the trust sovereignty principle leaves the Data Owner completely free to define his own additional levels and access rights.

&#x20;

**4 Implementation Considerations**

&#x20;By choosing how to implement this, there are a few considerations to take into account:

·       Fine grained trust settings are best achieved in combination with publish and subscribe delivery models. This is because in these models the data is not shared before checking and authorization has taken place.

·       Fine grained trust settings can generate much more transaction overhead then a-priori broad settings. In a number of use cases, depending on the level of trust between existing trading partners, full zero-trust checking can be overkill. The business value for using fine grained zero-trust, must be in line with the extra effort for implementation and the extra operation costs.

·       It is possible to develop from no-trust checking messaging, towards zero-trust publish and subscribe. In a lot of use case, zero-trust and publish-subscribe will not be functionally visible for users.

&#x20;The trade-off between security and Trust Sovereignty on one hand, and ease of use plus interoperability on the other hand needs to be made explicit. For example: for interoperability a shared reference database of participants in Data Space may seem like a good idea, but this may give bad actors (drugs trafficking, state actors) too much information about the possibilities of attacking a supply chain. The same applies to common code: ease of implementation versus creating an attractive attack vector is a trade-off.

&#x20;

**5 Interlinkages with other building blocks**

&#x20;Since zero-trust checks can occur as part of an Event Publish and Subscribe chain, that building block is relevant here.

&#x20;See the sections Identity, Authentication and Authorization for further detail. iSHARE is the mechanism used to set and check the zero-trust mechanism.

&#x20;

**6 Elements and their key functions**

&#x20;See the iSHARE framework sections for more details.



&#x20;**7 Core design decisions**

&#x20;The core design decisions are part of the iSHARE framework and documentation.

&#x20;

**8 Future topics**

&#x20;

**9 Further reading**

·      [https://bdinetwork.org/framework/trust/](https://bdinetwork.org/framework/trust/)

·       [https://bdinetwork.org/wp-content/uploads/2024/01/TNO-2023-R10610-Report-Considerations-on-data-space-connectors-and-connectivity-protocols.pdf](https://bdinetwork.org/wp-content/uploads/2024/01/TNO-2023-R10610-Report-Considerations-on-data-space-connectors-and-connectivity-protocols.pdf)

·       The BDI Proving Ground “Shared ETA” use case, BDI Architecture Board

·       The BDI “vertrouwede goederenuitgifte” use case, BDI Demo Working Group

·       Basic Data Infrastructure Framework, Key requirements. BDI website

&#x20;
