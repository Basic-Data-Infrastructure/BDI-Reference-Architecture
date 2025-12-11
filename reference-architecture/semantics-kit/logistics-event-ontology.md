# Logistics Event Ontology

{% hint style="info" %}
The **purpose of this building** block is to describe the creation and usage of a light-weight common BDI format, called LEO (Logistics Event Ontology). The purpose of this format is to bridge the existing standards in the realm of logistics data sharing, like OTM, FEDeRATED, OneRecord, DCSA, GS1, UN/CEFACT, EDIFACT and many others. It is not the intention to fully map all details of all standards on a single model. Instead, the LEO format distils the minimal data needed to follow goods through the supply chain based on the perspective of the beneficial cargo owner (BCO).
{% endhint %}

{% hint style="warning" %}
The Logistics Event Ontology is still under development
{% endhint %}

{% hint style="danger" %}
### Implementation Considerations

In creating this minilanguage, we should avoid reinventing the wheel. We achieve this by keeping close to existing standards. The most effective way to do this would be to pick a small number of modelling elements from a small number of carefully selected models.

These models should be widely used and well-understood, relatively simple, and, taken together, support the target use cases concerning supply chain visibility for BCOs. The challenge, however, is: how can we not only keep our minilanguage simple, but also ensure that mapping datapoints from existing messages in terms of dozens of languages is viable? The answer is to make pervasive use of code lists and thesauri.

Beneficial cargo owners (BCOs) greatly profit from this information allowing them to track and trace their cargo. Unfortunately, different subdomains in the logistics industry use vastly different languages to express such information. The unwanted result is that many BCOs suffer from an inadequate information position. Hence the need for an intermediary language as a solution.
{% endhint %}

{% hint style="danger" %}
### Interlinkages with other building blocks

This building block is closely linked with the Event Publish-Subscribe Service. The LEO format is mostly geared towards the description of events and the minimal data needed to communicate between modalities and existing standards. It defines templates for often used common logistic events and their linkage to domain standards.
{% endhint %}

There is a growing demand from Beneficial Cargo Owners (BCO) to create more visibility in the supply chain: visibility of the operational planning and execution of all the steps between ordering goods and receiving the consignments in the distribution center or warehouse of the BCO.

Each transport leg in the consignment journey results in one or more events which are to be communicated between parties directly involved in the transport leg. The event communication leads to data exchanges, typically using specific systems, platforms and data formats. The diversity of parties, systems and data formats are a barrier to automated exchanges.

The issue to be solved is the existence of a wide variety of data formats and semantic definitions in supply chains:

* beneficial cargo owners who want to track & trace their goods cannot adopt all the data standards in use;
* the logistics partners want to keep using their existing data standards;
* (global) unification of data standards is not a practical option for the near future.

The concept of an event envelope is introduced, named Logistics Event Ontology (LEO). The BDI framework separates the envelope from the payload, separating event data from other operational data. The BDI envelope is a notification of an event with additional data and meta-data, combined with a link to the endpoint of the data owner where more (sensitive) data about the event may be requested. The data owner evaluates the request and the party requesting access, and provides data on a 'need-to-know' basis.

The Logistics Event Ontology (LEO) is derived from existing standards, especially the GS1 EPCIS standard. OpenEPCIS is an open-sourced fully compliant implementation of the EPCIS standard, allowing for extensions on the standard to support future events.

LEO supports the use of standard operational trip data by operators (such as carriers) to generate notifications of events to cargo owners or authorities, leading to efficiency and productivity increases.

### Documents

{% file src="../../.gitbook/assets/20250120_BDI-Logistic-Event-Ontology.pdf" %}

{% file src="../../.gitbook/assets/20240101_DIL_BDI-Developing-Semantics-for-Supply-Chain-Transport-Logistics.pdf" %}
