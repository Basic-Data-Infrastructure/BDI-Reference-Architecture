---
cover: >-
  https://images.unsplash.com/photo-1483478550801-ceba5fe50e8e?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw2fHxkaWdpdGFsJTIwaWRlbnRpdHl8ZW58MHx8fHwxNzY1MzYwODc0fDA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 328
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

# Digital Identity

See [Digital Identity M2M](digital-identity.md) and [Digital Identity H2M](digital-identity-h2m.md)

{% hint style="warning" %}
Terminology in the field of digital identity can be confusing as different sources use terms in slightly different meaning. To deal with this confusion, we define some terms that are used in the description of the BDI Digital Identity.
{% endhint %}

The physical world is populated by persons and objects that can be recognized and distinguished from one another by their _Physical Identity_. Although the notion of physical identity is heavily debated in philosophy, we will not discuss this further beyond the observation that identities are unique and constant over time. In a sense, a physical identity determines the "sameness" of a person or object over time.

{% hint style="info" %}
Although persons and objects are of course entirely different categories, much of what is written here about persons also holds for objects.
{% endhint %}

A person that is identified through its physical identity can have many _attributes_ such as a name, date of birth, address, eye color and so on. Some of these attributes are unique for a given person and hence can be used for identification. It is however important to note that a physical identity is not the same as this unique set of attributes. A Digital Identity is a record in an information system, describing certain attributes of a person in the physical world. The digital identity can be used by information processing systems to determine e.g. access rights.There are several issues that must be dealt with when managing digital identities:

1. At creation time of the digital identity it must be certain that it indeed corresponds to the right person (the onboarding problem)
2. It must not be possible to use the digital identity for any purpose without the explicit consent of the holder of the physical identity.
3. The digital identity must contain sufficient information to uniquely identify the person.

​
