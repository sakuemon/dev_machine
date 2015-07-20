# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "TODO set box"
  config.vm.hostname = 'TODO set hostname'

  config.vm.network "private_network", ip: "TODO set ip address to host"

  config.vm.provider "virtualbox" do |v|
  	v.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
  end

  config.vm.synced_folder "TODO set source folder in local host",
                          "TODO set source folder in remote host" ,
                          type:"rsync", create:true,
                          rsync__exclude: [".git/",
                          ]

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./provision/site.yml"
    ansible.inventory_path = "hosts"
    ansible.limit = "all"
    ansible.verbose = "v"
  end
end
