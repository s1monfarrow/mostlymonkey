# Wrangling Lots of Machines

Just a reading list useful tech for doing stuff on lots of machines.

# [Kubernetes](http://kubernetes.io/) and [Swarm](https://docs.docker.com/swarm/) 
Managing larger numbers of containers. Swarm uses the native interface of docker, Kubernetes adds new terminology. I’m not sure if swarm deals with the software networking.

# [Rancher](http://rancher.com/) and [Openshift](https://www.openshift.com/showcase/)
These seem similar. But I think that rancher is going to top out in the hundreds of machines as it relies on the GUI too much. Open Shift seems to be the most mature platform. Both can deal with Kubernetes underneath.

# Going Large
As well as treating the hardware as separate machines it is also possible to manage a Data Centre almost as a single compute engine. [Apache Mesos](https://mesosphere.com/why-mesos/) abstracts away the underlying compute infrastructure.

Abstracting compute combined with clever scheduling potential allows for cost savings by [making full use of all resources](https://opensource.com/business/14/9/open-source-datacenter-computing-apache-mesos). Especially if large jobs are being run at a lower priority. Mesos is comparable to Google’s [Borg](http://research.google.com/pubs/pub43438.html) and is currently used in production by Twitter.

# Networking
As running a large number of containers tends to imply an internal architecture that is made up of smaller services. It is worth mentioning the [Networking infrastructure of the data centre itself](http://highscalability.com/blog/2015/8/10/how-google-invented-an-amazing-datacenter-network-only-they.html).

An infrastructure designed to service requests from the outside world (through n tiers) is unlikely to be able to deal with the increased number of internal requests made by a Micro-services Architecture.

Software Defined Networking may also become of significant interest as it abstracts the network in the same way that Mesos can with the compute. [OpenFlow](https://en.wikipedia.org/wiki/OpenFlow) is a standard that allows for the abstraction of networking hardware, it is now widely supported.
