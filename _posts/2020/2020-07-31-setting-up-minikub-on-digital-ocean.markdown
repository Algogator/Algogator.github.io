---
layout: "post"
title: "Setting up minikube on Digital Ocean"
date: "2020-07-31 10:45"
---

# Installation

Make sure you satisfy all the requirements for minikube, the plan I had to use with Digital Ocean was at 2 vCPUs / 2 GB Memory / 25 GB Disk / Ubuntu 20.04 (LTS) x64

You will need to create a new user account on the system to run minikube

Also you need docker installed as non-root.

`sudo groupadd docker`

`sudo usermod -aG docker ${USER}`

This will let you run Docker without sudo


minikube can be deployed as a VM, a container, or bare-metal. And the preferred drivers are Docker or KVM2

minikube has a better doc on this than Kubernetes

- https://minikube.sigs.k8s.io/docs/drivers/
- https://minikube.sigs.k8s.io/docs/start/
