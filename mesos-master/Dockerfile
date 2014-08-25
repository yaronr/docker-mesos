FROM mesos
MAINTAINER Yaron Rosenbaum <yaron.rosenbaum@gmail.com>

#EXPOSE 5050

######## Storm-Mesos
#RUN wget -q -N http://downloads.mesosphere.io/storm/storm-mesos-0.9.tgz && \
# tar xzf ./storm-mesos-0.9.tgz && \
# rm ./storm-mesos-0.9.tgz

RUN wget -q -N http://dl.bintray.com/whisklabs/generic/storm-mesos-0.9.2-incubating.tgz && \
 tar xzf ./storm-mesos-0.9.2-incubating.tgz && \
 mv /storm-mesos-0.9.2-incubating /storm-mesos && \
 rm ./storm-mesos-0.9.2-incubating.tgz

ADD storm.yaml /storm-mesos/conf/storm.yaml
ADD cluster.xml /storm-mesos/logback/cluster.xml

##### For Marathon and Chronos: 
RUN echo "zk://zookeeper:2181/mesos" > /etc/mesos/zk

# Configure process supervisor
ADD supervisord.conf /etc/supervisor/supervisord.conf

CMD ["supervisord"]
