# POC docker swarm with portainer : For tests only

## Pre requisites (windows or linux)

* Vagrant
* virtualbox

## Creating the VM

```
git clone git@github.com:sgaunet/poc-swarm-portainer.git
cd poc-swarm-portainer
vagrant up
```

Enjoy.

## Extra informations :

Create a cluster swarm of 3 nodes with portainer installed on the manager

* n60 : 192.168.56.60
* n61 : 192.168.56.61  
* n62 : 192.168.56.62  (manager)

Portainer is deployed at the end

http://192.168.56.62:9000

# How does it work ?

vagrant is used to create 3 virtual machines and provision it with ansible (playbook.yml). This playbook installs docker, create a user called sylvain (password sylv1).
And at the end, an other provision script is launched on the manager (playbook2.yml) which will create the swarm...

* playbook.yml (launched in local on all nodes : allow thoses scripts to be used on windows)
* pllaybook2.yml (launched in the manager, ansible will connect to the other nodes with sylvain user, see hosts file for inventory)
