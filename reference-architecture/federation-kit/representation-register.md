# Representation Register



**Summary**&#x20;

To be done&#x20;

**Purpose**&#x20;

The Representation Register registers mandates in the form of Representation Evidence given to natural persons, legal entities or governmental bodies that act on behalf of a data owner or data consumer.&#x20;

The Representation Register registers mandates given to natural persons, legal entities or governmental bodies that act on behalf of a data owner or data consumer. A mandate is a record of permission by an [authoritative](https://en.wiktionary.org/wiki/authoritative#English) [command](https://en.wiktionary.org/wiki/command#English) (mandator) provided to whom a mandate is assigned (mandatee)

For Business to Business interactions where a Legal Person can relate another Legal Person to act on its behalf using a different service provider. This can be the case when a Legal person contracts other organisations to execute a contract on its behalf. &#x20;

The purpose in Business to Business interactions is to accommodate where a [Legal Person](https://en.wikipedia.org/wiki/Legal\_person) can mandate another Legal Person to act on its behalf using a different service provider. This can be the case when a Legal Person contracts another organisations to execute a contract on its behalf. &#x20;

For H2M interactions where a Natural Person uses a Service of a Service Provider (e.g. via a web interface) of a Natural Person, the Representation Register relates the Natural Persons to Legal Persons and therefore defines if a Natural Person can act on behalf of a Legal Person or governmental body. However, also use cases with physical access could be considered (e.g. collection of goods, access to a location).&#x20;

For H2M interactions where a Natural Person uses a Service of a Service Provider (e.g. via a web interface) of a Natural Person, the Representation Register relates the Natural Persons to Legal Persons and therefore defines if a Natural Person can act on behalf of a Legal Person or governmental body. However, also use cases with physical access could be considered (e.g. collection of goods, access to a location).

**<< insert picture >>**

A Natural Person could be an employee of the Legal Person or governmental body (e.g. a Company) but it could also be the owner of the Legal Person or an external Natural Person which is empowered to represent the Legal Person for specific use cases (e.g. an external accountant).&#x20;

&#x20;

The Representation Register relates Natural Persons to Legal Persons and therefore defines if a Natural Person can act in behalf of a Legal Person. This is primary used in (remote) H2M interactions where a Natural Person uses a Service of Service Provider (e.g. via a web interface). However, also use cases with physical access could be considered (e.g. collection of goods, access to a location).&#x20;

A Natural Person could be an employee of the Legal Person (e.g. a Company) but it could also be the owner of the Legal Person or an external Natural Person that is empowered to represent the Legal Person for specific use cases (e.g. an external accountant).&#x20;

A Natural Person could be an employee of the Legal Person (e.g. a Company) but it could also be the owner of the Legal Person or an external Natural Person which is empowered to represent the Legal Person for specific use cases (e.g. an external accountant).&#x20;



Relationship to other Building Block&#x20;

The Representation Register is (directly or indirectly) used by the following Building Blocks:&#x20;

* Authentication: applicable for H2M Use Cases&#x20;
* Authorisation: applicable for H2M Use Cases&#x20;
* Digital Identity: to be checked if this relates to both the Roles of Legal Entities and / or Natural Persons&#x20;
* Zero Trust Check: applicable for H2M Use Cases&#x20;
* Certified Roles: to be checked if this relates to both the Roles of Legal Entities and / or Natural Persons&#x20;
* Professional Qualification Register: this registers the professional qualifications of Natural Persons. &#x20;
* Verifiable Credentials: this is future work; also reference to the planned iSHARE RFC on Verifiable Credentials
* (Federation of) Association(s): Validity of the Representation Evidence provided is only applicable if the Digital Identity can be related to a Legal Person part of the same (Federation of) Association(s) &#x20;

Elements & core Functions&#x20;

* the representation mandate of authenticated natural persons acting of behalf of the legal person or governmental body;&#x20;
* the representation mandate of organizations (sub-contractors) acting on behalf of the data owner;&#x20;
* the standardized roles the data owner’s organization supports.&#x20;

&#x20;

The DSCC Blueprint has no direct related Building Block for the Representation Register. The Representation Register must be able to issue credentials which represent the relationship between Natural Persons and Legal Persons. It mentions the example of the technical specification of GAIA-X which defines this as a Legal Person Party Credential. iSHARE also uses the term Party Credentials. &#x20;

TO BE VALIDATED: IF THIS IS ALSO USED FOR LEGAL PERSONS WITHIN ISHARE&#x20;

Examples of existing Representation Registers include:&#x20;

* Internal Representation Registers within a Legal Person related to IAM processes. Office 365 is widely used which uses Microsoft Entra (AAD) as a “Directory” of natural persons with email addresses, etc. But also other solution are available an used. The best practice is to use this as the “Golden Truth” of the Representation Register for the Legal Person.&#x20;
* E-Herkenning which is the Dutch B2B eIDAS  Framework. Note that most other European countries don’t have a similar Framework&#x20;
* Other external Identity Providers which Federate with Service Providers. Examples include Secure Logistics XSid and Portbase IAMconnected&#x20;
* Representation Register within a Service Provider&#x20;

Best Practices for Digital Access&#x20;

Use E-Herkenning for Dutch (only) Data Spaces.&#x20;

Federate the Service Provider Representation Register with the Internal Presentation Register of the Legal Entity. This enables Single Sign On for the natural person (ease of use) an increases the security (connecting to the Joiner / Mover / Leaver process of the Legal Person). &#x20;

Federate the Service Provider Representation Register with an External Identity Provider. This can be considered if the External Identity Provider overlaps with the (target) groups of the Service Provider.&#x20;

Best Practices for Physical Access&#x20;

Smart Card Solutions like the Secure Logistics Cargo Card and the Smart LOXS Cargo Card.&#x20;

App / Wallet based solutions on Smartphones.&#x20;

Notes / outstanding actions&#x20;

Note on Authorisations.&#x20;

Note on current iSHARE Approach and limitations&#x20;

Note on relation with iSHARE RFC on VC’s&#x20;

Note on European Wallet perspective (Future Versions)&#x20;

&#x20;

Core Design Systems&#x20;

&#x20;

Functional Specifications&#x20;

&#x20;

Recommended Standards&#x20;

&#x20;

Technical Specifications&#x20;

Future Versions&#x20;

Explore & Align with the DSCC approach for attestations based on verifiable credentials. eIDAS 2.0 will require Member States to provide citizens, upon their request, with a notified European Digital Identity Wallet (EDIW). It also addresses Legal Persons. &#x20;

&#x20;

Further Reading&#x20;

&#x20;

* DSSC Building Block&#x20;
* TNO Report on Verifiable Credentials&#x20;
* iSHARE References&#x20;

&#x20;

&#x20;

NOTES (NOT FOR EXTERNAL PUBLICATION)&#x20;

&#x20;

&#x20;

Reviewers:&#x20;

* DIL&#x20;
* Portbase&#x20;
* iSHARE&#x20;
* Secure Logistics&#x20;
* E-Herkenning partijen è Digidentity, KPN, &#x20;
* KVK&#x20;
* Ondernemingspaspoort&#x20;

&#x20;

REPRESENTATION REGISTER&#x20;

&#x20;

Summary&#x20;

To be done&#x20;

Purpose&#x20;

The Representation Register registers mandates given to natural persons, legal entities or governmental bodies that act on behalf of a data owner or data consumer.&#x20;

For Business to Business interactions where a Legal Person can relate another Legal Person to act on its behalf using a different service provider. This can be the case when a Legal person contracts another organisations to execute a contract on his behalf. &#x20;

For H2M interactions where a Natural Person uses a Service of a Service Provider (e.g. via a web interface) of a Natural Person, The Representation Register relates the Natural Persons to Legal Persons and therefore defines if a Natural Person can act on behalf of a Legal Person or governmental body. However, also use cases with physical access could be considered (e.g. collection of goods, access to a location).&#x20;

A Natural Person could be an employee of the Legal Person or governmental body (e.g. a Company) but it could also be the owner of the Legal Person or an external Natural Person which is empowered to represent the Legal Person for specific use cases (e.g. an external accountant).&#x20;

&#x20;

The Representation Register relates Natural Persons to Legal Persons and therefore defines if a Natural Person can act in behalf of a Legal Person. This is primary used in (remote) H2M interactions where a Natural Person uses a Service of Service Provider (e.g. via a web interface). However, also use cases with physical access could be considered (e.g. collection of goods, access to a location).&#x20;

A Natural Person could be an employee of the Legal Person (e.g. a Company) but it could also be the owner of the Legal Person or a external Natural Person which is empowered to represent the Legal Person for specific use cases (e.g. an external accountant).&#x20;

Relationship to other Building Block&#x20;

The Representation Register is (directly or indirectly) used by the following Building Blocks:&#x20;

* Authentication: applicable for H2M Use Cases&#x20;
* Authorisation: applicable for H2M Use Cases&#x20;
* Digital Identity: to be checked if this relates to both the Roles of Legal Entities and / or Natural Persons&#x20;
* Zero Trust Check: applicable for H2M Use Cases&#x20;
* Certified Roles: to be checked if this relates to both the Roles of Legal Entities and / or Natural Persons&#x20;
* Professional Qualification Register: this registers the professional qualifications of Natural Persons. &#x20;
* Verifiable Credentials: this is future work; also reference to the planned iSHARE RFC on Verifiable Credentials&#x20;

Elements & core Functions&#x20;

* the representation mandate of authenticated natural persons acting of behalf of the legal person or governmental body;&#x20;
* the representation mandate of organizations (sub-contractors) acting on behalf of the data owner;&#x20;
* the standardized roles the data owner’s organization supports.&#x20;

&#x20;

The DSCC Blueprint has no direct related Building Block for the Representation Register. The Representation Register must be able to issue credentials which represent the relationship between Natural Persons and Legal Persons. It mentions the example of the technical specification of GAIA-X which defines this as a Legal Person Party Credential. iSHARE also uses the term Party Credentials. &#x20;

TO BE VALIDATED: IF THIS IS ALSO USED FOR LEGAL PERSONS WITHIN ISHARE&#x20;

Examples of existing Representation Registers include:&#x20;

* Internal Representation Registers within a Legal Person related to IAM processes. Office 365 is widely used which uses Microsoft Entra (AAD) as a “Directory” of natural persons with email addresses, etc. But also other solution are available an used. The best practice is to use this as the “Golden Truth” of the Representation Register for the Legal Person.&#x20;
* E-Herkenning which is the Dutch B2B eIDAS  Framework. Note that most other European countries don’t have a similar Framework&#x20;
* Other external Identity Providers which Federate with Service Providers. Examples include Secure Logistics XSid and Portbase IAMconnected&#x20;
* Representation Register within a Service Provider&#x20;

Best Practices for Digital Access&#x20;

Use E-Herkenning for Dutch (only) Data Spaces.&#x20;

Federate the Service Provider Representation Register with the Internal Presentation Register of the Legal Entity. This enables Single Sign On for the natural person (ease of use) an increases the security (connecting to the Joiner / Mover / Leaver process of the Legal Person). &#x20;

Federate the Service Provider Representation Register with an External Identity Provider. This can be considered if the External Identity Provider overlaps with the (target) groups of the Service Provider.&#x20;

Best Practices for Physical Access&#x20;

Smart Card Solutions like the Secure Logistics Cargo Card and the Smart LOXS Cargo Card.&#x20;

App / Wallet based solutions on Smartphones.&#x20;

Notes / outstanding actions&#x20;

Note on Authorisations.&#x20;

Note on current iSHARE Approach and limitations&#x20;

Note on relation with iSHARE RFC on VC’s&#x20;

Note on European Wallet perspective (Future Versions)&#x20;

&#x20;

Core Design Systems&#x20;

&#x20;

Functional Specifications&#x20;

&#x20;

Recommended Standards&#x20;

&#x20;

Technical Specifications&#x20;

Future Versions&#x20;

Explore & Align with the DSCC approach for attestations based on verifiable credentials. eIDAS 2.0 will require Member States to provide citizens, upon their request, with a notified European Digital Identity Wallet (EDIW). It also addresses Legal Persons. &#x20;

&#x20;

Further Reading&#x20;

&#x20;

* DSSC Building Block&#x20;
* TNO Report on Verifiable Credentials&#x20;
* iSHARE References&#x20;

&#x20;

&#x20;

NOTES (NOT FOR EXTERNAL PUBLICATION)&#x20;

&#x20;

&#x20;

Reviewers:&#x20;

* DIL&#x20;
* Portbase&#x20;
* iSHARE&#x20;
* Secure Logistics&#x20;
* E-Herkenning partijen è Digidentity, KPN, &#x20;
* KVK&#x20;
* Ondernemingspaspoort&#x20;

&#x20;
