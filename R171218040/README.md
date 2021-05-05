# Application Containerisation Lab

### Container platform

It can be defined as a technology to isolate processes from each other in such a manner that processes run like they are running in a normal operating system
which is enforced by the container runtime. They ideally share the resources of a single host machine without having the ability to see each other’s or the host’s 
processes and resources because of namespaces and cgroups. A platform also has a control over the runtime and the lifecycle of the images.
It can also be defined as a tool or technology, which provides the functionality to spin up containers with the extraction at the software level and not at the hardware 
level like virtual Machines.

**Examples:** LXC, Rkt, Docker.

**In this repository, I have attached some experiments and their procedure**

### List of Experiments

1. Installing Vagrant & Creating basic vagrant box using VirtualBox virtualization
2. Docker Volumes, Env, Monitoring (Docker stats)
3. To create Docker network and attach it with Containers for connectivity
4. To create Docker image using Dockerfile and pushing to Docker Hub
5. To create Docker image using Docker compose
6. Docker Link
7. Docker Swarm 
