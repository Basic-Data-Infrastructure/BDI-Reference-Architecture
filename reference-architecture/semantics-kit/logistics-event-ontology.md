# Logistics event Ontology

There is a growing demand from Beneficial Cargo Owners (BCO) to create more visibility in the supply chain: visibility of the operational planning and execution of all the steps between ordering goods and receiving the consignments in the distribution centre or warehouse of the BCO.

Each transport leg in the consignment journey results in one or more events which are to be communicated between parties directly involved in the transport leg. The event communication leads to data exchanges, typically using specific systems, platforms and data formats. The diversity of parties, systems and data formats are a barrier to automated exchanges.

The issue to be solved is the existence of a wide variety of data formats and semantic definitions in supply chains:

* beneficial cargo owners who want to track & trace their goods cannot adopt all the data standards in use;
* the logistics partners want to keep using their existing data standards;
* (global) unification of data standards is not a practical option for the near future.

The concept of an event envelope is introduced, named Logistics Event Ontology (LEO). The BDI framework separates the envelope from the payload, separating event data from other operational data. The BDI envelope is a notification of an event with additional data and meta-data, combined with a link to the endpoint of the data owner where more (sensitive) data about the event may be requested. The data owner evaluates the request and the party requesting access, and provides data on a 'need-to-know' basis.

The Logistics Event Ontology (LEO) is derived from existing standards, especially the GS1 EPCIS standard. OpenEPCIS is an open-sourced fully compliant implementation of the EPCIS standard, allowing for extensions on the standard to support future events.

LEO supports the use of standard operational trip data by operators (such as carriers) to generate notifications of events to cargo owners or authorities, leading to efficiency and productivity increases.

### Documents

{% file src="../../.gitbook/assets/20250120_BDI-Logistic-Event-Ontology.pdf" %}
