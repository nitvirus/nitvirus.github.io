---
layout: post
title: Starting with Docker
Date: 2018-09-02
author: "Nitish"
---
Hi there,

I just started with learning docker basics and docker essentials.

Docker is a open source devops tools which enables you to use images inside container.

Now from devops I mean development and operations, in which one can deliver and develop applications continuously.
By images in docker we mean, libraries or template of libraries which are required for application development.
By container in docker we mean a particular instance where we a using an image.Containers are lightweight environments on which applciations are run.

few of the commands that I have used till now:
1.  docker container run --publish 80:80 nginx
2. docker container stop 797
3. docker container rm 797
4. docker container ls
5. docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -d mysql/mysql-server:latest
-e is required here as it is used to give the environment variables.


Whats next: to learn how to write dockers files, use Containers in local development.
