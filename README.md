docker-mesos
=====

A distributed computing cluster-in-a-box: Mesos, zookeeper, chronos, marathon, storm + add your own. 

Use other physical computers to add computational power to the cluster.

I decided to build this setup in order to be able to work with Mesos and its frameworks on a laptop. 

The first setup that I found, that actually worked, was [vagrant-mesos](https://github.com/everpeace/vagrant-mesos). However, I quickly realized that my laptop can't carry the weight of so many VMs.

Next, I searched for a Docker.io based setup (but couldn't find one): Docker offers a more elegant - and resource efficient approach, plus - it potentially offers a scenario where developers use the exact same setup in development and in production (Dev-Ops). That carries a lot of weight.

This work is inspired by [storm-docker](https://github.com/wurstmeister/storm-docker), the wonderful work of wurstmeiser - a clean and elegant Docker based Apache Storm setup.

The root of the project is [this](http://stackoverflow.com/questions/25217208/setting-up-a-docker-fig-mesos-environment/25218202?noredirect=1#comment39342354_25218202) stackoverflow question, and the detailed response by Mark O`Connor (Thank you Mark!).


I decided to take this solution forward and share it with the community - hopefully getting other people to contribute. It's no rocket scinence, and a few tweaks here and there can make a big difference.


###Use:
* Clone repository
* ./build.sh
* fig up

To open up the Mesos UI, open http://your docker host's IP:15050

To open up the Storm UI, open http://your docker host's IP:49080

Chronos UI: open http://your docker host's IP:14400

Marathon UI: open http://your docker host's IP:18080

If you're using boot2docker, to find out your docker host's IP, run <br/>$> boot2docker ip


###Known issues & Workarounds:
* Storm fails to run topologies. UI works, you can submit, but executors seem to die silently. Working on it, appreciate help if you have the time.
* When using boot2docker versions older than 1.2 (on mac, probably other platforms as well), Chronos and / or Marathon fail,  trying to increase the number of open file descriptors.
This is solved in [boot2docker 1.2 pull 166](https://github.com/boot2docker/boot2docker/pull/466) so please do:

```
 boot2docker down
 boot2docker update
 boot2docker up
```

##TODO:
* Centralized monitoring? [Ganglia?](http://ganglia.sourceforge.net/)
* [Centralized logging?](http://jasonwilder.com/blog/2012/01/03/centralized-logging/)  [Flume?](https://cwiki.apache.org/confluence/display/FLUME/Home%3bjsessionid=DE02EE9AD41DCFE2E244B6C03FF36B06)
* Process supervision for zookeeper?
* drive mapping for logging
* store images at hub.boot2docker.com + auto build


##PS

This is a work in progress, and I would appreciate individual contributions.


If you think you can fix any of the known issues, please do.

If you find an issue, please report!

If something is not clear, please ask.





