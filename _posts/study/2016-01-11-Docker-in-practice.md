---
layout: page-fullwidth
title: "Docker in Practice"
subheadline: "Docker in Study"
teaser: "This is the first glance on Docker. Here records the practical bit of docker..."
header: no
image:
    thumb:  homepage_typography_thumb.jpg
    homepage: homepage_typography.jpg
categories:
    - study
    - docker
---

##Docker in practice
###Running public images
	docker run hello-world
__A container is a stripped-to-basics version of a Linux operating system. An image is software you load into a container. When you ran the command, the Docker software:__

+ checked to see if you had the `hello-world` software image
+ downloaded the image from the [Docker Hub](https://hub.docker.com/)
+ loaded the image into the container and “ran” it

###Build your own image
####Step 1 : Write a Dockrfile
	A Dockerfile describes the software that is “baked” into an image.
	It isn’t just ingredients tho, it can tell the software what environment to use or what commands to run.

The `FROM` keyword tells Docker which image your image is based on. You are basing your new work on the existing `whalesay` image. `FROM docker/whalesay:latest`

####Step 2 : Build an image from your Dockerfile
	docker build -t docker-whale .
The `docker build -t docker-whale .` command takes the `Dockerfile` in the current directory, and builds an image called `docker-whale` on your local machine


###Cheat sheet
* Create a new docker vm:
`docker-machine create --driver virtualbox default`
* List docker machines:
`docker-machine ls`
* Get the environment commands for VM:
`docker-machine env default`
* Connect shell to the machine:
`eval "$(docker-machine env default)"`
* Start an NGINX container on the DOCKER_HOST:
`docker run -d -P --name web nginx`
* Display your running container:
`docker ps`
* View just the container’s ports:
`docker ps web`
* Get the address of the default VM:
`docker-machine ip default`
* To stop running container:
`docker stop web`
* To remove container:
`docker rm web`
