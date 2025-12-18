---
cover: >-
  https://images.unsplash.com/photo-1753715613388-7e03410b1dce?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxkaWdpdGFsJTIwc3lzdGVtJTIwYXJjaGl0ZWN0dXJlfGVufDB8fHx8MTc2NDMyNTE0MHww&ixlib=rb-4.1.0&q=85
coverY: 0
---

# 📃 INTRODUCTION

## 1. Introduction to the BDI Reference Architecture

The Basic Data Infrastructure Framework (BDI) is an infrastructure framework for controlled data sharing, supporting automated advanced information logistics in the physical economy. Departing from traditional messaging paradigms, the BDI shifts towards event-driven data collection at the source, fostering efficient and secure coordination through proven publish-and-subscribe architectures.

This introduction provides a short overview of some issues that play a role in the design of the architecture, starting with some observations about data in a logistics environment. These observations are used in the formulation of architectural principles which are in turn the basis of BDI building blocks. Finally, these building blocks are grouped in functional subsets called KITs.

See [bdinetwork.org](https://bdinetwork.org) for a full account of these concepts.

## 2. Observations

Some observations about data in the logistics environment are given below:&#x20;

<details>

<summary>Characteristics of data exchange patterns</summary>

The data exchange patterns in typical operational networks are a result of “doing business”. They have specific characteristics:

* The network of involved parties is driven by the fulfillment of an assignment. These networks are temporary and fluid, meaning that members are added whenever necessary and the network is dissolved when the job is done.
* Data exchanges are between members of a closed group, i.e. the members are vetted in advance.
* There can be time constraints on the exchange of data.

</details>

<details>

<summary>Support requirements for a data exchange infrastructure </summary>

A common data exchange infrastructure for operational networks should support the following:&#x20;

* dynamic instances
* multiple concurrent instances
* controlled event-driven exchange

</details>

<details>

<summary>Requirements for event-driven exchange of operational data</summary>

Event-driven exchange of operational data within an instance must be:

* **Efficient,** i.e. no polling, no unnecessary retrieval
* **Effective,** i.e. easy distribution to multiple parties simultaneously
* **Controlled**:
  * Limited exposure to malicious actors
  * Only authorized parties can retrieve information
  * Role-based data access
  * The Data Owner tracks access, providing a clear audit trail

</details>

<details>

<summary>Value of data</summary>

The following observations are made about the value of data:&#x20;

* Data has value
* Data owners want to protect and monetize this value

</details>

<details>

<summary>Trust in global business networks </summary>

The importance of trust in global business networks

* Identification authentication and authorization play an important role in establishing trust.
* **Zero trust** - do not trust anyone before trust is established.
* **Perimeterless trust** - do not base trust on membership of a closed group of trusted parties

</details>
