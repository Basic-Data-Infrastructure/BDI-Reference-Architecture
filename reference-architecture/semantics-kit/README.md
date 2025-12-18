---
cover: >-
  https://images.unsplash.com/photo-1457369804613-52c61a468e7d?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxib29rfGVufDB8fHx8MTc2NTQ2MzM5NHww&ixlib=rb-4.1.0&q=85
coverY: 0
layout:
  width: default
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# 📖 Semantics KIT



{% hint style="info" %}
The main, if not the only, purpose of the BDI is to facilitate the exchange of data between parties in a logistic chain. However, this is only possible if all involved parties share the same interpretation of the data. This requires a common format and structure (syntax) of the data as well as a common semantics.

Over time, many transport modalities have developed their own ‘language’ to communicate about their activities. This is illustrated by the number of semantics standards. It is expected that data spaces should align with sectors and their standards, creating the need for tools for organizations that participate in multiple data spaces to switch between standards.

The semantics KIT provides a common semantics framework called LEO as well as means to include a variety of existing standards, such as DCSA (for container transport), IATA (air transport) and ERA (rail transport).
{% endhint %}

{% hint style="warning" %}
Many of the known semantic standards currently in use in logistics are based on monomodal transport. However, modern supply chains are inherently multimodal, requiring the involved parties to exchange data with other parties that are not necessarily in their own modality. This limits the use of modality specific semantic models.
{% endhint %}

{% hint style="warning" %}
This KIT requires the Trust and Event KITs. This building block is closely linked with the Event Publish-Subscribe Service. The LEO format is mostly geared towards the description of events and the minimal data needed to communicate between modalities and existing standards. It defines templates for often used common logistic events and their linkage to domain standards.
{% endhint %}

{% hint style="info" %}
#### Concepts

Three distinct levels or perspectives exists from which one can consider the logistics domain, based on the three layers of the DCSA model:

1\. Transport: The movements of the transport means containing equipment which contains the goods. Like vessel, barge, ship, truck, airplane, etc.

2\. Equipment: The movements of the actual equipment containing the goods. Like container, parcel, trailer, package, loading, pick up, delivery, eta, etc.

3\. Shipment: The business transactions along the supply chain. Like bill of lading, airway bill, customs documents, clearances, certificates, etc.

The LEO format is primarily focused on the first two physical perspectives and builds on the semantic work done in de FEDeRATED projects.
{% endhint %}
