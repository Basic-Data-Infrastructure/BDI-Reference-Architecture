# Anomaly detection and autopsy support

### Logging and Monitoring (Audit log)

Comprehensive logging is a cornerstone of application security, capturing user actions, system events, and critical security data. Log analysis tools and intrusion detection systems are essential for identifying and responding to security incidents. Log format examples and recommendations for logged information assist in maintaining robust security practices.&#x20;

Logs should be able to be combined, sourced from separate entities that interact. This requires standardization of a minimum data set in the logs.&#x20;

Committed changes must be logged with details such as date/time, operator identity, and other relevant information. The audit log should be append-only, read-only, and accessible only by the Security Officer. To ensure integrity, consider logging to a separate component or isolated system.  must also be tracked in an append-only log.&#x20;

Input data must not be logged “as is” without either validation or encoding; logs should have a reliable format.&#x20;

When the system is operational in production, system status, load, request rates, errors etc must be logged and monitored. Alerts and notifications will be configured so that problems are detected quickly and can be resolved as soon as possible.&#x20;

Logging and monitoring may be partially implemented in an additional gateway/proxy services and must be in place in production.&#x20;

Logs should be exportable in a portable format (to be determined) for investigations of suspicious events, when sharing of logs between parties is necessary.&#x20;

Escaping (or encoding) is not just relevant when logging data. In general any ‘sink’ could be, for example an SQL-context, an HTML-context or an URL-context.&#x20;

The principle of escaping at the leaves means that escaping is applied at the last moment, when the context in which data is being used is known. Logging data is an example of such a ‘leave’.&#x20;

Access to logs must be restricted to authorized roles (CISO).

&#x20;**Incident Response**

Incident response involves a structured approach to handling security incidents, encompassing detection, containment, eradication, recovery, and post-incident analysis. A well-prepared incident response team and communication plan are paramount to address and mitigate security events effectively.
