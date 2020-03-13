---
layout: "post"
title: "Setting up Gitlab runner "
date: "2020-03-10 15:43"
category: Backend
---
First you need to install gitlab-runner on your system:

`curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh | sudo bash
sudo apt-get install gitlab-runner`

Next you register it with a token from the website (Project Settings > CI/CD > Expand Runners):

`sudo gitlab-runner register`

Pick your executor as docker and default image as docker/compose

Though it might be better to register a runner from https://docs.gitlab.com/ee/ci/docker/using_docker_build.html
