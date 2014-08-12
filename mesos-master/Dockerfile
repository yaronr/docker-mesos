FROM mesos
MAINTAINER Yaron Rosenbaum <yaron.rosenbaum@gmail.com>

EXPOSE 5050

CMD ["--zk=zk://zookeeper:2181/mesos", "--work_dir=/var/lib/mesos", "--quorum=1"]

ENTRYPOINT ["mesos-master"]
