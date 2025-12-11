---
cover: >-
  https://images.unsplash.com/photo-1664526937033-fe2c11f1be25?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxzZW1hbnRpYyUyMGZyYW1ld29ya3xlbnwwfHx8fDE3NjM1NjE0NTN8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 415
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

# 📑 Alternative Semantics Frameworks (Suus)

## 1. Introduction

When interacting parties do not share an existing semantics standard, the use of LEO is required. Note, however, that it is possible for BDI parties to use any other framework.

For example, consider a multi-model trip from a manufacturer to the BCO that partly travels over sea. The parties involved in the sea trip may, in interactions with one another, make use of the DCSA standard. This is a well-known standard that has been in use for a long time. For the communication with other stakeholders, however, DCSA may not be the best standard, as these parties are not familiar with it or are not currently using it. Therefore, LEO may be required for the interactions with these stakeholders.

## 2. Other standards

### 2.1 DCSA

The DCSA ([**Digital Container Shipping Association**](https://dcsa.org/)**)** maintains a set of standards for data exchange between stakeholders in the maritime world. These standards are widely adopted and can be considered for support in data exchange within BDI implementations. However, when using these standards, one must consider whether the BDI principles — e.g. security, zero trust, data sovereignty and data at the source — can still be maintained, as very few of these are required by the DCSA standards.



{% hint style="warning" %}
#### Other frameworks

The DCSA described above is only one example of an an alternative semantic framework that can be used in the context of the BDI. Other frameworks, such as the IATA standard used for air freight, will be added later when necessary.
{% endhint %}

