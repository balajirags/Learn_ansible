# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define 'web' do |machine|
    machine.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048"]
    end

    machine.vm.hostname = "web.com"
    machine.vm.network :private_network, ip: "192.168.99.102"
    machine.vm.box = "centos/7"
    machine.vm.network :forwarded_port, guest: 22, host: 2223, id: 'ssh'
  end

  config.vm.define 'db' do |machine|
    machine.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048"]
    end

    machine.vm.hostname = "db.com"
    machine.vm.network :private_network, ip: "192.168.99.103"
    machine.vm.box = "centos/7"
    config.vm.network :forwarded_port, guest: 22, host: 2224, id: 'ssh'
  end
end
