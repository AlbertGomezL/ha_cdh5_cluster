# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "master" do |node|
      config.vm.box = "hashicorp/precise64"
      node.vm.hostname = "master"
      node.vm.network "private_network", ip: "192.168.33.10/24", virtualbox__intnet: "network"
      node.vm.provision "ansible" do |ansible|
        ansible.verbose = "v"
        ansible.playbook = "provision/playbook-namenode.yml"
      end
  end

  # config.vm.define "worker1" do |node|
  #   config.vm.box = "hashicorp/precise64"
  #   node.vm.hostname = "worker1"
  #   node.vm.network "private_network", ip: "192.168.33.11/24", virtualbox__intnet: "network"
  #   node.vm.provision "ansible" do |ansible|
  #     ansible.verbose = "v"
  #     ansible.playbook = "provision/playbook-datanode.yml"
  #   end
  # end

  # config.vm.define "worker2" do |node|
  #   config.vm.box = "hashicorp/precise64"
  #   node.vm.hostname = "worker2"
  #   node.vm.network "private_network", ip: "192.168.33.12/24", virtualbox__intnet: "network"
  #   node.vm.provision "ansible" do |ansible|
  #     ansible.verbose = "v"
  #     ansible.playbook = "provision/playbook-datanode.yml"
  #   end
  # end

  # config.vm.define "monkey" do |node|
  #   config.vm.box = "hashicorp/precise64"
  #   node.vm.hostname = "monkey"
  #   node.vm.network "private_network", ip: "192.168.33.13/24"
  #   node.vm.provision "ansible" do |ansible|
  #     ansible.verbose = "v"
  #     ansible.playbook = "playbook-namenode.yml"
  #   end
  # end

  config.vm.synced_folder "sync", "/vagrant", create: true

end

  
