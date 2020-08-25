# -*- mode: ruby -*-
# vi: set ft=ruby :

#
# Vagrant File for minimal CentOS 7 Hosts
#

# Number of Hosts to deploy
NODE_COUNT = 2

Vagrant.configure("2") do |config|
  # General Vagrant VM configuration
  config.vm.box = "geerlingguy/centos7"
  config.ssh.insert_key = false
  config.vm.provider "virtualbox" do |v|
    v.memory = 384
    v.linked_clone = true
	v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
  
  # Hosts (this deploys as many machines, as is defined in the NODE_COUNT variable)
  (1..NODE_COUNT).each do |i|
    config.vm.define "local-test-vm-#{i}" do |host|
      host.vm.hostname = "local-test-vm-#{i}"
      host.vm.network "private_network", ip: "192.168.50.1#{i}"
    end
  end
end