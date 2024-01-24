# k8s-raw-vcluster Vagrant Cluster

Bootstrap a local **2 nodes** cluster using Vagrant in order to test kubernetes installation procedure.

This project aim to help quickly bootstrap a k8s training cluster for testing, devolpment or training purposes.

## Prerequisites

Please go ahead and install these two components from their official website.

- [Vagrant](https://www.vagrantup.com)
- [VirtualBox](https://www.virtualbox.org)

## Provision the Kubernetes cluster

```sh
vagrant up
```

Now Vagrant will start provisioning the cluster starting with the `controlplane` node and the the worker node.
This setup is available with 2 nodes: a master node (`controlplane`) and a worker node (`node01`).

If you wish to bootstarp additional worker nodes please feel free to update your `VagrantFile` accordingly.

## Work with the cluster

```sh
vagrant ssh controlplane
```

Now you may start playing around with the cluster and practice kubernetes installation.
Please refer to k8s documentation for further details about [Bootstrapping clusters with kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/).

## Delete cluster

```sh
vagrant destroy -f
```

## Environment technical details

### Nodes

|     Name     |   IP address   |   CPU   |  Memory(Mi)  |
|--------------|----------------|---------|--------------|
| controlplane |  192.168.56.10 |    2    |     2048     |
|   node01     |  192.168.56.11 |    1    |     1024     |



