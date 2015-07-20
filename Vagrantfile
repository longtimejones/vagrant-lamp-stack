# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Vagrant recommends you use key-based authentication rather than a password.
  # By default the private key to use to SSH into the guest machine is the
  # insecure private key that ships with Vagrant, since that is what public
  # boxes use.
  config.ssh.insert_key = false

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "tjo/debian-jessie64-lamp-stack"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.120.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # VirtualBox provider configuration:
  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "1024"
    # Customize the name that appears in the VirtualBox GUI:
    vb.name = "Debian jessie x64 LAMP stack"
  end

  # Specify an IP address to return for any host in the given domains
  config.vm.provision "shell", run: "always", inline: <<-SHELL
    sudo echo "address=/.local/192.168.120.10" > /etc/dnsmasq.d/pseudo.tld
  SHELL
  config.vm.provision "shell", inline: "sudo service dnsmasq restart", run: "always"
end
