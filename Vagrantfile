# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false
  config.vm.network :private_network, ip: "192.168.11.11"
  config.vm.define "cafetria_local"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end

  # Ansible provisioning
  config.vm.provision "ansible" do |ansible|
    # Local config
    ansible.playbook = "cafetria_playbook.yml"
    ansible.inventory_path = "hosts"
    ansible.limit = "cafetria_local"
    ansible.verbose = 'vvv'
  end
end

