# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  # config.vm.box = "ubuntu/trusty64"
  config.vm.box = "hashicorp/precise64"

  config.vm.hostname = "vagranttest"

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
  end

  # Add usb filter to attach mojo v3
 config.vm.provider :virtualbox do |vb|
   vb.customize ['modifyvm', :id, '--usb', 'on']
   vb.customize ['usbfilter', 'add', '0', '--target', :id, '--name', 'Mojo V3', '--vendorid', '0x29dd', '--productid', '0x8001']
   vb.customize ['usbfilter', 'add', '0', '--target', :id, '--name', 'Mojo V3 Bootloader', '--vendorid', '0x29dd', '--productid', '0x0001']
 end

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 4000, host: 4000, auto_correct: true

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "_playbook.yml"
  end
end
