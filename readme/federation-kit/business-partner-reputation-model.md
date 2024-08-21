# Business Partner Reputation Model

### Summary

In the BDI network, a reputation system within a BDI Association is integral for assessing the trustworthiness of visitors or outsiders: members of another BDI Association. While the BDI facilitates digital communication among a network of BDI Associations, establishing trust within a BDI Association through mutual agreements is relatively straightforward. However, evaluating the trustworthiness of participants in other BDI Associations can pose a challenge. Although the core trust framework in the BDI provides a foundation for determining trust, additional systems are necessary to enhance trust evaluation for external data sharing. Consequently, the BDI introduces a reputation system to enable more nuanced trust judgments.

### Purpose of the building block

The local dataspace association can be seen as the “in-group” where proximity, high frequency of interaction and strong social control are dominant in how trust is founded. This is backed by legal enforcement (contracts), a neutral organization (association) and possibly government authorities.

Interactions with members of the “in-group” need relatively minor additional trust assessments per interaction. On the other hand, interactions with members outside the association require an additional layer to base trust upon since interaction is less frequent or incidentally.

Members that want to interact with “in-group” members are classified as either a “visitor”, where the member has frequent interactions with members of the associations or as a “outsider”, where the member only has occasional interactions with members of the association.

The Business Partner Reputation Model proposes a system where “in-group” members score members outside the association. Thus a reputation system is created that can help other members of the same association the better determine the trust of the relevant party.

“visitors” can finally become members if they are allowed to by the association administer. &#x20;

The association is the core neutral organization that supports the members of the “in-group” in dealing efficiently with trust-assessment in a perimeterless network. Trust Sovereignty means that the association does not make trust decisions for members, unless specifically tasked to do so. In principle, the Data Owner makes this decision (delegated or not to the data service provider).

### Implementation Considerations&#x20;



### Interlinkages with other building blocks

* Authentication: Authentication out of group members
* Digital Identity: An additional layer to verify trust worthiness of digital identity
* Zero Trust Check: An additional layer to verify trust worthiness of digital identity
* Certified Roles:
* Federation of Associations: especially implemented when dealing cross associations
* Verifiable Credentials: this is future work;

### Elements and their key functions

Reputation registers where the reputation of visitors and outsiders are stored and maintained.

### Core design decisions

* Are the reputations stored decentrally or with a central party within the BDI Association?
* Optional component of a BDI Association?
* Are the ratings visible outside the BDI Association?

### Future topics

This building block is still highly conceptual and gives a first consideration on how to implement a reputation system. Further things to consider are:

* How often can a member review a visitor or outsider?
* How are ratings automated?
* Is the rating system for data exchange with one BDI Association only or is it federated with other BDI Associations?
* Can organizations complain / request withdrawal of ratings & rating comments (e.g. based on false motives like competition libel
* Options for blacklist

### Further reading

https://bdinetwork.org/wp-content/uploads/2024/01/2024-BDI-Reputation-System.pdf

&#x20;
