# -*- mode: ruby -*-

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.define "master" do |master|
    master.vm.hostname = "master.teste.lan"
    master.vm.box = "centos/7"

    master.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--cpus", "2" ]
        v.customize ["modifyvm", :id, "--memory", "1024" ]
    end
    master.vm.network "private_network", ip: "192.168.200.10", :adapter => 2
    master.ssh.forward_agent = true
  end

  config.vm.define "node" do |node|
    node.vm.hostname = 'node.teste.lan'
    node.vm.box = "centos/7"

    node.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--cpus", "1"]
        v.customize ["modifyvm", :id, "--memory", "1024"]
    end
    node.vm.network "private_network", ip: "192.168.200.11", :adapter => 2
  end
 
end
