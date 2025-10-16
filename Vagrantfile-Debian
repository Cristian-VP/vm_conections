# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "debian/bullseye64"
  config.vm.network "private_network", ip: "192.168.56.10"

  # set up Docker in the new VM:
  config.vm.provision :docker
  config.vm.provision :docker_compose

  # install docker-compose into the VM and run the docker-compose.yml file - if it exists -  whenever the  VM starts (https://github.com/leighmcculloch/vagrant-docker-compose)
  #config.vm.provision :docker_compose, yml: "/vagrant/docker-compose.yml", run:"always"

  config.vm.provider "virtualbox" do |vb|
    vb.name = 'debian-compose'
    vb.memory = 4096
    vb.cpus = 1
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end

end
