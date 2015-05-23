Navigating the ever-changing Docker ecosystem can be difficult, so we at CenturyLink would like to make it easier for you. A few weeks ago, I wrote about the top 10 startups using Docker. This week we are talking about the top 10 open-source projects using Docker. I will group them to highlight what each project focuses on.
Table of Contents


## Docker PaaS

Although Docker was a technology originally built out of a PaaS (DotCloud), there have been multiple attempts to create micro-PaaS'es out of Docker.

1. Flynn – https://github.com/flynn 961 stars, 24 forks in Mar 2014 "Flynn is like Sinatra where Cloud Foundry is like Rails"

Flynn is one of the most anticipated Docker PaaS'es right now. With nearly 1,000 stars and dozens of forks, this open-source Docker project has not even been released yet. With a git push deployment to Docker, it is easy to see why there is so much anticipation. Flynn simplifies deploying and maintaining applications. Instead of using complex configuration management systems, Flynn allows self-serve management of containerized deployments, making life easier for ops and developers. Flynn is also different than the other projects on this list because they are a sponsored open-source project. With 14+ sponsors having donated over $80,000, this project is definitely one to watch.

Flynn

2. Deis – https://github.com/opdemand/deis 1,341 stars, 120 forks in Mar 2014 "Your PaaS. Your Rules."

With over 1,300 stars and over 120 forks, Deis is more established than Flynn and also has a git push deploy style. Deis leverages Chef, Docker, Django, Celery, Heroku Buildpacks, and Slugbuilder to do its magic. Deis comes with out-of-the-box support for Ruby, Python, Node.js, Java, Clojure, Scala, Play, PHP, Perl, Dart and Go. Also, Deis can deploy anything using Heroku Buildpacks, Docker images or Chef recipes. Deis can be deployed on any system including every public cloud, private cloud or bare metal. Deis currently supports automated provisioning on EC2, Rackspace and Digital Ocean. In an upcoming blog post, we will compare Deis and Flynn in more detail.

3. Dokku – https://github.com/progrium/dokku 4,806 stars, 384 forks in Mar 2014 "Docker powered mini-Heroku in around 100 lines of Bash"

**If you just want the smallest viable git push to Docker container functionality in the world, take a look at Dokku. From the maker of localtunnel (a super useful utility to reverse-proxy your localhost ports to a public url), this little power-house of an open-source project has the most eye-balls. It is not as feature rich as Deis or Flynn, but it is incredibly easy to install and use on Ubuntu 13 or 12.04 x64.
$ wget -qO- https://raw.github.com/progrium/dokku/v0.2.2/bootstrap.sh | sudo DOKKU_TAG=v0.2.2 bash

Note: Users on 12.04 will need to run apt-get install -y python-software-properties before bootstrapping stable.
Docker Orchestration

4. CoreOS – https://github.com/coreos 2,564 stars, 237 forks in Mar 2014 "CoreOS enables warehouse-scale computing on top of a minimal, modern operating system."

**CoreOS is developing best practices for deploying containerized applications to production. It is not a single open-source repository, but rather a collection of many open-source tools that can be used together including etcd, docker, and systemd. We have written about generating CoreOS files from Fig files before because getting started with CoreOS can be a daunting experience. The etcd library is used as a universal key/value store to stitch services together and share service credentials across an entire application. Unlike many of the other projects in this list, CoreOS is both an open-source project and a venture backed startup (which is why CoreOS is also listed in our Top 10 Startups Built on Docker post).

5. Fig – https://github.com/orchardup/fig 1,526 stars, 51 forks in Mar 2014 "Fast, isolated development environments using Docker"

**I have written a few times about Fig because it is one of my favorite little utilities for Docker (Auto-Loadbalancing Docker with Fig, HAProxy and Serf and Building Complex Apps for Docker on CoreOS and Fig). Fig lets you write a simple fig.yml file that lists all the Docker containers your app needs and how they should link together. Once you write the fig.yml you just fig up -d and your app will be up and running. This blog is managed by fig right now.

6. Serf – https://github.com/hashicorp/serf 1,652 stars, 91 forks in Mar 2014 "A decentralized solution for service discovery and orchestration that is lightweight, highly available, and fault tolerant"

**Although Serf is not Docker specific, it is like jelly to Docker's peanut butter. Serf is one of my favorite new open-source projects and came from the guys who make Vagrant. I wrote about it a few weeks ago in Decentralizing Docker: How to Use Serf with Docker so you can get a great insight into how to use it with Docker there, but essentially it is a hammer you can use where CoreOS and etcd is a nail-gun. Serf is also really easy to use outside of Docker and can be used in a lot of different ways where etcd and CoreOS are pretty specific tools that aren't nearly as flexible (though definitely very powerful).
CI/CD

7. Drone – https://github.com/drone/drone 2,516 stars, 133 forks in Mar 2014 "A Continuous Integration platform built on Docker"

Drone (another project that is both an open source project and a startup) gives you a simple go binary, distributed in a debian file, that gives you a full CI/CD pipeline hooked natively into Docker. Cool, right? Your code never needs to leave your laptop or your company's network to be tested, which is a huge deal for big company developers who have policies that prevent them from using public hosted services like GitHub and Travis. The other cool part of Drone is that you can deploy the fully tested containers into production and be assured that the exact same environment is used in both locations. Finally, Drone lets you build custom Docker containers with whatever custom binaries and configuration you need, which is way more flexible than most CI platforms today.
UI

8. Shipyard – https://github.com/shipyard/shipyard 1,443 stars, 96 forks in Mar 2014 "Open Source Docker Management"

Shipyard gives you the ability to manage Docker resources including containers, images, hosts, and more all from a single management interface including: Multi-Host Support, Container Metrics, and a RESTful API. I love this part, to deploy Shipyard, you just run:
$ docker run -i -t -v /var/run/docker.sock:/docker.sock shipyard/deploy setup

Then you should be able to login to http://localhost:8000 and get the pretty UI (more QuickStart docs available). Slick! Being able to visually see all your containers is killer and Shipyard is a great way to do that.
Orchestration

9. Kubernetes – https://github.com/GoogleCloudPlatform/kubernetes 3,598 stars, 501 forks in Sept 2014 "Google's Docker Orchestrator"

Kubernetes is an open source implementation of container cluster management. In other words, it is a system for managing containerized applications across multiple hosts, providing basic mechanisms for deployment, maintenance, and scaling of applications. Its APIs are intended to serve as the foundation for an open ecosystem of tools, automation systems, and higher-level API layers.

10. Panamax – https://github.com/centurylinklabs/panamax-ui 510 stars, 43 forks in Sept 2014 "Docker Management for Humans"

Panamax is a containerized app creator with an open-source app marketplace hosted in GitHub. Panamax provides a friendly interface for users of Docker, Fleet & CoreOS. With Panamax, you can easily create, share and deploy any containerized app no matter how complex it might be.
Conclusion

If you measure the health of an open-source project by the open-source projects created around it, I think it is fair to say that Docker is the picture of health. This article was meant to be more of an overview than an in-depth comparison. In future weeks, we plan to talk more about the differences between some of these technologies like Flynn vs Deis.
Did you like what you read?

Stay on the bleeding edge with the weekly CenturyLink Labs newsletter featuring Docker tutorials, news, jobs, and much more.
# DB Management
-
## Flocker - ClusterHQ - DB Management
> Run your databases in Docker and make them as portable as the rest of your app

https://clusterhq.com/
# Container management

## Cloudify
> With Cloudify you can deploy the same application in your own data center or on the cloud of your choice using your favorite automation and configuration management tools. This enables you to build a robust continuous delivery pipeline by standardizing deployment, orchestration and build processes to create smoother transitions between development and production environments
http://getcloudify.org/

## Rancher
> Rancher is a container management platform for running Docker at scale. We built Rancher because we loved the Docker experience on a single host, and wanted to build a platform that would scale that experience across teams, projects and infrastructure running anywhere, while retaining Docker’s native APIs and tools.

http://rancher.com/rancher-io/

![](http://rancher.com/wp-content/uploads/2015/02/host_home.png)

## RancherOS
> Built on Docker

> When we started the RancherOS project, we set out to build a minimalist Linux distribution that was perfect for running Docker containers. We wanted to run Docker directly on top of the Linux Kernel, and have all user-space Linux services be distributed as Docker containers. By doing this, there would be no need to use a separate software package distribution mechanism for RancherOS itself.

http://rancher.com/rancher-os/#gettingstarted
## Panamax
Management for Humans
An open-source project that makes deploying complex containerized apps as easy as Drag-and-Drop

video: https://www.youtube.com/watch?v=xGjBZ0lZG5E

http://panamax.io/
![](http://i.imgur.com/nzGRvZQ.png)

## Kubernetes

> No discussion of third-party Docker projects would be complete without mention of Kubernetes, an open source Docker management tool developed by Google for deploying containers across clusters of computers. Aside from helping to manage workloads for Docker nodes by keeping container deployments balanced across a cluster, Kubernetes also provides ways for containers to communicate with each other, minus the need to open network ports or perform other hacks. These features and the fact that Kubernetes is written in Go -- the same language as Docker -- strongly suggest it will be rolled into Docker at some point in the future.

Project: Kubernetes
GitHub: https://github.com/GoogleCloudPlatform/kubernetes
![](http://images.techhive.com/images/article/2014/10/01-44ss-docker-100527298-orig.jpg)

## DockerSH
> If you want to give users shell access but are leery of the security complications, Dockersh offers a Docker-ized way to provide shell sessions with above-average security.

> Dockersh lets multiple users connect to a given box, with each user running a shell spawned from a separate Docker container of your choosing. Users can see their home directory and make persistent changes to it, but they can view only their own processes and can use only their private networking stack. The creators are wary of potential security holes in Dockersh and don’t recommend it for unrestricted public access, at least not until Docker adds improvements in this vein. But the concept alone makes this one to watch.

Project: Dockersh
GitHub: https://github.com/Yelp/dockersh

![](http://images.techhive.com/images/article/2014/10/02-44ss-docker-100527304-orig.jpg)


## DockerUI

> While most devs and admins create and run Docker containers via the command line, Docker’s Remote API enables them to run the same commands through a RESTful API. Enter DockerUI. This Web front end allows you to handle many tasks normally managed from the command line of a Web browser. All of the containers on a given host can be manipulated via a single connection, and the project has almost no dependencies. It is, however, under heavy development, but it’s MIT-licensed, so it can be reused quite freely. In addition, it contains no built-in authentication or security, so be sure to put any publicly exposed DockerUI connections behind something with a password on it.

Project: DockerUI
GitHub: https://github.com/crosbymichael/dockerui


![](http://images.techhive.com/images/article/2014/10/03-44ss-docker-100527305-orig.jpg)

## Shipyard

> Shipyard uses the Citadel cluster management toolkit to facilitate management of Docker container clusters that span multiple hosts. Through a Web UI, you can get at-a-glance information about how much CPU or memory your containers are using and which containers are running, plus examine a log of events across all clusters. A full API and CLI are included, and specially constructed Docker images (aka extension images) can be used to expand on Shipyard’s functionality. That last conceit is still a work in progress, but a load-balancing/routing image is available by way of the Interlock project.

Project: Shipyard
GitHub: https://github.com/shipyard/shipyard

![](http://images.techhive.com/images/article/2014/10/04-44ss-docker-100527307-orig.jpg)


## Kitematic

> Kitematic is one of a number of projects that aims to make Docker useful as a desktop-environment developer’s tool for OS X-based programmers. It makes the process of downloading Docker images, spinning them up, and managing them into a task no more difficult than, say, using VMs in an application like VMware Workstation. Other projects in the same vein include DVM, Docker OS X, and OS X Installer, although Kitematic is easily the most polished of the bunch. The only major downside is that the uninstallation process is somewhat convoluted.

Project: Kitematic
GitHub: https://github.com/kitematic/kitematic

![](http://images.techhive.com/images/article/2014/10/05-44ss-docker-100527306-orig.jpg)


## Logspout

Docker does not yet provide a way to manage logs generated by programs running inside Docker containers. Logspout, a Docker container that weighs in at 14MB and uses BusyBox as its core, can route container-app logs to a single central location, such as a single JSON object or a streamed endpoint available through an HTTP API. Logspout is currently limited in terms of what it can scoop up, as it can only stdout and stderr output from a container, but plans are in place to allow more comprehensive logging as soon as Docker provides hooks for it. Keep an eye on this one for the future.

Project: Logspout
GitHub: https://github.com/progrium/logspout

![](http://images.techhive.com/images/article/2014/10/06-44ss-docker-100527312-orig.jpg)


# Autodock

Docker automation tools are something of a commodity. After all, isn’t easier automation the whole point of Docker? But Autodock stands out with a few differences. It’s designed to work in environments that use Salt and SaltStack as the main automation technology, and it’s specifically designed to make spinning up new containers as fast as possible by determining which servers in a given Docker cluster have the least load. One possible gripe is the number of ingredients needed to make it work (SaltStack, Golang, Etcd, Python).

Project: Autodock
GitHub: https://github.com/cholcombe973/autodock

![](http://images.techhive.com/images/article/2014/10/07-44ss-docker-100527308-orig.jpg)


## DIND -- Docker-in-Docker

Docker-in-Docker is exactly what it sounds like: A way for you to run Docker within Docker containers, made possible in Docker 0.6 by the addition of the privileged mode for containers. "Inception," anyone?

Gimmicks and jokes aside, this is useful if you want to provide Docker itself as a service to Docker containers -- for instance, if you want to experiment with an automation tool or methodology. Note that the “inner” instance of Docker is the most recent Docker binary, which is retrieved from docker.io when it’s built. Also bear in mind that instances that run in this manner do so in privileged mode; as such, you need to take more precautions when exposing them to the non-Dockerized outside world.

Project: Docker-in-Docker
GitHub: https://github.com/jpetazzo/dind

![](http://images.techhive.com/images/article/2014/10/08-44ss-docker-100527309-orig.jpg)


## Heroku-Docker

Heroku was (and to a degree still is) a standout PaaS with broad language support, but Docker makes it possible to do PaaS-like work almost anywhere. To that end, those looking for ways to migrate existing Heroku projects to Docker without rebuilding them from scratch need look no further. This simple little project takes an existing Heroku app and converts it into a Docker image from the command line, with no more than a few commands needed to perform the whole operation.

Project: Heroku-Docker
GitHub: https://github.com/ddollar/heroku-docker

![](http://images.techhive.com/images/article/2014/10/09-44ss-docker-100527310-orig.jpg)


## Docker Node Tester

What do you get when you use one of the hottest new IT technologies as a testing mechanism for another hot, new IT technology? Docker Node Tester, apparently. DNT provides a test bed in which a Node.js project runs against multiple versions of Node.js in Docker containers, then tabulates the output. You can also automatically test against the most bleeding-edge version of Node, whatever it is. Note that the various versions of Node are all built from source, which means you’ll end up with a local copy of the entire source tree for Node; make sure you have space enough for it.

Project: Docker Node Tester
GitHub: https://github.com/rvagg/dnt

![](http://images.techhive.com/images/article/2014/10/10-44ss-docker-100527311-orig.jpg)



