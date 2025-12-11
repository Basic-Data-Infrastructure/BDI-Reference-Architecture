# Discovery

### 1. Summary

This building block defines how BDI supports organizations (Data Providers and Data Consumers) in discovering other organizations, services and endpoints by:

Utilizing discovery-aspects of the iSHARE Trust Framework.

or

Defining a standard for discovery using the DNS Protocol.

### 2. Purpose of this building block

{% hint style="info" %}
In the BDI, the discovery process is recommended for enabling connections between data providers and consumers. Unlike traditional data marketplaces, where the primary focus is on matching providers with potential consumers to establish new data-sharing relationships, BDI focuses on optimizing existing data exchanges. These exchanges often support operational logistics in the supply chain, where different parties are already connected but require more efficient methods for data exchange.
{% endhint %}

#### Option 1: Discovery using the iSHARE specifications

iSHARE and thereby BDI provide a framework for the discovery of:

1. **(Data) Services.** All participants providing services must provide a [/capabilities endpoint](https://dev.ishare.eu/common/capabilities.html), as defined in the developer documentation. This endpoint provides information on the available BDI supported service offerings.
2. **Participants of a data space**. Participants of an association (in iSHARE: data space) are (if they choose to) discoverable through the [/parties endpoint](https://dev.ishare.eu/satellite/parties.html) of any Association Register (in iSHARE: iSHARE Satellite).
3. **Data spaces**. Associations (data spaces) are (if they choose to) discoverable through the [/dataspaces endpoint](https://dev.ishare.eu/satellite/dataspaces.html) of any Association Register (in iSHARE: iSHARE Satellite).

#### Option 2: Discovery using DNS

The Domain Name System (DNS) is a foundational protocol in internet infrastructure, serving as a directory that translates human-readable domain names into IP addresses. In the context of federative data sharing networks like the BDI, DNS plays a crucial role in enabling data consumers and providers to discover each other's service endpoints. By utilizing DNS for service endpoint discovery, organizations can publish and find endpoints, thereby facilitating data exchange within the network. This building block outlines the purpose, concepts, implementation considerations, key elements, and recommended standards for using DNS in the BDI discovery building block.

The purpose of using DNS in the BDI discovery building block is to provide a standardized method for publishing and discovering service endpoints. This allows data consumers to easily find the endpoints of data providers without the need of a common shared register, assess their trust level, and establish connections for data exchange. The use of DNS ensures that the discovery process is both scalable and compatible with existing internet infrastructure. Discovery based upon DNS allows for a perimeter-less federation of BDI users and Associations.

### 3. Concepts

1. _DNS Overview_: DNS is a hierarchical and decentralized naming system that translates domain names into IP addresses, enabling users to access websites and other resources on the internet. DNS is organized into zones, each managed by an organization that controls its own part of the DNS namespace.
2. _DNS Subdomain:_ a standardized subdomain ( "\_bd1.\[ url] ") improves discoverability, educes the risk of interference with existing DNS records for the domain name already in possession of an organization.
3. _Service Discovery_: In the context of BDI, service discovery involves using DNS to locate the endpoints of parties involved. This is achieved by creating specific DNS records in a subdomain "\_bdi" that describe the services and where they can be accessed.
4. _DNS Records_: Different types of DNS records serve various purposes. For service discovery in BDI, TXT and SRV records are particularly important. TXT records can store arbitrary text and are used to describe the services offered, while SRV records specify the hostname, port, and protocol for accessing a service.
5. _Federation:_ The URL of the Association of a party (the "Home" of a party) can be used to discover the service endpoints of their Association. These services can be used to verify onboarding and membership of that previously unknown party. The DNS namespace is used as a shared register, suitable for perimeterless global interactions.

<figure><img src="../../.gitbook/assets/20240911 Federation Discovery.png" alt=""><figcaption></figcaption></figure>

### 4. Implementation Considerations

When implementing DNS for service discovery in BDI, several factors need to be considered:

1. _Zone Management_: Organizations must manage their DNS zones effectively to ensure accurate and up-to-date information is available for discovery. This involves maintaining the appropriate DNS records and ensuring that the DNS infrastructure is reliable and secure.
2. _Security_: To secure the discovery process, DNSSEC (DNS Security Extensions) should be implemented. DNSSEC adds a layer of security to DNS by enabling the authentication of DNS data, preventing tampering, and ensuring the integrity of the information provided in DNS records.
3. _Scalability_: DNS is inherently scalable, making it suitable for large, federated networks like BDI. However, organizations must ensure that their DNS infrastructure can handle the expected load, particularly as the network grows.
4. _Standardization_: To ensure interoperability within the BDI network, it is crucial to follow standardized naming conventions and DNS record formats. This includes using well-known subdomains { "\_bdi.\[url]"} and consistent formatting for TXT and SRV records.

### 5. Elements and Their Key Functions

1. _Well-Known Subdomain_: A predictable subdomain, such as \_bdi.acme-corp.com, serves as a central point for service discovery. This subdomain is used to organize DNS records related to BDI services, making it easy for data consumers to find relevant endpoints.
2. _SRV Records_: SRV records are used to locate the actual endpoints where services are hosted. These records specify the hostname or IP address, port number, protocol, and other parameters necessary to connect to the service.
   1. Key Fields: target (hostname/IP), port (service port number), priority and weight (used to select the best service endpoint if multiple are available).
3. _TXT Records_: TXT records provide descriptive information about the services offered by a data provider. These records can include lists of services available under a specific subdomain, details about the protocols used, and any additional attributes required for service access.
4. _DNSSEC_: DNSSEC provides security for DNS by enabling the validation of DNS responses. This is crucial for preventing attacks like cache poisoning, ensuring that data consumers receive accurate and trustworthy information during the discovery process.

{% file src="../../.gitbook/assets/2024_DIL_BDI-DNS-Service-Discovery-Proposal.pdf" %}

{% file src="../../.gitbook/assets/20240920_BDI_DNS as a service discovery mechanism.pdf" %}
