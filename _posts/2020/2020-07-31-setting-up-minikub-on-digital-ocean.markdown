---
layout: "post"
title: "Setting up minikube on Digital Ocean"
date: "2020-07-31 10:45"
---

# Installation

Make sure you satisfy all the requirements for minikube, the plan I had to use with Digital Ocean was at 2 vCPUs / 2 GB Memory / 25 GB Disk / Ubuntu 20.04 (LTS) x64

Also you need docker installed as non-root.

`sudo groupadd docker`

`sudo usermod -aG docker ${USER}`

This will let you run Docker with sudo
