# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.define "webserver_dev" do |webserver_dev|

        webserver_dev.vm.box = "ubuntu/xenial64"
        webserver_dev.vm.network "private_network", ip: "192.168.33.10"
        webserver_dev.vm.network "forwarded_port", guest: 80, host: 8888
        webserver_dev.vm.network "forwarded_port", guest: 8080, host: 8080
        webserver_dev.vm.hostname = "develop.dev"

        webserver_dev.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

        webserver_dev.ssh.forward_agent = true

        webserver_dev.vm.provider "virtualbox" do |vb|
            vb.memory = "1824"
            vb.cpus = "2"
        end
    end
end
