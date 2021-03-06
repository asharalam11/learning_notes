# GCP Core Infrastructure

### *Module: Containers in the Cloud* 

* __Compute__ engine :cloud::computer: is Google's __IaaS__ (Infrastructure as a service offering). We get to run VMs in cloud and also get persistent storage for them.
* __App__ engine is Google's __PaaS__ (Platform as a service offering). 
* __Kubernetes__ engine :gear: is the best of both worlds (it saves you both infrastructure and platform chores).

#### Some concepts

* __IaaS__: Lets you share compute resources with others while virtualizing the hardware. Each VM has an OS and you can build applications on them. Virtual machines are highly configurable (but consume more resources), so there is a trade-off. IaaS is the most flexible model giving you complete access except the physical access or overhead of maintaining and managing devices. It is more like a virtual data center. :bank:
* __PaaS__: Instead of blank VMs, we get access to a range of services, which are needed by applications. Using these services, we write code in self contained workloads and dependencies on libraries. But, we have to give up control of underlying server architecture when we scale rapidly. Succinctly, PaaS provides a framework for building customized applications. All the servers, storage and networking are handled by service providers. :school:
* __Containers__: This is the best of both worlds. Independent scalibility of workloads (like in a PaaS environment) and an abstraction of OS and hardware (like in a IaaS environment). Container is like an invisible box handling dependencies and such. In OS, a process is an instance of a running program and a container starts as fast as a process (unlike VMs without any boot up process). Essentially *we are virtualizing the OS, instead of the hardware*. The environment scales as PaaS but gives flexibility like IaaS. Advantages to containerization:
  * Treating hardware and OS as a black box and making your code more portable.
  * You can move your code from development to staging to production 
  * You can move your code from laptop to cloud without changing/rebuilding anything.
  * For example, take each container as a microservice architecture making applications modular
  * Thus we can run our app seamlessly among various hosts using __KuberNetes__
  * We use __Docker__ to help build containers

### Kubernetes Engine

Kubernetes is an orchestrator for containers to better manage and scale applications. It lets you deploy containers on a set of nodes called cluster. Cluster consists of master (that controls the system as a whole) and a set of nodes (which run the containers and nodes are compute engine VMs). In *Kubernetes, nodes are computing instances but in Google Cloud, nodes are VMs running in Compute Engine.* __Kubernetes Engine__ is *kubernetes as a managed service in the cloud*.

#### :swimmer: Deep dive into Kubernetes Engine

* __pod__: Smallest deployable unit in Kubernetes. Usually we have one container for each pod. 
* `kubectl run nginx --image=nginx:1.15.7`starts a deployment with a container running in a pod.
* __deployment__: It refers to the group of replicas of the same pod
* __GKE__: It helps in load balancing for containers
* __service__: A service groups a set of pods together and provides a stable end point for them (like IP address). Services provide stable endpoints for nodes.
Instead of using kubectl commands, we can have a configuration file for service.

#### Containers

Transformation from monolithic application :railway_car: to containerized microservices application :bullettrain_side:.
Distributed systems housed on-premises are costly to upgrade :worried:
Getting more agile with cloud :sunglasses:

__Anthos__ Google's modern solution for hybrid and multi-cloud systems. It helps to keep some essential parts on premises while shifting some stuff to cloud.

### *Module: Applications in the Cloud*
