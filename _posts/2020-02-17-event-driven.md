---
layout: post
title: "Event-driven architecture"
category: Backend
---

## Event driven architecture

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

* Scalable
* Decoupling is also a huge disadvantage
* Redis and Celery is a way to go about it

### SSE

* Server sends clients data
* Not bidirectional
* Won't have to wait for data to be returned
* Security is going to be annoying
* Loss of data
* Seems to be a couple of packages but seems like a bad idea (https://github.com/niwinz/django-sse) and (https://uwsgi-docs.readthedocs.io/en/latest/articles/OffloadingWebsocketsAndSSE.html)

"...you cannot mix blocking apps with non-blocking engines, even a single, ultra-tiny blocking part can potentially destroy your whole stack. As I have already said dozens of time, if your app is 99.9999999% non-blocking, it is still blocking." -Roberto De Ioris

Refer [https://nordicapis.com/5-protocols-for-event-driven-api-architectures/](https://nordicapis.com/5-protocols-for-event-driven-api-architectures/")
