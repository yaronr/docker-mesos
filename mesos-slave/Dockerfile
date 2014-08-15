FROM mesos
MAINTAINER yaronr

CMD ["--master=zk://zookeeper:2181/mesos", "--log_dir=/var/log/mesos"]

ENTRYPOINT ["mesos-slave"]
