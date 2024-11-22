# Trusted Goods Release - Event Demo

The "Event Demo" (Demo Phase 3) further advanced the "Trusted Goods Release" process by integrating real-time event notifications. This phase demonstrated how event-driven updates, particularly gate-out events, could be leveraged to improve logistics transparency and coordination. Utilizing an event broker (Apache Pulsar) and building on the iSHARE framework, this demo highlighted the importance of timely, secure data sharing in logistics processes.

In Demo Phase 3, the focus was on implementing an event-based notification system to communicate critical logistics events. Key components included:

1. **Setup and Registers**:
   * Implementation of Authorization and Assignment Registers to manage permissions and roles associated with each transport order.
2. **Event Broker**:
   * Use of Apache Pulsar as an event broker to handle event data propagation, allowing secure, role-based access to notifications.
3. **Mockup Systems**:
   * Simulated environments for ERP, Warehouse Management System (WMS), and Transport Management Systems (TMS) to incorporate event notifications and handle delegation to subcontractors.
4. **Messaging and Events**:
   * Focus on gate-out events, notifying the shipper when goods leave the distribution center. Events were managed through a dedicated topic per transport order, enhancing traceability and ensuring only relevant parties accessed event information.
5. **Demonstration and Presentation**:
   * The demo was presented in a series of project meetings, with discussions on implementation insights and future improvements.
6. **Non-Functional Observations and Findings**:
   * Insights from the demo led to suggested improvements in architecture, event handling, and component documentation.
   * Identified potential challenges, including scalability of the event broker, secure access to event data, and data protection strategies such as publishing only URLs to sensitive information instead of the data itself.
   * Explored alternative methods, such as webhooks and long polling, to further refine notification mechanisms.

The Event Demo demonstrated the feasibility of using real-time event notifications in logistics. By integrating event brokers and secure data-sharing protocols, this phase emphasized transparency and control in logistics processes, laying the groundwork for scalable, event-driven solutions in the industry.

You can find the document with lessons learnt attached to this article (in Dutch).

Documentation in GitHub [https://github.com/Basic-Data-Infrastructure/demo-vertrouwde-goederenafgifte/tree/fase-3](https://github.com/Basic-Data-Infrastructure/demo-vertrouwde-goederenafgifte/tree/fase-3)

{% file src="../../.gitbook/assets/20241002_DIL-VGU-bevindingen-fase-3.pdf" %}
