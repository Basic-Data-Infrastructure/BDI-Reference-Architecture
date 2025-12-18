---
hidden: true
cover:
  light: ../../../.gitbook/assets/a8d30c33-527b-425f-bd0f-41ed90561b77.png
  dark: ../../../.gitbook/assets/istockphoto-1054396134-612x612.jpg
coverY: 0
coverHeight: 418
layout:
  width: default
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Triple Identity (Suus)

<div data-full-width="true"><figure><img src="../../../.gitbook/assets/251110 BDI RfC Triple Identity.drawio (2) (1).png" alt=""><figcaption></figcaption></figure></div>

### 1. Introduction

The Triple Identity model is a key concept in the Digital Identity building block. As can be seen in the triangle in the figure above, this model consists of 3 elements. Each one of these elements is required in order to verify a digital identity. Let us consider each of the elements separately.&#x20;

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Natural person</strong></td><td><em>A natural person, working for this legal entity</em> </td><td>The natural person refers to a person working for the legal entity, such as an organization. This person uses the application of the organization to request or share data, in the name of the organization. </td><td><a href="../../../.gitbook/assets/BDI_developers-1-scaled.webp">BDI_developers-1-scaled.webp</a></td></tr><tr><td><strong>Legal Entity</strong></td><td><em>A legal entity, such as an organization</em></td><td>The legal entity refers to an organization of any kind. Within the data sharing context, this organization can be the data owner or the data requestor. However, the legal entity itself is not performing the actions required to share or receive data. This is performed by a natural person working for this Legal Entity. </td><td><a href="../../../.gitbook/assets/bdi website images 2.webp">bdi website images 2.webp</a></td></tr><tr><td><strong>Application</strong></td><td><em>The application used by the natural person</em></td><td>The application refers to the back-end of the organization. This is the application where the natural person working for this organization works with the data. </td><td><a href="../../../.gitbook/assets/bdi website images.webp">bdi website images.webp</a></td></tr></tbody></table>

#### 1.1 Purpose

The Triple Identity model was selected for its ability to establish **verifiable, contextual trust** in federated digital ecosystems. Unlike models that rely solely on machine or user identity, this approach provides a holistic structure that ties digital actions to accountable actors within organizational and technical boundaries.

The triple identity model allows for a unique combination of three elements. This unique combination is essential in establishing a digital identity in e.g. the following cases:&#x20;

1. The onboarding of a new legal entity within the BDI
2. A new system-to-system integration&#x20;
3. Forming a basis for more complex transactions, such as mandates&#x20;



#### 1.2 External trust

The Triple Identity model is based on the principle that each one of its elements is anchored in external trust. By trusting external identification mechanisms, BDI-participants are more inclined to trust the entire framework.&#x20;

The figure below shows some suggestions on how the trust in each element can be verified externally.&#x20;

<figure><img src="../../../.gitbook/assets/251110 BDI RfC Triple Identity-Copy of Copy of Page-1.drawio (1).png" alt=""><figcaption></figcaption></figure>



Additionally, the trust in the connection between these elements should be verified. Click on a tab below for some suggested mechanisms for external trust in these connections.&#x20;

<details>

<summary>Natural person and Application</summary>

The connection between a natural person and the application they use, can for example be verified externally with the use of an Estonia Personal Certificate.&#x20;

</details>

<details>

<summary>Application and Legal entity</summary>

A commonly used method to verify that an application belongs to a certain legal entity, is [eHerkenning](https://www.eherkenning.nl/nl).&#x20;

</details>

<details>

<summary>Legal entity and Natural person</summary>

The connection between a legal entity and a natural person can for example be verified with the use of CA or an [eIDAS](https://www.digitaleoverheid.nl/overzicht-van-alle-onderwerpen/identiteit/eidas/) provider.&#x20;

</details>

#### 1.3 Should-Have

The Triple Identity model relies on external trust. However, associations may decide not to externally validate the identity of (one of) the elements. Instead, they might agree to use a simpler alternative. While such an approach can be reasonably effective within smaller organizations, challenges emerge as the number of organizations increases. Moreover, employing external trust validators facilitates smoother collaboration not only within a single association, but also between multiple associations. &#x20;

{% hint style="warning" %}
It is strongly advised to validate digital identities with external trust mechanisms.&#x20;
{% endhint %}





### 2. Interactions with other building blocks



### 3. Examples
