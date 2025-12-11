---
cover: >-
  https://images.unsplash.com/photo-1618044619888-009e412ff12a?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxhdXRoZW50aWNhdGlvbnxlbnwwfHx8fDE3NjM1NjUzNjF8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 476
---

# 🔑 Authentication M2M (Suus)

## 1. Introduction

To achieve the main goal of the BDI — simplifying safe data transfers between organizations — four related aspects are required:&#x20;

<figure><img src="../../../.gitbook/assets/Untitled Diagram.drawio.png" alt=""><figcaption></figcaption></figure>

This page focuses on the practical application of **Digital Trust** and **Controlled Data Access** by zooming in  on machine-to-machine interactions.&#x20;

In the context of the BDI, the user is a representative of a legal entity, e.g. an organization. This user needs to be authenticated for Human-to-Machine (H2M) interactions. However, authentication is also required for Machine-to-Machine use cases.  This page focusses on these M2M use cases, and specifically on the cases where a [Data Consumer](../../../reference-architecture/glossary/bdi-terms.md#data-consumer-data-user) requests data via an API.&#x20;

{% hint style="success" %}
**Authentication** is the process of proving that a user (human or IT process) with a digital identity who is requesting access is the rightful owner of that identity \[IDPro, 2022].&#x20;
{% endhint %}

## 2. Authentication methods for ASR applications

Four different levels for authenticating applications can be distinguished. The first level has the lowest level of trust but requires the least amount of effort/costs, while the fourth level is the most trustworthy and the most costly option. The levels are given below. Note that for each individual situation, the balance between trustworthiness and costs needs to be assessed in order to select a suitable authentication method.&#x20;

{% hint style="info" %}
The levels below are based on the following example situation:&#x20;

The example is based on hinterland transport of containers to and from the port of Rotterdam via inland waterways. Portbase is the central IT service provider/platform (data custodian) in the port, ITG is one of the hinterland parties and the shippe ris the Beneficial Cargo Owner (BCO).&#x20;

Assume there exists one BDI association for the port, one for the hinterland and one for the shippers.&#x20;
{% endhint %}

<table><thead><tr><th width="265"></th><th></th></tr></thead><tbody><tr><td>BDI-H</td><td>Association Port </td></tr><tr><td>BDI-V1</td><td>Association Hinterland</td></tr><tr><td></td><td></td></tr></tbody></table>



### 2.1 ID + Secret in ASR

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/251117 drawio - security rfc-ID + secret.drawio (4).png" alt=""><figcaption></figcaption></figure></div>

The simplest form of authentication is the combination of an ID and a Secret. This authentication can be compared to a username-password combination.&#x20;



### 2.2 Key-pair in the BDI Connector&#x20;

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/251117 drawio - security rfc-Key-pair in connector en ASR.drawio (3).png" alt=""><figcaption></figcaption></figure></div>

Level 2 contains an asymmetrical key-pair generated in the BDI connector, in combination with a publicly available key in the Association Register. This key-pair is generated using known cryptographical algorithms and libraries. The private key is securely saved locally and the public key is sent to the Association Register.&#x20;

### 2.3 Key-pair by Certificate Authority (CA)&#x20;

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/251117 drawio - security rfc-Key-pair door CA.drawio.png" alt=""><figcaption></figcaption></figure></div>

### 2.4 Key-pair with eIDAS QSeal&#x20;

<figure><img src="../../../.gitbook/assets/251117 drawio - security rfc-Key-pair eIDAS.drawio.png" alt=""><figcaption></figcaption></figure>

## Sources

_Authentication and Authorization (v2)_ (2022). IDPro. Retrieved November 24, 2025, from https://bok.idpro.org/article/78/galley/161/view/&#x20;
