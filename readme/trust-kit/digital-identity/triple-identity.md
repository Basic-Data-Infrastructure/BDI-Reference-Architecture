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

# Triple Identity

### Triple identity pattern

{% hint style="info" %}
#### Triple Identity

When a data owner or data custodian receives a request for data it must validate whether the requator has sufficient rights to receive the data. To do so in a zero trust data space, the requestor must supply identity information. In general, all requests are sent by a system, triggered by a command from a human user. The system is owned by a legal entity and the user acts on behalf of that entity. To assess the validity of the request, the data owner must know each of these stakeholders, as well as the relations between them. Therefore, a triple identity is added to the data request. This identity contains three component identities: the legal entity, the human user and the system.
{% endhint %}

{% hint style="info" %}
The identity triple model was selected for its ability to establish **verifiable, contextual trust** in federated digital ecosystems. Unlike models that rely solely on machine or user identity, this approach provides a holistic structure that ties digital actions to accountable actors within organizational and technical boundaries.
{% endhint %}
