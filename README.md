# Vagrant for Ansible development

This project contains a Vagrantfile which deploys CentOS 7 hosts on Vritualbox Hypervisor.
Once these hosts are deployed, the Ansible Playbook can be used to prepare the hosts for further Ansible development. 
The purpose of these hosts is to act as Ansible managed nodes for development.

# Requirements

- Vagrant
- Virtualbox
- Master Node with Ansible (e.g. WSL Ubuntu or any other Linux distribution)

# Usage 

Deploy the virtual machines, use Powershell and change to directory with the Vagrantfile:
```
vagrant up 
```

The number of VMs to be deployed can be adjusted in the Vagrantfile by changing this variable:
```
NODE_COUNT = 2
```
If you change the number of nodes, add the addtional IPs to the inventory.


When the hosts are deployed sucessfully, run the Ansible playbook for further configuration:
```
ansible-playbook provision -i inventory
```