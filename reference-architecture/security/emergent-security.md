# Emergent security

### HTTP processing; rate limiting, buffering, other limits

The system should mitigate denial of service scenarios:

Rate limiting to prevent overloading the service



Request/response buffering to ease handling of slow clients

Header size limits.

Prevent caching for endpoints (_Cache-Control: no-store_ unless explicitly allowed for an endpoint)

Set charset on endpoints (including _application/json_ endpoints)

Some of these mitigations may be implemented in an additional gateway/proxy service and  should be in place in production.

### Exposed endpoint protection

Endpoints that are exposed to the Internet are a prime attack surface. One of the options to reduce the attack surface is to limit access to a specific port in the firewall only to authenticated systems, for a limited period of time (“port-knock” service). This has been investigated by the BDI  [https://bdinetwork.org/wp-content/uploads/2024/07/20240716-BDI-Port-Knocking-Security.pdf](https://bdinetwork.org/wp-content/uploads/2024/07/20240716-BDI-Port-Knocking-Security.pdf)

\


***

