---
cover: >-
  https://images.unsplash.com/photo-1516233074716-992e90fe18f8?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxkaXNjb3Zlcnl8ZW58MHx8fHwxNzY0NzY1ODkzfDA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 456
---

# Discovery

## 1. Summary

This building block defines how BDI supports organizations (Data Providers and Data Consumers) in discovering other organizations, services and endpoints by either&#x20;

* utilizing discovery-aspects of the iSHARE Trust Framework, or
* defining a standard for discovery using the DNS Protocol.

## 2. Purpose of this building block

In the BDI, the discovery process is recommended for enabling connections between data providers and consumers. Unlike traditional data marketplaces, where the primary focus is on matching providers with potential consumers to establish new data-sharing relationships, BDI focuses on optimizing existing data exchanges. These exchanges often support operational logistics in the supply chain, where different parties are already connected but more efficient methods for data exchange are required.

{% tabs %}
{% tab title="Option 1: Discovery using DNS" %}
**Option 1: Discovery using DNS**

The Domain Name System (DNS) is a foundational protocol in internet infrastructure, serving as a directory that translates human-readable domain names into IP addresses. In the context of federative data sharing networks like the BDI, DNS plays a crucial role in enabling data consumers and providers to discover each other's service endpoints. By utilizing DNS for service endpoint discovery, organizations can publish and find endpoints, thereby facilitating data exchange within the network. This building block outlines the purpose, concepts, implementation considerations, key elements, and recommended standards for using DNS in the BDI discovery building block.

The purpose of using DNS in the BDI discovery building block is to provide a standardized method for publishing and discovering service endpoints. This allows data consumers to easily find the endpoints of data providers without the need of a common shared register, assess their trust level, and establish connections for data exchange. The use of DNS ensures that the discovery process is both scalable and compatible with existing internet infrastructure. Discovery based upon DNS allows for a perimeter-less federation of BDI users and Associations.
{% endtab %}

{% tab title="Option 2: Discovery using the iShare specifications " %}
**Option 2: Discovery using the iShare specifications**

iSHARE and thereby the BDI provide a framework for the discovery of:

1. **(Data) Services.** All participants providing services must provide a [capabilities endpoint](https://dev.ishare.eu/common/capabilities.html), as defined in the developer documentation. This endpoint provides information on the available BDI supported service offerings.
2. **Participants of a data space**. Participants of an association (in iSHARE known as a _data space_) are optionally discoverable through the [parties endpoint](https://dev.ishare.eu/satellite/parties.html) of any Association Register (in iSHARE known as _iSHARE Satellite_).
3. **Data spaces**. Associations (data spaces) are optionally discoverable through the [dataspaces endpoint](https://dev.ishare.eu/satellite/dataspaces.html) of any Association Register (_iSHARE Satellite_).
{% endtab %}
{% endtabs %}

## 3. Concepts

<table data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>DNS Overview</strong></td><td>DNS is a hierarchical and decentralized naming system that translates domain names into IP addresses, enabling users to access websites and other resources on the internet. DNS is organized into zones, each managed by an organization that controls its own part of the DNS namespace.</td></tr><tr><td><strong>DNS Subdomain</strong></td><td><p>A standardized subdomain </p><p>("<em>_bd1.[ url]</em> ") improves discoverability, reduces the risk of interference with existing DNS records for the domain name already in possession of an organization.</p></td></tr><tr><td><strong>Service Discovery</strong></td><td>In the context of BDI, service discovery involves using DNS to locate the endpoints of parties involved. This is achieved by creating specific DNS records in a subdomain "_bdi" that describe the services and where they can be accessed.</td></tr><tr><td><strong>DNS Records</strong></td><td>Different types of DNS records serve various purposes. For service discovery in BDI, TXT and SRV records are particularly important. TXT records can store arbitrary text and are used to describe the services offered, while SRV records specify the hostname, port, and protocol for accessing a service.</td></tr><tr><td><strong>Federation</strong></td><td>The URL of the Association of a party (the "Home" of a party) can be used to discover the service endpoints of their Association. These services can be used to verify onboarding and membership of that previously unknown party. The DNS namespace is used as a shared register, suitable for perimeterless global interactions. For a visual explantion, see Figure 1. </td></tr></tbody></table>

<figure><img src="../../.gitbook/assets/20240911 Federation Discovery.png" alt=""><figcaption><p>Figure 1: Federation: Discovery by DNS</p></figcaption></figure>

## 4. Implementation Considerations

When implementing DNS for service discovery in BDI, several factors need to be considered:

{% stepper %}
{% step %}
#### Zone management

Organizations must manage their DNS zones effectively to ensure accurate and up-to-date information is available for discovery. This involves maintaining the appropriate DNS records and ensuring that the DNS infrastructure is reliable and secure.
{% endstep %}

{% step %}
#### Security

To secure the discovery process, DNSSEC (DNS Security Extensions) should be implemented. DNSSEC adds a layer of security to DNS by enabling the authentication of DNS data, preventing tampering, and ensuring the integrity of the information provided in DNS records.
{% endstep %}

{% step %}
#### Scalability

DNS is inherently scalable, making it suitable for large, federated networks like BDI. However, organizations must ensure that their DNS infrastructure can handle the expected load, particularly as the network grows.
{% endstep %}

{% step %}
#### Standardization

To ensure interoperability within the BDI network, it is crucial to follow standardized naming conventions and DNS record formats. This includes using well-known subdomains { "\_bdi.\[url]"} and consistent formatting for TXT and SRV records.
{% endstep %}
{% endstepper %}

## 5. Elements and Their Key Functions

{% tabs %}
{% tab title="Well-Known Subdomain" %}
A predictable subdomain, such as _\_bdi.acme-corp.com,_ serves as a central point for service discovery. This subdomain is used to organize DNS records related to BDI services, making it easy for data consumers to find relevant endpoints.
{% endtab %}

{% tab title="SRV Records" %}
SRV records are used to locate the actual endpoints where services are hosted. These records specify the hostname or IP address, port number, protocol, and other parameters necessary to connect to the service.

**Key Fields**:&#x20;

* target (hostname/IP)
* port (service port number)
* priority
* weight (used to select the best service endpoint if multiple are available)
{% endtab %}

{% tab title="TXT Records" %}
TXT records provide descriptive information about the services offered by a data provider. These records can include lists of services available under a specific subdomain, details about the protocols used, and any additional attributes required for service access.
{% endtab %}

{% tab title="DNSSEC" %}
DNSSEC provides security for DNS by enabling the validation of DNS responses. This is crucial for preventing attacks — e.g. cache poisoning — ensuring that data consumers receive accurate and trustworthy information during the discovery process.
{% endtab %}
{% endtabs %}

{% file src="../../.gitbook/assets/2024_DIL_BDI-DNS-Service-Discovery-Proposal.pdf" %}

{% file src="../../.gitbook/assets/20240920_BDI_DNS as a service discovery mechanism.pdf" %}
