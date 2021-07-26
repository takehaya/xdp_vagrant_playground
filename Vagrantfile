# -*- mode: ruby -*-
Vagrant.configure("2") do |config|
    config.vm.box = "bento/ubuntu-21.04"
    config.vm.boot_timeout = 500
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
      vb.cpus = 4
      vb.customize [
        "modifyvm", :id,
        "--hwvirtex", "on",
        "--nestedpaging", "on",
        "--largepages", "on",
        "--ioapic", "on",
        "--pae", "on",
        "--paravirtprovider", "kvm",
        "--nicpromisc1", "allow-all",
      ]
    end
    config.vm.provision "shell", path: "./env_init.sh"
    config.vm.synced_folder "../../Workspace/Vinbero", "/home/vagrant/workspace"

end
