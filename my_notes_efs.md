# Automatized K8s cluster

## Resources

https://github.com/k3s-io/k3s-ansible
https://code-maven.com/enable-ansible-passwordless-sudo
https://www.ssh.com/academy/ssh/copy-id
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent


## My home setup

| Node   | Role    | IP            | Network        | Gateway     |
| ------ | ------- | ------------- | -------------- | ----------- |
| k8s-10 | master  | 192.168.42.10 | 192.168.0.0/16 | 192.168.1.1 |
| k8s-20 | worker  | 192.168.42.20 | 192.168.0.0/16 | 192.168.1.1 |
| k8s-21 | worker  | 192.168.42.21 | 192.168.0.0/16 | 192.168.1.1 |
| ------ | ------- | ------------- | -------------- | ----------- |
| NAS    | storage | 192.168.3.1   | 192.168.0.0/16 | 192.168.1.1 |
| router | router  | 192.168.1.1   | 192.168.0.0/16 | 192.168.1.1 |

*note: the gaps in the addressings are intentional, as I plan to add further master/worker nodes*

## Preparation

First, install the new servers and network them (my setup as per above; code need to be edited if your setup is different)

First step is to add your ssh keys to the nodes / NAS.
In case of Ubuntu servers, just install your GitHub credentials upon install.

Alternatively, [create new key](https://docs[.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and [copy it to the servers](https://www.ssh.com/academy/ssh/copy-id)

```sh
ssh-copy-id -i ~/.ssh/id_ed25519 ubuntu@192.168.42.10
```

## Cluster provisioning

New [guide](https://github.com/fabricesemti80/home-k8s-cluster)

~~For this we will refer to [this guide](https://github.com/k3s-io/k3s-ansible)~~

### Prep

* connect to each host via SSH before Ansible
