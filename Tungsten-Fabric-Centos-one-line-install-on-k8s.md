Tungsten Fabric CNI can be installed on a Kubernetes cluster through multiple provisioning schemes.

This wiki will describe the most simplest of all: **A single yaml based install**

## Pre-requisites
1. **A running Kubernetes cluster**

   There are multiple options available to a user to install Kubernetes. The most simplest being [kubeadm](https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/)

   Alternatively if you would like to install Tungsten Fabric and K8s cluster together, you can use [Tungsten Fabric Ansible Deployer](https://github.com/Juniper/contrail-ansible-deployer/wiki/Contrail-microservice-installation-with-kubernetes). 

2. **Docker version on all nodes should be >= 1.24**

3. **Linux kernel version 3.10.0-957**

   Tungsten Fabric forwarding uses a kernel module to provide high throughput, low latency networking.

   The latest kernel module is compiled against 3.10.0-957 kernel.

## Installation
  Installation of Tungsten Fabric is a **1**-step process.

  Note: Replace x.x.x.x with the IP of your Kubernetes Master node.

```
K8S_MASTER_IP=x.x.x.x; CONTRAIL_REPO="docker.io\/opencontrailnightly"; CONTRAIL_RELEASE="latest"; mkdir -pm 777 /var/lib/contrail/kafka-logs; curl https://raw.githubusercontent.com/Juniper/contrail-kubernetes-docs/master/install/kubernetes/templates/contrail-single-step-cni-install-centos.yaml | sed "s/{{ K8S_MASTER_IP }}/$K8S_MASTER_IP/g; s/{{ CONTRAIL_REPO }}/$CONTRAIL_REPO/g; s/{{ CONTRAIL_RELEASE }}/$CONTRAIL_RELEASE/g" | kubectl apply -f -
```

## What just happened ?

**Hurray! Welcome to Tungsten Fabric.**

1. You installed Tungsten Fabric CNI in your Kubernetes node. If new compute nodes are added to your Kubernetes cluster, Tungsten Fabric CNI will be propogated to them auto-magically as it is backed by a Kubernetes DaemaonSet.

2. You installed entire Tungsten Fabric Networking suite with rich Networking, Analytics, Security, Visualization functions, to name a few.

3. Tungsten Fabric UI is available on port 8143 of your node.  Feel free to play around. [About Tungsten Fabric](https://www.juniper.net/documentation/en_US/release-independent/contrail/information-products/pathway-pages/index.html)
```
https://x.x.x.x:8143
Default credentials: admin/contrail123
```
## Check Tungsten Fabric Status

You can get the status of Tungsten Fabric components, by running "contrail-status" command line tool in your Kubernetes master node. This will list all Tungsten Fabric components running in your system.
```
[root@foo ~]# contrail-status
Pod         Service         Original Name                          State    Status         
            zookeeper       contrail-external-zookeeper            running  Up 35 minutes  
analytics   alarm-gen       contrail-analytics-alarm-gen           running  Up 35 minutes  
analytics   api             contrail-analytics-api                 running  Up 35 minutes  
analytics   collector       contrail-analytics-collector           running  Up 35 minutes  
analytics   nodemgr         contrail-nodemgr                       running  Up 33 minutes  
analytics   query-engine    contrail-analytics-query-engine        running  Up 35 minutes  
analytics   snmp-collector  contrail-analytics-snmp-collector      running  Up 35 minutes  
analytics   topology        contrail-analytics-topology            running  Up 34 minutes  
config      api             contrail-controller-config-api         running  Up 35 minutes  
config      cassandra       contrail-external-cassandra            running  Up 35 minutes  
config      device-manager  contrail-controller-config-devicemgr   running  Up 35 minutes  
config      nodemgr         contrail-nodemgr                       running  Up 33 minutes  
config      rabbitmq        contrail-external-rabbitmq             running  Up 35 minutes  
config      schema          contrail-controller-config-schema      running  Up 35 minutes  
config      svc-monitor     contrail-controller-config-svcmonitor  running  Up 35 minutes  
control     control         contrail-controller-control-control    running  Up 35 minutes  
control     dns             contrail-controller-control-dns        running  Up 35 minutes  
control     named           contrail-controller-control-named      running  Up 35 minutes  
control     nodemgr         contrail-nodemgr                       running  Up 33 minutes  
database    cassandra       contrail-external-cassandra            running  Up 35 minutes  
database    kafka           contrail-external-kafka                running  Up 35 minutes  
database    nodemgr         contrail-nodemgr                       running  Up 34 minutes  
kubernetes  kube-manager    contrail-kubernetes-kube-manager       running  Up 35 minutes  
vrouter     agent           contrail-vrouter-agent                 running  Up 34 minutes  
vrouter     nodemgr         contrail-nodemgr                       running  Up 33 minutes  
webui       job             contrail-controller-webui-job          running  Up 35 minutes  
webui       web             contrail-controller-webui-web          running  Up 35 minutes  

WARNING: container with original name 'contrail-external-zookeeper' have Pod os Service empty. Pod: '' / Service: 'zookeeper'. Please pass NODE_TYPE with pod name to container's env

vrouter kernel module is PRESENT
== Contrail control ==
control: active
nodemgr: initializing (NTP state unsynchronized. ) . <-- Safe to ignore
named: active
dns: active

== Contrail kubernetes ==
kube-manager: active

== Contrail database ==
kafka: active
nodemgr: initializing (NTP state unsynchronized. ) . <-- Safe to ignore
zookeeper: inactive                                  <-- Safe to ignore
cassandra: active

== Contrail analytics ==
nodemgr: initializing (NTP state unsynchronized. ) . <-- Safe to ignore
api: active
collector: active
query-engine: active
alarm-gen: active

== Contrail webui ==
web: active
job: active

== Contrail vrouter ==
nodemgr: initializing (NTP state unsynchronized. )    <-- Safe to ignore
agent: active

== Contrail config ==
api: active
zookeeper: inactive                                   <-- Safe to ignore
svc-monitor: active
nodemgr: initializing (NTP state unsynchronized. ) .  <-- Safe to ignore
device-manager: active
cassandra: active
rabbitmq: active
schema: active

```

## Get to know Tungsten Fabric more

[All about Tungsten Fabric](https://www.juniper.net/documentation/en_US/release-independent/contrail/information-products/pathway-pages/index.html)

[Tungsten Fabric and Kubernetes Intro](https://github.com/Juniper/contrail-controller/wiki/Kubernetes)

[Install Kubernetes using Kubeadm](https://github.com/Juniper/contrail-controller/wiki/Install-K8s-using-Kubeadm)

[Install Tungsten Farbric on AWS](Tungsten-Fabric-15-minute-deployment-with-k8s-on-AWS.md)
