# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.network "forwarded_port", guest: 8080, host: 8880
  config.vm.network "forwarded_port", guest: 8081, host: 8881
  config.vm.network "forwarded_port", guest: 8082, host: 8882
  config.vm.network "forwarded_port", guest: 8083, host: 8883
  config.vm.network :private_network, ip: "192.168.222.116"

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.provision "ansible" do |ansible|
    #ansible.verbose = 'vvvv'
    ansible.limit = 'twofishes_vagrant'
    ansible.playbook = "provisioning/vagrant.yml"
    ansible.inventory_path = "provisioning/ansible_hosts"
  end
end
