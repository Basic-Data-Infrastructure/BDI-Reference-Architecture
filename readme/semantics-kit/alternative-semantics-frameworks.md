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

# Alternative semantics frameworks

Although the use of LEO is required for interactions between parties that do not share an existing semantics standard it is quite possible for BDI parties to use any other framework if they agree to it.

An example of this is a multi-modal trip from the manufacturer to the beneficial cargo owner that goes partly over sea. The parties involved in the sea trip may use among themselves the DCSA standard, as they all know it and have been using it for a long time. But for the communication with other stakeholders in the chain, DCSA may not be known or in use, so for interactions with these, the common LEO standard is required.

{% hint style="info" %}
#### Digital Container Shipping Association

The DCSA matains a set of standards for data exchange between stakeholders in the maritime world. These standards are widely adopted and BDI implentations may choose to support them for data exchange as well. However, to do so, other BDI principles such as security, zero trust, data sovereignty and data at the source must be maintained as well. Very few of these are required by the DCSA standards.
{% endhint %}

{% hint style="info" %}
#### Other frameworks

The DCSA described above is only one example of an an alternative semantic framework that can be used in the context of the BDI. Other frameworks, such as the IATA standard used for air freight, will be added later when necessary.
{% endhint %}

