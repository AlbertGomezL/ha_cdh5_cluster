# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config| 
  
  config.vm.define "datanode1" do |node|
    config.vm.box = "hashicorp/precise64"
    node.vm.hostname = "datanode1"
    node.vm.network "private_network", ip: "10.0.0.13", virtualbox__intnet: "network"
    node.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provision/playbook-datanode.yml"
    end
  end

  config.vm.define "datanode2" do |node|
    config.vm.box = "hashicorp/precise64"
    node.vm.hostname = "datanode2"
    node.vm.network "private_network", ip: "10.0.0.12", virtualbox__intnet: "network"
    node.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provision/playbook-datanode.yml"
    end
  end
  
  config.vm.define "namenode" do |node|
    config.vm.box = "hashicorp/precise64"
    node.vm.hostname = "namenode"
    node.vm.network "private_network", ip: "10.0.0.11", virtualbox__intnet: "network"
    node.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "provision/playbook-namenode.yml"
    end
  end
 

  config.vm.synced_folder "sync", "/vagrant", create: true

end

  
