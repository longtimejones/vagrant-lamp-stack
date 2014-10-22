Vagrant.configure("2") do |config|

    config.vm.box = "tjo/debian-76-x64-lamp-stack"

    config.vm.network "private_network", ip: "192.168.120.10"

    config.vm.synced_folder "http/", "/srv/http", group: "vhost", owner: "vagrant", :mount_options => ["dmode=775", "fmode=775"]
    config.vm.synced_folder "logs/", "/srv/logs", group: "vhost", owner: "vagrant", :mount_options => ["dmode=775", "fmode=775"]
    config.vm.synced_folder "vhosts/", "/srv/vhosts", group: "vagrant", owner: "vagrant", :mount_options => ["dmode=775", "fmode=775"]

    config.vm.provider "virtualbox" do |v|

	v.name = "Vagrant LAMP stack"
        v.customize ["modifyvm", :id, "--memory", "1024"]

    end

end