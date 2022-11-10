# K8s @ home

Ansible playbook to set up my very own kubernetes cluster with GPU support.

**Features**:
- Installs nvidia drivers, docker, k8s (via kubeadm), nvidia docker runtime
- Disable swap
- Install some basic helm charts (eg. traefik)
- Install basic apt packages (eg. nfs, btrfs, mergerfs, haproxy, mosh)

## Setting up a node
Install `ubuntu 22.04 LTS server` on a new node. When going through the install add ssh keys from github (not necessary but makes things easier).  
No need to install any additional software.

## Preparations
- Rename `inventory.sample` to `inventory` and populate it with your nodes.
- Install roles:
```
ansible-galaxy install -r requirements.yml
```

## Running the playbook
Having matching passwords and users on all nodes makes this step easier.
  
     ansible-playbook main.yml --ask-become


## Author
This playbook was created by Noran Raskin
