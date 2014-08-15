FROM mesos
MAINTAINER yaronr

RUN echo "zk://zookeeper:2181/mesos" > /etc/mesos/zk

EXPOSE 8080

CMD ["marathon"]
