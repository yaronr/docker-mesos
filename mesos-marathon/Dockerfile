FROM mesos
MAINTAINER Mark O'Connor <mark@myspotontheweb.com>

RUN echo "zk://zookeeper:2181/mesos" > /etc/mesos/zk

EXPOSE 8080

CMD ["marathon"]
