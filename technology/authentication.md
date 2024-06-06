# Authentication

Authentication is the process or action of proving or showing something to be true, genuine, or valid.

Before Authentication Identification is required. A trusted Identity is validated in the (Federated) Association Register for the Data Service Provider to authorize the Service Consumer access to the source.

For Authentication between parties of the same Association the OAuth 2.0 protocol for authenticating parties and providing access tokens is used when requesting access to a service within BDI. This standard provides secure delegated access. However in OAuth 2.0 it is assumed that clients are pre-registered. In the BDI participants have the option to interact with previously unknown clients this is not a satisfying solution on it's own.

Therefor the BDI adopts the [iSHARE OAuth specifications](https://ishareworks.atlassian.net/wiki/spaces/IS/pages/75235411/OAuth+2.0) as iSHARE facilitates an ecosystem within which parties can interact with previously unknown parties, pre-registration is therefore not a prerequisite and thus requires alterations to the official standard OAuth standard.

There are 2 [Identification ](digital-identity.md)trusted sourced support by the the BDI scheme:

1. **iSHARE whitelisted** [**PKI**](https://ishareworks.atlassian.net/wiki/spaces/IS/pages/70222163/PKI) **certificates.** For authentication purposes, iSHARE requires parties to acquire an X.509 certificate which is distributed by a trusted root under certain PKIs (Public Key Infrastructure). For interoperability on a European scale, all trusted roots under the eIDAS regulation are trusted issuers. This is a secure level starting defined as '[eIDAS substantial](https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/eIDAS+Levels+of+Assurance)'.
2. BDI Association signed X.509 certificates. This credential is issued by the trusted association to it's members as a result of onboarding and maintained to the agreed lifecycle requirements. This credential is endorsed by the association members and federated associations.&#x20;



## Federated Authentication

In the BDI network, a [reputation system](business-partner-reputation-model.md) within a BDI Association is integral for assessing the trustworthiness of visitors or outsiders: members of another BDI Association. While the BDI facilitates digital communication among a network of BDI Associations, establishing trust within a BDI Association through mutual agreements is relatively straightforward. However, evaluating the trustworthiness of participants in other BDI Associations can pose a challenge.

A federation trust is designed to enable efficient and secure online transactions between business partners. Trust to engage between parties is most often based on more attestations agreed between parties and/or assocation they are member of. The service provider can then make [authorization ](authorization.md)decisions based on te information on behalf of the data owner.

When a requests from a member of association A is directed to access data of a member of association B the request is redirected to the association's B attestation service to validate the federated trust artifacts available with the requestor association. These attestations help decide the authentication response of the data provider and authorization conditions applied on behalf the data owner. Note: Emphasizing '_helps decid_e' as the Trust Sovereignty principle is kept by allowing the assessment against the policies of the data owner to determine authorization. The owner might want to provide the data service to the requestor that has a low(er) level of attestations.

The concept for the [association ](federation-of-associations.md)is to adopt the framework standards with it's members to achieve a goal (benefits outweigh the costs). Add local specifics, ratify common standards across associations, evolve and so on.



### Implementation Considerations&#x20;

* Is your collaboration with other parties mostly within a trusted group an relatively static? Association assigned X.509 might suffice
* Are the interaction partners varying and expted frequent to be outside of the direct known parties? Government-issued Identities provide a built in level of trust to start of on.

### Interlinkages with other building blocks

* Authorization: Access rights to data
* Digital Identity: An additional layer to verify trust worthiness of digital identity
* Zero Trust Check: An additional layer to verify trust worthiness of digital identity
* Federation of Associations: especially implemented when dealing cross associations
* Verifiable Credentials: this is future work;

### Elements and their key functions

&#x20;

### Core design decisions

* &#x20;

### Future topics

&#x20;

