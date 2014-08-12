FROM mesos
MAINTAINER Yaron Rosenbaum <yaron.rosenbaum@gmail.com>

RUN echo "zk://zookeeper:2181/mesos" > /etc/mesos/zk

EXPOSE 4400

CMD ["chronos"]
