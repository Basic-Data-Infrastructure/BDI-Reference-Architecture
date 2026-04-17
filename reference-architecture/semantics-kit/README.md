---
cover: >-
  https://images.unsplash.com/photo-1457369804613-52c61a468e7d?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxib29rfGVufDB8fHx8MTc2NTQ2MzM5NHww&ixlib=rb-4.1.0&q=85
coverY: 0
---

# 📖 Semantics KIT

## 1. Introduction

The main, if not the only, purpose of the BDI is to facilitate the exchange of data between parties in a logistic chain. However, this is only possible if all involved parties share the same interpretation of the data. This requires a common format and structure (syntax) of the data as well as a common semantics.

Over time, many transport modalities have developed their own ‘language’ to communicate about their activities. This is illustrated by the number of semantics standards. It is expected that data spaces should align with sectors and their standards, creating the need for tools for organizations that participate in multiple data spaces to switch between standards.

The semantics KIT provides a common semantics framework called [LEO ](../../readme/semantics-kit/logistics-event-ontology-1.md)as well as means to include a variety of existing standards, such as DCSA (for container transport), IATA (air transport) and ERA (rail transport). The LEO format is mostly geared towards the description of events and the minimal data needed to communicate between modalities and existing standards. It defines templates for often used common logistic events and their linkage to domain standards.

{% hint style="success" %}
Many of the known semantic standards currently in use in logistics are based on monomodal transport. However, modern supply chains are inherently multimodal, requiring the involved parties to exchange data with other parties that are not necessarily in their own modality. This limits the use of modality specific semantic models.
{% endhint %}

## 2. Interlinkages with other building blocks

<a href="../trust-kit/" class="button secondary">Trust KIT</a>  <a href="../logistics-event-kit/" class="button secondary">Logistic Event KIT</a>  <a href="../logistics-event-kit/event-pub-sub-service.md" class="button secondary">Pub/Sub service</a>

## 3. Concepts&#x20;

Three distinct levels or perspectives exists from which one can consider the logistics domain, based on the three layers of the DCSA model:

1. **Transport**: The movement of transport vehicles carrying equipment and goods, such as vessels, barges, ships, trucks, and airplanes.
2. **Equipment**: The movements of the actual equipment containing the goods, such as containers, parcels, trailers, packages, loading, pick-ups, deliveries and etas.
3. **Shipment**: The business transactions along the supply chain, such as bills of lading, airway bills, customs documents, clearances and certificates.

The LEO format is primarily focused on the first two physical perspectives and builds on the semantic work done in de FEDeRATED projects.
