FROM mesos

MAINTAINER Yaron Rosenbaum <yaron.rosenbaum@gmail.com>

RUN wget -q -N http://downloads.mesosphere.io/storm/storm-mesos-0.9.tgz && \
 tar xzf ./storm-mesos-0.9.tgz && rm ./storm-mesos-0.9.tgz

#CMD ["--zk=zk://zookeeper:2181/mesos", "--work_dir=/var/lib/mesos", "--quorum=1"]
#ENTRYPOINT ["/storm-mesos-0.9/bin/storm-mesos"]

ADD storm.yaml /storm-mesos-0.9/conf/storm.yaml

CMD ["supervisord"]

