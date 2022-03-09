---
title: "Microservices Security in Action"
tags: ["Sécurité 201"]
date: 2021-03-07T12:20:27-05:00
Note: 10/10
image: cover.jpeg
auteur: Prabath Siriwardena
---

 
---
Each microservice runs in its own container, and as a best practice, the container has to be an immutable server.3 In other words, after the container has spun up, it shouldn’t change any of the files in its filesystem or maintain any runtime state within the container itself.

---

You need a way to verify that the user context passed among microservices isn’t deliberately modified

---

This architecture, which enables the various components in a system to pick the technology stack that is best for them, is known as a polyglot architecture.

---

In a microservices deployment based on containers, audit logs aren’t kept at each node that runs the microservice; they’re published in some kind of a distributed tracing system like Jaeger or Zipkin

---

Most proxy servers support two modes of operation with respect to TLS: TLS bridging and TLS tunneling. TLS bridging terminates the first TLS connection

---

The API gateway centrally enforces security for all the requests entering the microservices deployment, including authentication, authorization, throttling, and message content validation for known security threats

---

The OAuth 2.0 security token represents both the third-party appli-cation and the user who delegated access to the third-party application to access an API on their behalf.

---

The API gateway terminates all the client connections at the edge

---

User context carries basic information about the end user, and client context carries infor-mation about the client application

---

how do you pass the user context to the upstream microser-vices? You have a couple of options: pass the user context in an HTTP header, or cre-ate a JWT with the user data

---

with JWT, you have an assurance that a man in the mid-dle can’t change its content and go undetected, because the issuer of the JWT signs it.

---

three common ways to secure communications among services in a micro-services deployment: trust the network, mTLS, and JWTs.

---

Challenges in mTLS include bootstrapping trust and provisioning keys/certificates to workloads/microservices, key revocation, key rotation, and key monitoring

---

Each microservice has its own public/private key pair, and the private key is used to sign the JWT.

---

Each microservice talks to a centralized PDP to authorize each request it receives.

---

the calling microservice can embed that JWT in the new JWT it creates to make a nested JWT (if JWT-based authentication is used among microservices) or pass the original JWT as-is, as an HTTP header (if mTLS is being used among microservices).

---

in a single trust domain, all the microservices trust one STS and accept only security tokens issued by that STS.

---

The -u flag provided to curl instructs it to create a basic authentication header and send it to the authorization server as part of the HTTP request

---

we chose OAuth 2.0 over protocols such as basic authentication and mTLS to secure your resource server

---

In the case of the client_credentials grant type, the authorization server validates the Basic authentication header and issues an access token if it’s valid.

---

Most of the OAuth deployments we see today use bearer tokens.

---

The client_credentials grant type is good when the client application doesn’t need to worry about end users.
If it has to, it should pick an appropriate grant type. The client_credentials grant type is used mainly for system-to-system authentication.

---

@Enable-WebSecurity

---

A privilege describes the actions you’re permitted to perform on a resource

---

privilege is mapped to a scope

---

instead of refusing to issue an access token, the server issues an access token bound to the scopes that you’re entitled to.

---

In an ideal world, the microservices developer should worry only about the busi-ness functionality of a microservice, and the rest should be handled by specialized components with less hassle. The API Gateway and Service Mesh are two architectural patterns that help us reach that ideal.

---

API Gateway deals with north/south traffic, while the Ser-vice Mesh deals with east/west traffic

---

One key aspect of microservices best practices is the single responsibility principle.

---

An API gateway helps in decoupling security from a microservice

---

None of us likes having to authenticate into an application again and again to perform operations. Therefore, if basic authentication is used, the application has to retain this information for long durations of time.
The longer this information is retained, the higher the chance of compromise.

---

After an application gets access to the username and password of a user, it can do everything that user can do with the microservice. In addition to accessing the microservice, the application can do anything with those credentials, even on other systems.

---

Then again, unlike basic authentication (where you send your password over the wire), when you use mTLS, the corresponding private key never leaves its owner—or is never passed over the wire.
That’s the main advantage mTLS has over basic authentication.

---

mTLS fails to meet access delegation requirements we discussed in section 3.2.2 in a microservices deployment

---

mTLS is mostly used to secure communication between a client application and a microservice, or communications among microservices. In other words, mTLS is mostly used to secure communications among systems.

---

You must properly understand the audience of your microservices through their characteristics and desires:
 Who—Ensure that only permitted entities are granted access to your resources  What purpose—Ensure that the permitted entities can perform only what they’re allowed to perform on your resources  How long—Ensure that access is granted for only the desired period

---

token introspection

---

When we use the OAuth 2.0 client_credentials grant type, the value of sub is the same as the value of client_id

---

An authorization server, unlike other services in an organization, usually is managed by a separate group of people who have special privileges because of the server’s sensitivity.

---

You may think that you’re burdening the microservice with extra responsibilities by expecting it to verify the client through mTLS. But mTLS verification happens at the Transport layer of the microservice and doesn’t propagate up to the Application layer.

---

An access token can be a reference token or a self-contained token (JWT)

---

The same-origin policy exists to pre-vent a malicious script on one website from accessing data on other websites uninten-tionally. The same-origin policy applies only to data access, not to CSS, images, and scripts, so you could write web pages that consist of links to CSS, images, and scripts of other origins. Figure 4.4 illustrates this scenario.

---

OpenID Connect is an identity layer built on top of OAuth 2.0. Most SPAs use OpenID Connect to authenticate users.

---

Vertical scaling increases the computing power on which our software runs, such as increasing the memory and CPU capacity of the corresponding servers.

---

horizontal scaling, we scale our deployment by adding more virtual machines

---

quota, such as 200 requests per second, and to enforce this quota at the API gateway

---

regular OAuth 2.0 tokens (or the reference tokens)

---

throttling per each operation of the API instead of applying for the entire API as a whole.

---

web application firewall (WAF), which runs before the API gate-way and intercepts all the requests. Imperva, Akamai Technologies, Cloudflare, and AWS WAF are some popular WAF solution providers that also provide DoS and DDoS prevention.

---

The modern term for monitoring and analytics is known as observability

---

Prometheus is a popular open source monitoring tool for microservices

---

Grafana is an open source data visualization tool. It can help you build dashboards to visualize the metrics being provided by Prometheus or any other data source

---

Prometheus pulls metrics data from microservices on a periodic time interval. As you’ve learned, this is known as scraping

---

Open Policy Agent (OPA)

---

Access-control policies evolve as business requirements change—so every time we have to change our access-control policies, changing the microservice code is not a good practice.

---

OPA server; these policies check whether a user/system that’s accessing a resource with an access token bears the scopes required for accessing that resource. We’ll use OPA policies to make autho-rization checks on the Order Processing microservice.

---

Not all microservices use JSON over HTTP for service-to-service interactions, and gRPC is already a popular pick as an alternative

---

Ideally, during the continuous integration/continuous delivery (CI/CD) pipeline, the keys should be generated and provisioned to the microservices.

---

TLS first has to generate a public/private key pair, and then create a certificate-signing request (CSR) and submit the CSR for approval to the team that maintains the corporate CA. If everything looks good, the signed certificate is handed over to the developer who initiated the signing request. Then the developer deploys the certificate and the keys to the microservice. But this process is painful in a microservices deploy-ment with hundreds of services spinning up and down all the tim

---

Lemur isn’t a CA, but it knows how to integrate with a CA and generate a signed cer-tificate. Microservices developers shouldn’t worry about the certificate-signing proces

---

Certificate revocation can happen for two main reasons: the corresponding private key is compromised or the private key of the CA that signed the certificate is compromise

---

Netflix microservices deployment, service-to-service communication is secured with mTLS using short-lived certificates

---

a system identity or long-lived credentials residing in a Trusted Platform Module (TPM) or an Intel Software Guard Extensions (SGX) chip tightens security.

---

Long-lived credentials are secured with a TPM or an SGX chip. Loading such long-lived credentials frequently is a costly operation. Short-lived credentials, on the other hand, are kept in memory.

---

Netflix, for example, rotates keys every 4 minutes in its microservices deployment

---

Netflix, for example, uses TPM or an SGX chip with tightened security to secure its long-lived credentials.

---

three pillars of observ-ability: logging, metrics, and tracing.

---

mTLS is the most popular way of securing interservice communications among microservices.

---

OCSP stapling makes OCSP a little better. It takes the overhead of talking to the OCSP endpoint from the TLS client and hands it over to the server

---

In practice, you use JWT along with mTLS, together, in most cases.

---

JWT helps you achieve two things. First, it helps you pass the end-user context across microservices in a manner that can’t be forged. Because the claims set of the JWT is signed by the STS, no microservice can change its content without invalidat-ing its signature. Also, JWT helps you secure service-to-service communications. One microservice can access another microservice only if it carries a valid JWT issued by the trusted STS. Any recipient microservice rejects any request without a valid JWT.

---

With mTLS alone, you can’t achieve nonrepudiation. But when you use a self-issued JWT, all the data added to it is bound to the owner of the corresponding private key that’s used to sign the message, and helps you achieve nonrepudiation

---

The nested JWT carries the iden-tities of the end user and the calling microservice in a manner that can’t be forged!

---

JWT addresses two main concerns in a microservices security design: secur-ing service-to-service communications and passing end-user context across microservices.

---

When the identity of the microservice isn’t relevant, but the identity of the end user (system or human) is, you should prefer using JWT over mTLS. But still, in practice you will use JWT with mTLS together to build a second layer of defense.

---

Having a different or new JWT for each interaction among microservices is a more secure approach than sharing the same JWT among all the microservices.

---

A self-issued JWT is issued by a microservice itself and used for authentication among microservices.

---

text-based protocol like JSON, you can use a binary protocol like Protocol Buffers (Protobuf)

---

Unlike in HTTP, gRPC doesn’t have headers

---

gRPC operates over HTTP/2, which is significantly more efficient than HTTP/ 1.1 because of request response multiplexing, binary encoding, and header compression.

---

Unlike in HTTP/1.1, HTTP/2 supports bidirectional streaming, which is bene-ficial in microservice architectures.

---

the recipient microservice is decoupled from the calling microservice

---

The client application should securely store and use the client secret. For example, you should never store a client secret in cleartext; instead, encrypt it and store it in persistent storage (such as a database).

---

the client application can use mTLS instead if stronger authentication is required

---

As we discussed earlier in this chapter, because the value of the access token is passed in the URL, it will be in the browser history and also possibly logged into server logs.

---

A typical difference between an MPA and a SPA is that in an MPA, each request for new content reloads the web page. But in a SPA, after the application has been loaded into the browser, no page reloads happen

---

To limit the visibility of the filesystem to a running process, chroot is still popular today and is considered a best practice by system administrators.

---

The main value Docker provides over traditional Linux containers is portability.

---

Protocol Buffers are a flexible, efficient, and auto-mated mechanism for serializing structured data. You can think of it as JSON or XML but with the following exceptions:
 Much smaller size for representing a given message  Much shorter time duration for processing a given message  Much simpler to understand, given its resemblance to programming languages

---

HTTP/2 provides request multiplexing and header compression, which increase its performance significantly.

---

over HTTP/1.x, if the client wants to make multiple requests to the server (in parallel) to improve performance, multiple TCP connections have to be used

---

The API gateway works mostly with north/south traffic—the traffic between applications (or consumers) and APIs

---

It deals with east/west traffic (the traffic among microservices) to take most of the burden off of the microservices, with respect to security processing and other nonfunctional requirements.

---

approach we fol-lowed in chapter 6 and chapter 7 while securing inter-microservice communications with mTLS and JWT. You can even call this model an embedded service mesh (figure K.1) or an in-process service mesh.

---

Service Mesh architecture consists primarily of two planes: a data plane and a control plane

---

HTTP/2 provides request multiplexing and header compression that increases its performance significantly compared to HTTP/1.1