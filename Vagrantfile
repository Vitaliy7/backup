# -*- mode: ruby -*-
# vim: set ft=ruby :
ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_version = "2004.01"
  config.vm.box_check_update = false
  
  config.vm.define "backup" do |backup|
      backup.vm.network  "private_network", ip: "192.168.11.160"
      backup.vm.hostname = "backup" 
      backup.vm.disk :disk, size: "2GB", name: "bckp"
      backup.vm.provider "virtualbox" do |vb|
         vb.memory = "4096"
         
      end
  end
     
 config.vm.define "client" do |client|
      client.vm.network  "private_network", ip: "192.168.11.150"
      client.vm.hostname = "client"  
      client.vm.provider "virtualbox" do |vb|
         vb.memory = "4096"
     end
 end
      
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml" 
 end
end
