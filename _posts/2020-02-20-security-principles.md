---
layout: "post"
title: "Security Principles from Mozilla"
date: "2020-02-20 11:06"
category: Backend
---

Mozilla has this really neat page on security: https://infosec.mozilla.org/fundamentals/security_principles.html & https://infosec.mozilla.org/guidelines/web_security

## Do not expose unnecessary services

### Do

* "List all services presented to the network (Internet and Intranets). Justify the presence of each port or service." FYI: In precise, Intranet is an extension of a LAN in which Internet protocol services are added.

### Do not

* OpenSSH Server (sshd) is running but no users ever login.
* "A web-application has a web accessible administration interface, but it is not used." For example the Django web admin.
* A database server (SQL) allows connections from any machine in the same VLAN, even though only a single machine needs to access it.

## Do not allow lateral movement

Goal: Make it difficult or impossible for an attacker to move from one host in the network to another host.

### Do

* Prevent inbound network access to services on a host from clients that do not need access to the service through either host-based firewall rules, network firewall rules or both (which is preferred).

## Patch Systems

### Do

* Establish regular recurring maintenance windows in which to patch software.
* Ensure individual systems can be turned off and back on without affecting service availability.
* Enable automatic patching where possible.
* Check web application libraries and dependencies for vulnerabilities.

## Guarantee data integrity and confidentiality

### Do

* Use full-disk encryption where available on systems without physical security (laptops and mobile phones).
* Encrypt credentials storage databases (Ansible Vault, Credstash, etc.)
* Encrypt data in transit with TLS (during transmission).
* Also encrypt data in transit inside the internal network.

### Do not

* Terminate TLS (e.g. with a reverse proxy or load balancer) outside a system and then transmit the data in clear-text across the rest of the network.

## Require two-factor authentication

Goal: Minimize credential theft and identity mismanagement by minimizing the handling of user credentials such as password, MFA to a set of dedicated systems.

### Do

* Use an SSO (Single Sign-On) solution that authenticates users credentials on your service’s behalf.
* Use authorization (e.g. group membership) data from the SSO system (possibly, in addition to your own authorization data)

### Do not

* Accept, process, transmit or store user credentials (passwords, OTPs, keys, etc.) Let the authentication server directly handle that data.

## Require strong authentication

### Do

* Use credential-based authentication and user session management where the session information is passed by the user
* Use API keys for service authentication.
* Prefer using asymmetric API keys with request signing (e.g. x509 client certificates, AWS Signature) over symmetric API keys (e.g. HTTP header)
* "Ensure that API keys can be automatically rotated in the case of a data leak". FYI: Key rotation is when you retire an encryption key and replace that old key by generating a new cryptographic key.

### Do not

* Trust traffic from a certain network address.
* Rely on VLANs to indicate requests are safe.
* Trust the office network for access to devices.
* Use machine API keys for user authentication.
* Store API keys on devices that are not physically secure (e.g. laptops or mobile phones)
