---
cover: >-
  https://images.unsplash.com/photo-1542382257-80dedb725088?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxuZXR3b3Jrc3xlbnwwfHx8fDE3NzA3Mzc0NzR8MA&ixlib=rb-4.1.0&q=85
coverY: 0
coverHeight: 427
---

# Token Exchange for Federated Association-to-Association Communication

## 1. Introduction

The foundation of the BDI are Associations. Within an Association, members can obtain access\
tokens from an Association Register (ASR). However, enabling secure communication across\
Associations requires bridging distinct authorization domains without introducing a central broker.

This building block defines the Token Exchange Service (TES). A TES refers to a standards-track profile that uses OAuth 2.0 Token Exchange to enable controlled, policy-based cross-Association token exchange. TES reuses existing OAuth servers and avoids introducing a centralized authority. Multiple architectural approaches can be used to implement a TES. The architectural design in this block is based on the Proving Ground experiment. In this experiment, an ASR Proxy and a Trust Register are used. A detailed report of this Proving Ground experiment is attached to this page.

{% hint style="info" %}
The architecture and processing model described here were validated in a reference implementation\
experiment.&#x20;
{% endhint %}

## 2. Purpose of the building block

The purpose of this building block is to enable Association-to-Association communication: members of different Associations that communicate with each other. To enable this communication, Associations will be administrated in a to-be-developed Trust Register, which will be part of the ASR. The intent is to use this trust to facilitate the trust between members of different Associations while the members only communicate with their own ASR to establish the trust.

The baselines is that a large number of independent BDI associations will coexist without any overarching governance structure to federate at an Association‑to‑Association level on behalf of their members. It is intended for BDI associations to form federations with voluntary common standards where necessary to maintain interoperability potential. These include topics such as authentication, roles, semantics, and similar areas.&#x20;

Within the BDI, OAuth M2M-authentication plays an important role in obtaining a secured and trusted M2M connection between a client of party A and a server of party B. This building block extends the role of OAuth by using an extension on Token Exchange as the mechanism through which the Client can obtain their own BDI-association type tokens. The server trades token from its own type for the expected type, without losing the context of the requesting party.&#x20;

## 3. Concepts

### 3.1 Terminology&#x20;

Expand the following terns for an explanation of this term in the context of the TES.&#x20;

<details>

<summary><strong>Association</strong></summary>

A local trust domain with its own OAuth 2.0 authorization server and onboarding policy.

</details>

<details>

<summary><strong>Association Register (ASR)</strong></summary>

The Association's OAuth 2.0 authorization server plus onboarding and membership administration.

</details>

<details>

<summary><strong>Token Exchange Service (TES)</strong></summary>

A function implemented within the ASR that performs controlled token exchange for cross-Association use.

</details>

<details>

<summary><strong>ASR Proxy</strong></summary>

The TEA-facing endpoint that receives member requests and orchestrates issuance or exchange.

</details>

<details>

<summary><strong>Trust Register</strong></summary>

A data store maintained by an ASR describing trusted peer Associations and their relevant endpoints and policy.

</details>

<details>

<summary><strong>Target Association</strong></summary>

The Association that operates the authorization server which issues the token to be used at the target resource.

</details>

<details>

<summary><strong>Origin Association</strong></summary>

The Association in which the requesting member is onboarded and from which the initial token originates.

</details>

### 3.2 Architecture&#x20;

TES adds two functional components to an ASR:

1. **ASR Proxy**: a token service endpoint used by Association members.
2. **Trust Register**: policy and routing for trusted peer Associations.

The member interacts only with its Origin Association ASR Proxy. Figure 1 shows an overview of the token exchange architecture. In this figure _Party 1_ (a member of Association A) aims to share data with _Party 2_ (a member of Association B). This process is explained in more detail in the upcoming sections.&#x20;

<div data-full-width="true"><figure><img src=".gitbook/assets/260211 Plaat Token Exchange voor Gitbook (1).png" alt=""><figcaption><p><strong>Figure 1</strong>: Overview Token Exchange Architecture</p></figcaption></figure></div>

### 3.3 OAuth M2M authentication&#x20;

When a Client initiates a connection with the Server, the identity of the Server is first validated using the Server's TLS-certificate, ensuring the Client is connecting to the right party. Secondly, the connection is encrypted to avoid unwanted eavesdropping. Thirdly, the Client provides the Server with an Access Token, so the Server can trust the identity of the party behind the Client. The Client receives this Access Token from the OAuth server of its own Association.&#x20;

During onboarding, the OAuth server and the Client exchange a secret that is exclusively known by them. The Client requests the OAuth server for a short-lived token containing the following:&#x20;

* The token provider (OAuth server)
* The token requestor (Client)&#x20;
* Target (Server of the other party)
* Restrictions (e.g. only reading or writing rights)
* Datetime of the token issuance
* Duration of token validity (often a maximum of 30 seconds)
* A digital signature added by the OAuth server, which ensures that the contents remain unchanged&#x20;

The OAuth Server provides the Client with this Token, and the Client sends it to the Server. The Server then checks its content and the signature with the OAuth server. Here, it is assumed that the Client and Server are onboarded within the same Association and are using the same OAuth server. &#x20;

### 3.4 Federation with Token Exchange

The previous section ended with the assumption that the Client and Server are both onboarded within the same Association and OAuth server. If this is not the case, the abovementioned method cannot be used. Luckily, the OAuth standard has created an extension to resolve this issue: the Token Exchange.&#x20;

To allow for communication between Associations, the following steps have to be followed:&#x20;

{% stepper %}
{% step %}
### Token Exchange Service&#x20;

The two Associations that wish to communicate have to create their own Token Exchange service (the "Exchange Client"). This Client is onboarded — and therefore known — within the other Association, and can request a Token Exchange from the other party.
{% endstep %}

{% step %}
### Request access

When the Client requests an access token to gain access to the Server, the OAuth server recognizes that the Server belongs to a different Association.&#x20;
{% endstep %}

{% step %}
### Exchange the token

The OAuth server generates a token and uses the Exchange Client to request the other OAuth server for a token exchange. This new token has the same content, but in the standard format of the other Association, signed by their OAuth server.&#x20;
{% endstep %}

{% step %}
### Providing the token

The exchanged token is returned and offered to the Server through the Client. The Server reads this token as a regular token of its own OAuth server, without losing the context of which party makes the request. This allows the Data Custodian to maintain the transparency needed to perform the local evaluation on the access rights.&#x20;
{% endstep %}
{% endstepper %}

### 3.5 Architecture&#x20;

TES adds two functional components to an ASR:

1. **ASR Proxy**: a token service endpoint used by Association members.
2. **Trust Register**: policy and routing for trusted peer Associations.

The member interacts only with its Origin Association ASR Proxy. Figure 1 shows an overview of the token exchange architecture. In this figure _Party 1_ (a member of Association A) aims to share data with _Party 2_ (a member of Association B).

<div data-full-width="true"><figure><img src=".gitbook/assets/260211 Plaat Token Exchange voor Gitbook (1).png" alt=""><figcaption><p><strong>Figure 1</strong>: Overview Token Exchange Architecture</p></figcaption></figure></div>

### 3.6 Benefits of Token Exchange&#x20;

Some benefits of the Token Exchange solution are the following:&#x20;

* Subtle compatibility issues are avoided
* Server only needs to trust its own Association and OAuth server
* The API becomes standard and trustworthy&#x20;

### 3.7 Trust Model

Trust is established between Associations and recorded in the Trust Register. The Trust Register entry for a Target Association must at least contain the following:

1. a stable Association Identifier for the Target Association,
2. the token endpoint URL for the Target Association,
3. the client authentication method and credentials to be used by the Origin ASR Proxy when calling the Target token endpoint.&#x20;

{% hint style="danger" %}
Note that Associations must not assume mutual trust unless explicitly configured.
{% endhint %}

### 3.8 Adding assurance hash

Within the BDI framework, it is provided that information about an onboarded party is made digitally available to a counterparty, enabling that party to assess, based on the associated risk, whether there is sufficient trust in the company. This assurance information does not change frequently, but when it does, the counterparty should be informed immediately.&#x20;

A possible solution is to add a hash of the assurance information to the access token. This stems from the Association's onboarding register. The receiving Server can compare this hash to the hash of the locally saved Assurance information per party. When the hash does not match, new information should be requested.&#x20;

The benefit of this approach is that the number of tokens and interactions decreases, while every connection is still checked for changes.&#x20;

### 3.9 Protocol overview

A member requests a token from the Origin ASR Proxy using an OAuth 2.0 token endpoint style request. When the member requests access for:&#x20;

* **a resource within the Origin Association**, the ASR Proxy obtains an access token using the local authorization server.
* **a resource within a Target Association**, the ASR Proxy exchanges the Origin token for a Target token at the Target authorization server using the current building block.&#x20;

## 4. Interlinkages with other building blocks

<a href="readme/trust-kit/association-register-1.md" class="button secondary">Association Register</a>&#x20;

## 5. Future topics & Future Reading&#x20;



