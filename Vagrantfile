# -*- mode: ruby -*-
# vi: set ft=ruby :

# BOX_IMAGE = "centos/8"
BOX_IMAGE = "bento/ubuntu-20.04"
MEMORY = "2048"
CPU = "2"

Vagrant.configure("2") do |config|
  config.vm.define "node1" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "node1"
	subconfig.vm.network :private_network, ip: "192.168.56.111"
	subconfig.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", MEMORY]
          vb.customize ["modifyvm", :id, "--cpus", CPU]
	end
  end
  config.vm.define "node2" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "node2"
	subconfig.vm.network :private_network, ip: "192.168.56.112"
	subconfig.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", MEMORY]
          vb.customize ["modifyvm", :id, "--cpus", CPU]
	end
  end
  #Install some additional packages 
  config.vm.provision "shell", inline: <<-SHELL
	sudo su
	sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config    
    systemctl restart sshd.service
	apt -y install nano
	apt -y install net-tools
  SHELL
end