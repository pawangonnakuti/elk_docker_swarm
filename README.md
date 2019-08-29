# Elastic cluster using Docker swarm


## Below is my brain dump, so please they are not instructions for someone to follow and i may/maynot be having time to respond. and if you understand what i've written and like to help document, be my guest.

## The intent
The intent is to run a multi-node multi-host elastic stack on docker swarm. which may be adoptable to kubernetes.

__Note: Docker swarm is not supported by ELK stack by elastic. However they do provide feedback/support on the forum.__

Docker setup: i've setup docker on 3 hosts with 2 hosts are manager and one as worker.

##Limitations:
  docker volume cant be shared with multiple elasticsearch nodes, however their is an option but elastic suggested that this will be removed in the next version. Due to this, i've defined 3 nodes (1 master, 1 ingest and 1 data) to be run on each host running docker.

initial master node, the compose file takes into account 1 single master node where all the nodes lookupto to help guide and find other nodes are. so if the primary node changes, you may run into issues if new nodes are run.


