# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.define "lb1" do |lb1|
    lb1.vm.box = "hashicorp/bionic64"
    lb1.vm.network "private_network", ip: "10.0.0.10"
    lb1.vm.provision "shell", path: "https://gist.githubusercontent.com/arzybagas/33d5e684fb84686ca12bdb16f2f32659/raw/ffd1705ad57fa98cdf5646ba406779435e0e2374/provision-lb.sh"
  end

  config.vm.define "db1" do |db1|
    db1.vm.box = "hashicorp/bionic64"
    db1.vm.network "private_network", ip: "10.0.0.11"
    db1.vm.provision :shell do |shell|
      shell.args = "1"
      shell.path = "https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbnRsUjhkaVk1RnE1X2Ftd2VlRElRWm1yQWM0UXxBQ3Jtc0tuaHpNMXc3OTJHZWllZm13aXhDYTFkS0pya3dteFFMR1lLRXBxSmNfQWdiSWtDRjZXM281UmN5Wmh2dFBNOUJpV04zTThMekszMllSTl9WRjNfMEIwZVEzYkFQUS1OUG1JVnVyUjY5X1loZVBwdzNvSQ&q=https%3A%2F%2Fgist.githubusercontent.com%2Farzybagas%2Ff38727570fec59c8ed5c2cd6af5b3ddf%2Fraw%2Fb67f9539f2c338fee828715f8e681cedef76b89b%2Fprovision-db.sh"
    end
  end

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
