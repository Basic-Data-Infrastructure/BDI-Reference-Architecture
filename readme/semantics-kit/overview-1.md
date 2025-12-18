---
cover: >-
  https://images.unsplash.com/photo-1610116306796-6fea9f4fae38?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxib29rc3xlbnwwfHx8fDE3NjM0MzUwNzZ8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 418
---

# 📖 Overview (Suus)

## 1. Introduction

Over time, different sectors have developed their own operational “languages” to describe and manage their activities. This fragmentation is evidenced by the multitude of global and local data standards across logistics, trade, and transport. The BDI explicitly recognizes this landscape and emphasizes that participants should:

1. **Align with sector-relevant standards** where possible, rather than duplicating efforts or creating isolated models. Examples of well known and governed standards are (non exhaustive):

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><a href="https://dcsa.org/"><strong>Digital Container Shipping Association</strong></a></td><td>Focuses on standardizing data and processes for containerized maritime transport, including Track &#x26; Trace and documentation flows. </td><td><a href="../../.gitbook/assets/dcsa.png">dcsa.png</a></td></tr><tr><td><a href="https://www.iata.org/"><strong>International Air Transport Association</strong></a></td><td>Develops standards for the global air cargo industry, covering electronic messaging, air waybills, and cargo operations.</td><td data-object-fit="contain"><a href="../../.gitbook/assets/iata.avif">iata.avif</a></td></tr><tr><td><a href="https://opentripmodel.org/"><strong>Open Trip Model</strong></a></td><td>Provides a modular data model for planning, execution, and tracking of multimodal transport and logistics movements, mainly in the European inland context.</td><td><a href="../../.gitbook/assets/otm (2).png">otm (2).png</a></td></tr><tr><td><a href="https://www.era.europa.eu/"><strong>European Union Agency for Railways</strong></a></td><td>Defines technical specifications for interoperability in rail transport, including infrastructure, rolling stock, and data exchange for railway operations.</td><td><a href="../../.gitbook/assets/era.jpg">era.jpg</a></td></tr></tbody></table>

2. **Organize for supply chain-wide semantic interoperability**. In many logistics environments, not all actors operate under the same modality or domain-specific framework. Therefore, the Semantic KIT recommends adding the [**Logistic Event Ontology**](../../reference-architecture/semantics-kit/logistics-event-ontology.md) as a minimal, cross-modal structure. This enables end-to-end visibility of goods movement from the perspective of the Beneficial Cargo Owner (BCO), serving as a neutral format for semantic consistency across the supply chain.



## 2. Selecting a standard&#x20;

{% hint style="success" %}
It is strongly recommended to conduct research into existing standards, as the tools or practices you currently employ are likely derived from one.&#x20;
{% endhint %}

There are a couple of relevant considerations to take into account for the selection of a data standard. For the evaluation of suitable existing data models, please consider the following.&#x20;

#### <i class="fa-book-atlas">:book-atlas:</i>  Applicability, geographical coverage, coverage of logistics and supply chain areas

Market participants might ask themselves the question:

> &#x20;"_If I invest in particular standard semantics, how many partners can I work with using this standard?"_&#x20;

To avoid using an unknown or rarely-used standard, it is recommended to determine if there is an actively maintained data model governed by a Standards Development Organization (SDO). In addition, one should assess how well the model aligns with the use case(s), and understand the model’s governance structure and licensing terms.

***

#### <i class="fa-gears">:gears:</i>  Technical maturity, support for Event-Driven and Linked Data approaches

Indicates the extend to which the standard can be deployed in an automated way, as well as its ability to support anticipated future developments.&#x20;

Given that the BDI is a logistics, event-driven architecture, consider selecting a standard that supports events as well.

***

#### <i class="fa-cloud-binary">:cloud-binary:</i>  Scope to Adopt

Identify which part of the standard is relevant for the use case. Often, only a subset is required, making adoption more lightweight. If the standard offers well-defined extensibility mechanisms, use them to incorporate case-specific data while maintaining compliance. If critical elements are missing, engage with the SDO to evolve the model, thereby improving the standard for the broader community.

***

#### <i class="fa-integral">:integral:</i> Integration with BDI Trust KIT

Consider how the data model supports or integrates with BDI’s Identity, Authentication, and Authorization (IAA) protocol. Most standards are silent on identity and trust, which allows BDI’s Trust KIT to be applied alongside.

***

{% hint style="success" %}
When no suitable standard exists, it is recommended to use **LEO:** a generic cross-modal structure that can be extended for specific use cases serving as a neutral format for semantic consistency across the supply chain.
{% endhint %}
