FROM mesos

MAINTAINER yaronr

RUN wget -q -N http://downloads.mesosphere.io/storm/storm-mesos-0.9.tgz && \
 tar xzf ./storm-mesos-0.9.tgz && \
 rm ./storm-mesos-0.9.tgz

# Configure process supervisor
ADD supervisord.conf /etc/supervisor/supervisord.conf

#CMD ["--zk=zk://zookeeper:2181/mesos", "--work_dir=/var/lib/mesos", "--quorum=1"]
#ENTRYPOINT ["/storm-mesos-0.9/bin/storm-mesos"]

ADD storm.yaml /storm-mesos-0.9/conf/storm.yaml
ADD cluster.xml /storm-mesos-0.9/logback/cluster.xml

CMD ["supervisord"]


#apt-get install git maven
#cd /usr/share
#git clone https://github.com/mesos/storm.git

