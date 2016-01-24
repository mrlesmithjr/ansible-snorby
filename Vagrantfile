# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.define "snorby" do |snorby|
    snorby.vm.box = "mrlesmithjr/trusty64"
    snorby.vm.hostname = "snorby"

    snorby.vm.network :private_network, ip: "192.168.202.201"
    snorby.vm.network "forwarded_port", guest: 80, host: 8080
    snorby.vm.network "forwarded_port", guest: 3000, host: 3000

    snorby.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = "2"
    end
  end
  config.vm.provision :shell, path: "provision.sh", keep_color: "true"
end
