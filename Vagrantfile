# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.network "public_network", bridge: "BRIDGE" 
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.disk :disk, size: "10GB", primary: true
  config.vm.provider "virtualbox"
  config.vm.provider "virtualbox" do |v|
    v.name = "ubuntu_astra"
    v.linked_clone = true
    v.cpus = 4 
    v.memory = 4096
  end

  config.vm.provision "ansible" do |a|
    a.verbose = "v"
    a.playbook = "./ansible/playbook.yaml"
  end
end
