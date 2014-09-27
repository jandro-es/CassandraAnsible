Cassandra Ansible development box
==================================

Creates, using Vagrant, virtual boxes with Apache Cassandra and DataStax's OpsCenter.

Suitable only for development, not for production, although with minumum modifications can be suitable for production.

###Requirements
You need to install on your development machine the following:

######Vagrant

Donwload it from <http://www.vagrantup.com/> and follow the instructions.
 
######Virtual box
Download from <https://www.virtualbox.org/> the one that suits your system
 
######Vagrant guests additions plugin

	vagrant plugin install vagrant-vbguest
	
######Ansible
In Mac OSX with Macports:
	
	sudo port install ansible
	
In Mac OSX with Homebrew:

	brew install ansible

In Ubuntu:

	sudo apt-get update

	sudo apt-get install python-software-properties

	sudo add-apt-repository ppa:rquillo/ansible

	sudo apt-get update

	sudo apt-get install ansible

