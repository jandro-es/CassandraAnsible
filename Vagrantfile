# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant Configuration file for Cassandra learning using Ansible for provisioning
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "Precision64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  
  config.vm.network "private_network",ip: "10.0.0.10"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  
  config.vm.define "localhost" do |l|
    l.vm.hostname = "localhost"
  end

  config.vm.provider :virtualbox do |vb|
    vb.name = "ansible-role-cassandra"
  end
  
  config.vm.synced_folder ".", "/var/www/local.cassandra", type: "nfs"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"] 
  end

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "ansible/playbook.yml"
    ansible.verbose = "v"
    ansible.host_key_checking = false
    ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
  end
end
