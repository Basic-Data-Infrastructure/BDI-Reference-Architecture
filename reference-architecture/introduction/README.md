# INTRODUCTION

### Introduction to the BDI Reference Architecture

The Basic Data Infrastructure Framework (BDI) is an infrastructure framework for controlled data sharing, supporting automated advanced information logistics in the physical economy. Departing from traditional messaging paradigms, the BDI shifts towards event-driven data collection at the source, fostering efficient and secure coordination through proven publish-and-subscribe architectures.

This introduction provides a short overview of some issues which play a role in the design of the architecture. We start with some observations about data in a logistic environment. These observations are used in the formulation of architectural principles which are in turn the basis of BDI building blocks. Finally, these building blocks are grouped in functional subsets called KITs.

See [bdinetwork.org](https://bdinetwork.org) for a full account of these concepts.

### Observations&#x20;

* The data exchange patterns in typical operational networks are a result of “doing business” have specific characteristics:
  * The network of involved parties is driven by the fulfillment of an assignment - these networks are temporary and fluid, that is, members are added whenever necessary and the network is dissolved when the job is done.&#x20;
  * Data exchanges are between members of a closed group, i.e. the members are vetted in advance.
  * There can be time constraints on the exchange of data.
* A common data exchange infrastructure for operational networks should support:
  * Dynamic instances
  * Multiple concurrent instances
  * Controlled event-driven exchange
* Event-driven exchange of operational data within an instance must be:
  * Efficient: no polling, no unnecessary retrieval
  * Effective: easy distribution to multiple parties simultaneously&#x20;
  * Controlled:&#x20;
    * Limited exposure to malicious actors.
    * Only authorized parties can retrieve information.
    * Role based data access.
    * The Data Owner tracks access, providing a clear audit trail.
* The value of data:
  * Data has value
  * Data owners want to protect and monetize this value
* The importance of trust in global business networks
  * Identification authentication and authorization play an important role in establishing trust.
  * Zero trust - do not trust anyone before trust is established.
  * Perimeterless trust - do not base trust on membership of a closed group of trusted parties
