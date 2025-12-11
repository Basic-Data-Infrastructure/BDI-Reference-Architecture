# Edge agreements

### 1. Summary

Edges are the boundaries of an association. Edge Agreements define how members of the association can interact with non-members of the association

### 2. Purpose of the building block

{% hint style="info" %}
One can identify three types of “edges” or boundaries:

1. The boundaries that arise from specific agreements in groups that all use the BDI framework but have specific agreements per group
   * The principle of subsidiarity of governance will lead to many “soft” boundaries: specific rules, roles and regulations that are common within a sector but differ from the equivalent agreements in other sectors
2. The boundaries that are to be crossed when “non-BDI” actors are part of a specific operational network and need to be incorporated in the digital data exchange.
   * An example of this is the delivery of a shipment towards a car-manufacturing company. While the Shipper and transporter might be part of the BDI-network. The car manufacturer is part of the industry data-sharing network. Both networks have different rules of participation but still need to be able to cooperate with each other in the operational process.
3. The boundaries that are to be crossed when “non-BDI” or “data-sharing network” actors are part of a specific operational network and need to be incorporated in the digital data exchange.
   * The most obvious example is the delivery of a shipment to a receiving party. The receiving party may very well not be a member of a BDI association, unaware of the BDI framework and may have less Logistics IT maturity. The shipper and transporter would like to maintain the benefits of the automated controlled digital data exchange in such a case, without reverting to the default paper-based process.
   * This boundary has both technological (IT) and legal (liabilities) aspects that interact with each other: the shipper, receiver and transporter execute two commercial transactions at the same time. The shipper executes the delivery of the goods sold to the receiver by means of a transport order which is another commercial transaction between the transporter and the shipper.

Edge agreements are standards for interactions on a boundary. This standard may be local to a group (or Association), or more global over multiple groups. The BDI has a listing available of a set of potential agreements that can be used in such a process. In these agreements it is also indicated which are obligatory and which are not.
{% endhint %}

### Example for digital shipment data

Transport is a consequence of trade. In the terms and conditions of a purchase agreement, the seller and buyer agree, among other things, who should take care of the transport of the shipment. In international trade, sellers and buyers can use the Incoterms 2020. These are standardized agreements about who arranges what (e.g. transport, but also insurance and customs formalities), payment and payment securities, at what point the responsibility is transferred (e.g. when a container is lifted over the railing of a ship), and the like.

Standardized terms and conditions have been developed to codify roles, responsibilities and liabilities between the seller, a carrier and the buyer. International treaties harmonize these conditions between countries. The aim is clear: this standardization and harmonization facilitates trade.

These conditions are specifically tailored to a modality. The CMR Convention, for example, was set up for international road transport. The CMNI Convention exists for inland navigation. In the maritime sector, the Hamburg Convention (United Nations Convention on the Carriage of Goods by Sea) is leading. The Montreal Convention sets out the liability of air cargo carriers, and IATA also has specific conventions for the carriage of dangerous goods and live animals by airplanes.

All these treaties have a main document that is intended for commercial agreements about transport in the context of a commercial transaction.

When the paper-based process is “digitized” the legal boundary interactions (“edge agreements”) have to be redefined. Suddenly questions arise on the legal status of digital “signatures”, i.e. signatures that in the paper process are a record of the handover moments.

Digitally recording a transaction is something that causes a lot of unrest and uncertainty for many entities. There are many technological variants and possibilities, each with their own advantages and disadvantages. And some technological secure variants do not resemble the tried and trusted 'wet' signature, and vice versa. A PDF with a pasted-in scan of a signature gives a familiar feeling but is a very weak method. A geo-tagged, time-stamped digital image of the delivered shipment at the desired location does not require digital infrastructure for the receiver, but can it be used as evidence in court if there is a conflict?

For many users, including authorities, digitized processes are an unknown field, and the risks and implications of the various variants are not immediately clear. There also exists doubt about what is required and enforced by law (fined when not complied with), what is a commercial business choice between parties, and how does that work out when a business conflict arises.

Edge agreements are a building block that helps parties to overcome this uncertainty, build and codify acceptable practices, standardize them and gain the benefits of digital transactions. Edge agreements are accepted by parties involved in any commercial transactions that take place within and on the edge of the BDI.

### Implementation example

#### The boundaries that are to be crossed when “non-BDI” or “data-sharing network”

A practical implementation example might be constructed as follows.

A group of entities in a sector defines an enumerated list of practices, including roles, responsibilities and liabilities. The list spans a range of trade-offs between ease-of-use and levels of legal and IT-security. For example:

* “A handover is defined by the driver hitting a button, that records:
  * driver ID,
  * license plate
  * time,
  * geolocation
  * shipment ID”
* “A handover is defined by the driver taking one or more digital pictures of the shipment unloaded, geo-tagged, time-stamped”
* “A handover is defined by a qualified digital signature of the receiver and the driver”

The shipper identifies the acceptable practices for a specific transport order (“all acceptable” or “only qualified signature”) and makes them part of delivery conditions in the sale to the buyer. This gives clarity and certainty to all parties involved and gives legal (commercial) backing. In turn, other parties involved in this transaction, like a transportation company, now know what to do when delivering the goods to the buyer of the goods to confirm handover.

### Implementation Considerations 

Edge interaction protocols are vital for a functioning supply chain. The definition and maintenance of these protocols are common pool resources. It is recommended that associations agree upon a set of protocols to deal with parties on the edges of the data-sharing network.

### Use case scenario:

1. Acme Inc. buys a batch of hydrofluoric acid from its supplier Lets-B-chemical. Acme inc. agrees to the terms and conditions of delivery from Lets-B-Chemical including terms on proof of delivery.
2. They agree that Lets-B-chemical will hire De Snelle Visser for transport
3. It is known that Acme Inc. does not use any IT.
4. Lets-B-Chemical and De Snelle Visser are accustomed to working together according to the BDI framework where status updates on shipments are done through event-driven coordination.
5. Lets-B-Chemical informs the transport company De Snelle Visser that a digital confirmation of handover can be done by either a picture of the delivery or an SMS confirmation. This is also agreed upon in step 1 between Lets-B-chemical and Acme inc.
6. The driver working for De Snelle Visser delivers the goods to Acme Inc. and takes a picture of the delivered hydrofluoric acid.
7. The confirmation of delivery with the provided evidence will trigger a status update on the shipment from “in transit” to “delivered”.

<figure><img src="../../.gitbook/assets/Edge Agreements.png" alt=""><figcaption><p>Overview of interactions between parties</p></figcaption></figure>

In this scenario, the BDI supports both the shipper (Lets-B-Chemical) and the transportation company (De Snelle Visser). However, the buyer (Acme Inc.) is not part of the BDI or any other network due to its low IT maturity level. As a result, the BDI cannot directly assist the buyer, which reduces its effectiveness for both the shipper and the transportation company. Establishing a set of defined agreements to address situations like this would enhance overall digitization and provide clear legal backing for these handover moments. This case is not unique; many supply chains still rely on paper for such handovers.

### Interlinkages with other building blocks

* Terms and Conditions
* Policies

### Elements and their key functions

* Agree on a set of accepted edge interactions like (but not limited to)
  * Picture of the freight taken by the driver
  * SMS confirmation between the buyer and seller
  * Signature on tablet by the driver and buyer

### Core design decisions

When starting an association, it is advisable to establish a set of "edge agreements." These agreements should be developed across three layers, all of which need to be considered:

* _Association-Specific_: These agreements are tailored to meet the unique needs of the association, which may vary by sector, geographical location, or specific theme. For example, in bulk transport, the quantity delivered might differ depending on the customer or transport company due to factors like time delays or poor internet connectivity. An edge agreement could be established to define the correct weight of goods upon delivery.
* _Common_: Utilize a standardized set of edge agreements available in the BDI repository. For instance, an agreement could state that a picture of the delivered goods serves as sufficient proof of delivery.
* _Global_: Seek to align these edge agreements with those used in other sectors and standards whenever possible, promoting convergence and consistency.

### Future topics

* Proving inclusion of the protocol in the proving grounds
* Further describe data exchange with non-BDI actors
* Further describe edges with BDI actors.

### Further reading

* [https://digitalshipmentdata.org/](https://digitalshipmentdata.org/)
* [https://www.evofenedex.nl/kennis/internationaal-ondernemen/incoterms/de-11-incoterms-2020](https://www.evofenedex.nl/kennis/internationaal-ondernemen/incoterms/de-11-incoterms-2020)

{% file src="../../.gitbook/assets/Waybill complete.pdf" %}
