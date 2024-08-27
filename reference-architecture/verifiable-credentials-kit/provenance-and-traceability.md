---
description: >-
  As adopted from
  https://dssc.eu/space/BVE/357075283/Provenance+%26+Traceability
---

# Provenance & Traceability

**Summary**&#x20;

This building block provides guidance support provenance, traceability, logging, audits, etcetera, in a standardized way for the use cases it supports.

Some use cases need additional data over the actual data being shared. This additional data may need the same or different access and usage management than the actual data itself.

It must be defined which information about this transaction is stored and how the access and the usage are regulated and controlled.

The evidence itself is again data, which is shared among different participants. Therefore, many concepts applied to data can also apply to this evidence, e.g., syntax and semantics of the evidence, access & usage policies on multiple levels.

The amount and granularity of evidence should be reasonable and appropriate to balance between the requirements of the availability of evidence and the scalability of the solution. The advantages and disadvantages of different approaches like a centralised, a decentralised, or a distributed solution must be assessed and understood.

A solution needs to fulfil the requirements of the governance, legal and contractual requirements, as well as other policies requiring such evidence, and balance this with the technical requirements like resource management, scalability, consistency, availability, and others.

The requirement for observability, traceability and provenance tracking is usually found in highly regulated industries or in cases dealing with high-value data. Data being used for artificial intelligence is an example of a situation where such mechanisms can be required by law (in this case, the AI Act).

**Purpose**&#x20;

The purpose of this building block is to provide approach for the provenance and traceability.

The forward-looking direction of a data value chain is referred to as traceability, i.e., a data provider can receive evidence of what was done with the data. The backwards-looking direction of a data value chain is referred to as provenance tracking, i.e., a data consumer can receive evidence on the origin of the data and the treatment of the data during its processing in the value chain. Both traceability and provenance are important functional requirements for each participant in such a data value chain, which can consist of multiple data transactions.

**Implementation Considerations**

This building block addresses the following capabilities:



|                                                                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Framework for requirements for observability                              | Data transactions can require the observability of each activity in the transaction, including the provisioning of evidence. The requirement for observability can be stated by law, Governance Framework , Contract between parties or other policies.                                                                                                                                                                                                              |
| Third parties to provision or use evidence:                               | The provisioning and usage of this evidence can be used by the parties directly involved in the transaction and optionally by a third party not directly involved in the transaction. Third parties can be involved for different purposes, e.g., auditing, usage accounting and billing, or compliance.                                                                                                                                                             |
| Mechanisms to provide and use evidence of the activities of a transaction | This is particularly relevant when multiple parties are involved in the value creation, so called value chains, as such parties have a different interest. Depending on the use case and requirements, the participants (themselves or with 3rd parties) must keep logs of the transactions, which can be used for non-repudiation in case of disputes.                                                                                                              |
| Mechanisms to verify the origins:                                         | The provenance of data can be relevant in many use cases and could be a potential driver for added value in data sharing. The requirements for proper verification of the origins of the data can be stated by law, governance framework, contracts between parties or other policies. Provenance could refer to either the traceability of the data in the value chain, as explained above, or the origin of the data itself from a trusted and/or verified source. |

**Interlinkages with other building blocks**&#x20;

&#x20;Federation of assoiciation

Events pub/sub



**Elements and their Key Functions**

Nonrepudiation provides proof of the origin (provenance) , authenticity and integrity. It provides assurance to the sender that its message was delivered, as well as proof of the sender's identity to the recipient. This way, neither party can deny that a message was sent, received and processed.​

Example usage: The proverbial use case: man at the gate and the security guard has to verify claims. The Warehouse stores and handles goods for the client. De charter needs to provide evidence of assignment of the transport and compliance to the needed professional qualification (ie ADR-certificate)​.

In the BDI stack, we refer to Registers with claim (Association-, Representation, Professional Qualification- and Business Reputation registers), however this does not mean ‘central’. Practical deployment is explored: The ‘Secure Issuance of Goods demo’ works, however many calls / interactions to federated infrastructure is needed not benefitting non-functionals and robustness of the solution in complex scenarios.​

Direction that is being explored now is by combining ‘Embedded JWTs’ with VC’s (Verfiable Credentials) for a powerful mechanism for secure, flexible, and privacy-preserving information exchange whilst providing a Chain of Trust (tracebility):​

* Enables multi party trust (Chain of Trust)​
* Captures needed delegation and mandates​
* Seperation of concerns – you only need to know what you need to know​
* Privacy preserving - Holder can choose which claims to reveal to a verifier​
* Nonrepudiation​
* Known and in use technology, well defined and accepted protocols for token creation and embedding​

**Core Design Decissions**

The following design decisions should be considered:

* How can the origin of the data be established?
* How can you find out how data has travelled through the chain?
* Can the data origin be trusted?
* Is there a way to find out what and where something went wrong in the chain of transactions?
* Can other participants store/keep logs of data sharing that I am part of?
* Will I be able to use traceability data?
* How can you ascertain who acted on the data and at which point?

**Future topics**&#x20;

Future work: Claims need to be stored for usage in a transactions. Ideally the subject should ‘hold’ the claim (like EU Digital Wallets). This is the defined EU direction. Not immidiate needed to work within the BDI scheme.

* The BDI provides nonrepudiation across the supply chain through a Chain of Trust based on Embedded JWT’s combined with VC’s to create a powerful mechanism for secure, flexible, and privacy-preserving information exchange based on known technology. Reference to be developed​
* (EU) Wallet’s to be researched on readiness (ecosystem) and easy of implementation​

To be potentially covered in future versions.

* Examples of provenance data products
* Examples of traceability data products

&#x20;
