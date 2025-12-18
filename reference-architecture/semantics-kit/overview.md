---
layout:
  width: default
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

# Overview

{% hint style="warning" %}
### NOTE

This page will disappear in the near future, as the information contained herein is moved to more appropriate locations in this git book.
{% endhint %}

### Elements and their key functions

According to EPCIS (ISO/IEC 19987) an Event contains at least the following 5 aspects: 'What, Where, When, Why and How'.

• What: To which object or entity does this Event primarily relate (e.g. pallet, order, truck, wagon, etc.)?

• Where: At which location did the event take place (warehouse receipt door, terminal access)?

• When: On what date and time did the event take place?

• Why: Why (in which business activity exactly) did the event take place (goods receipt, freight collection, transport document definitively agreed, etc.)?

• How: It may also include the 'How' aspect. In what state (how) are or was the cargo being transported at the time of the event?

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>A FEDeRATED example event and attached data</p></figcaption></figure>

The example figure above, brings together the ideas of Event-Driven as also used in FEDeRATED and the EPCIS standard (which is almost 20 years old and used in practice in transport, logistics and supply chain). The Event is central in the figure, it is linked to a location (Where), to a logistics service (Why) and to a (physical) object (What).

The semantic model of the Event, expressed in RDF in the figure, also has a date and time. Since there are also quite a few connections beyond the figure's boundary, it will be clear that the Event-Driven semantic model can be extended to any level.

### Future topics

We are not the only party looking for minimalistic logistics formats to create multi-modal supply chain visibility in conjunction with the many logistic domain standards now in practice. There are several commercial platforms creating this function already.

Several of them are completely open and have published and maintained formats like this for years. Much like the successful creation of the OTM standard, they are based on operational pragmatism and have been tested in practice.

We see them as excellent starting points for the format we are trying to define. A good example is Shippeo’s Real-Time Transportation Visibility Platform service with [https://api-doc.shippeo.com/](https://api-doc.shippeo.com/) as an open data model and API format.

### Further reading

The choices made for this building block are based on the following research:

* [Federated Semantic Interoperability](https://www.federatedplatforms.eu/index.php/federated-semantic-interoperability)
* LEO: THE LOGISTICS EVENT ONTOLOGY. A generic “minilanguage” for sharing information across domains, BDI Architecture Board
* Selection of a base model for LEO, BDI Architecture Board
* Semantic model development, BDI Architecture Board

