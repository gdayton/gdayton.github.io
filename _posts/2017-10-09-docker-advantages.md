---
title: "7 Reasons to Start Using Docker"
layout: post
date: 2017-10-09 20:02:31 +0700
author: glenndayton
description: Docker is becoming hotter and hotter. We'll examine why.
comments: true
img: /assets/img/docker.png
---
### 7 Reasons to Start Using Docker

{% include post/share-buttons.html %}

Glenn Dayton &middot; October 9, 2017

Docker is hot. It's becoming as standard as git in any programming organization. It's one step closer to almost entirely removing version and configuration headaches and further automates development. But there are so many more reasons Docker is as popular as Kim Kardashian.

**Helps with onboarding new people to the development team** With Docker Compose an entire project can be stored on Github, cloned, and then `docker-compose` built. That's it. There's no need for new onboards to install, configure, and get services running on their computer, it's all handled through Docker.

**Minimizes configuration difficulties** Docker runs off of the configure once, run everywhere principle. If the decision to switch from MongoDB to Cassandra is made, a one line edit in the `docker-compose.yml` file handles the transition. With a development team of 15 people, without Docker we'd have to download, install, configure, and transition 15 instances of Cassandra, a task prone to mistakes.

**Eliminates version mismatch** A 15 person development team could easily be running several different versions of Cassandra without the use of Docker. This opens the team to possible version specific incompatibility issues. This issue becomes highly problematic when members push code that worked on their local version of Cassandra to members of the team that have a different incompatible local versions of Cassandra. Docker addresses this issue by standardizing the environment allowing all team members to work in a parity environment.

**Makes managing services much easier** Before Docker to start/stop MySQL I'd have to type, `sudo /usr/local/mysql/support-files/mysql.server start/stop`, but now with Docker it's just `docker-compose restart`, and it restarts ALL services making life that much easier.

**Continuous Integration (CI) advantages** Once a Docker image is built, it can be taken from development to production with little to no staging requirements saving time.

**Ease of integration into top Docker Cloud hosting providers** There are many many hosting providers for container hosting services that easily take your application from development to production.
- Google Cloud Platform
- Amazon Web Services
- Microsoft Azure
- Rackspace
- Heroku
- Dokkur
- Sloppy.io

**Very easy to scale** Docker Swarm drastically reduces the amount of steps to scale a platform. It's as simple as `docker service scale project=5` to add 5 more tasks. This coupled with the compute power of a cloud hosting provider makes for a extremely easy to scale platform.

If you're not convinced Docker is something big, take a look at my tutorial on [How to setup an Angular, Node, and MongoDB environment with Docker](http://coderbro.com/docker/node/mongodb/2017/10/09/node-mongodb-docker-compose.html).