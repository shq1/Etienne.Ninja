---
title: "Practical Cloud Security A Guide for Secure Design and Deployment"
tags: ["Sécurité 201"]
date: 2021-03-07T12:20:27-05:00
note: "8/10"
image: cover.jpeg
auteur: Chris Dotson
---


 
---
If you are in a very high security environment and your threat model includes protecting data in memory from a privileged user, you should seek out a platform that supports memory encryption; it goes by brand names such as Intel SGX, AMD SME, and IBM Z Pervasive Encryption.

---

You must track who has access to the private keys, because these individuals have the ability to impersonate your site.

---

1Zero-knowledge encryption means that your provider has no technical way of decrypting the data, usually because you only send encrypted data without the keys. This sharply limits what the provider can do, and is most suitable for backup services where the provider just needs to hold a lot of data without any processing

---

OpenID Connect is a much newer authentication layer, finalized in 2014, on top of OAuth 2.0

---

The legacy application will trust this frontend service (often a reverse proxy) to per‐ form authentication, and it must not accept connections from anything else

---

You cannot put a heavyweight vulnerability management tool that uses a few percent of your CPU in every container, like you would in virtual machines

---

Continuous integration and continuous delivery allow smaller changes to be deployed to production on each iteration. Smaller changes reduce the risk of catastrophic failures and make troubleshooting easier for problems that do arise.

---

Many frameworks have built-in protections against cross-site scripting (XSS), cross-site request forgery (CSRF), SQL injection (SQLi), clickjacking, and other types of attacks

---

middleware or platform components, such as databases, application servers, or message queues

---

The first approach is to use scanners that pull apart the container images and look through them for vulnerabilities

---

I recommend the use of immutable containers that are replaced by a new container whenever any change is needed

---

sof t ware composition analysis (SCA) tools look primarily at the open source dependencies that you use rather than the code you’ve written

---

Interactive application security testing (IAST) tools do a little bit of both static scan‐ ning and dynamic scanning.

---

IAST solutions can often be more effective at finding problems and eliminating false positives than either SAST or DAST solutions

---

Remember that the real attackers will usually have more time than your pentesters do!

---

if the pentesters are coming back with results that an automated scan could have found, you’re probably wasting money

---

- Contrast provides IAST and RASP solutions

---

container scanner.

---

Using an existing framework for evaluating risk, such as NIST 800-30 or ISO 31000, can be much easier than starting from scratch.

---

For each tool, what percentage of the in-scope systems is it able to cover

---

Forward proxies are most often used to put rules on what traffic is allowed out of the network

---

Reverse proxies can improve security if there’s a vulnerability in a protocol or in a particular implementation of a protocol

---

Overlay networks are often used to allow your virtual systems to communicate with each other as if they were on the same network

---

A VPC, despite the name, generally deals only with network isolation, by allowing you to create separate virtual networks to keep your applications separate from other cus‐ tomers or applications.

---

Communications between components that will always remain on the same operating system, or between different containers in a pod in Kubernetes, do not gain a security benefit from using TLS.

---

In Kubernetes environments with Istio, Istio Auth can provide keys and certifi‐ cates to Kubernetes containers

---

WAFs can also help you respond quickly to a new vulnerability, because it’s often faster to configure the WAF to block the exploit than to update all of your systems.

---

RASP modules must support the specific language and application environment, whereas WAFs can be used in front of almost any application.

---

explicit proxy, enforced by configuring each component not to communicate directly with the outside world, but instead to ask the proxy to make the connection on its behalf.

---

transparent proxy. In this case, something on the network (such as an intelligent router) sends the traffic to the proxy. The proxy then evaluates the request (for example, to see whether it’s going to a whitelis‐ ted URL) and makes the request on behalf of the backend system if it meets the vali‐ dation requirements. S

---

AWS CloudTrail, Azure Activity Log, Google Stackdriver Logging, and IBM Cloud Activity Tracker

---

on a Linux system, most changes to the /etc directory tree should be viewed with some suspicion.

---

The Kuber‐ netes documentation explains how to turn on audit logging and how to direct those logs to a collection point.

---

Cloud Audit Data Federation (CADF) standard is intended to allow switch‐ ing between cloud providers without changing the log aggregation and parsing systems.