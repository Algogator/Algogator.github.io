---
layout: post
title: "Event-driven architecture"
tags: [Backend]
---

## Event driven architecture

This is great for decoupled components which works well for me.

### WebSockets

* Based on TCP and pretty common
* Django has support for it (Channels 2)
* Won't have issues with firewalls
* It is NOT HTTP
* No scalability - ports are hardcoded and limited

### WebHooks

* Callbacks - code passed as arg to another code.
* Got a package for it (https://djangopackages.org/grids/g/webhooks/) but not a lot of documentation online
* Work well for server to server setup
* Based on HTTP so easy to setup
* Could be done by REST
* Resource intensive (think about using a messaging queue)

### RESTHooks

* Client waits for a change and reacts to it
* Based on Http
* Subscription based
* Not really RESTful
* Still consistent pooling (just moved to the other side)
* Zapier has something for it, not really widely adopted (https://github.com/zapier/django-rest-hooks)

### Pub-Sub

*

### SSE
