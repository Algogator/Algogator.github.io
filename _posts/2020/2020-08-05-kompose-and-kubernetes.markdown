---
layout: "post"
title: "Kompose and Kubernetes"
date: "2020-08-05 13:54"
---

I have a lot docker compose files for most of my projects which works very well with Gitlabs' CI/CD.

When I tried to do a `kompose up` I kept getting

  > FATA Error while deploying application: Get https://127.0.0.1:6443/api: dial tcp 127.0.0.1:6443: connect: connection refused

to fix this started a proxy to the API with

`kubectl proxy --port=6443 &`

which threw this error next but it's an improvement

  > FATA Error while deploying application: Get https://127.0.0.1:6443/api: http: server gave HTTP response to HTTPS client

I had to specify the server in Kompose

`kompose up --server http://127.0.0.1:6443`
