# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # config.vm.box = "debian/stretch64"
  # config.vm.box = "ubuntu/xenial64"
  config.vm.box = "ubuntu/bionic64"
  # config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = 1024
    vb.cpus = 1
  end

  config.vm.provision "shell", inline: <<-SHELL
    echo -ne "vagrant ALL=(ALL:ALL) NOPASSWD: ALL" >> /etc/sudoers.d/ansible
    mkdir -p /etc/ansible/roles
    ln -fs /vagrant /etc/ansible/roles/couchpotato
  SHELL

  config.vm.provision "ansible_local" do |ansible|
    ansible.install_mode        = "pip"
    ansible.limit               = "all"
    ansible.playbook            = "tests/test.yml"
    ansible.verbose             = true
    ansible.version             = "2.5.0"
  end
end
