FROM ubuntu:14.04
MAINTAINER Yaron Rosenbaum <yaron.rosenbaum@gmail.com>

RUN echo "deb http://repos.mesosphere.io/ubuntu/ trusty main" > /etc/apt/sources.list.d/mesosphere.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF
RUN apt-get -y update
RUN apt-get -y install wget python mesos marathon chronos
