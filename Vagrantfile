# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
    
  config.vm.define :master do |master_config|
    master_config.vm.box = "centos/7"
    master_config.vm.box_url = "https://atlas.hashicorp.com/centos/boxes/7"
  
    master_config.vm.network :forwarded_port, guest: 8080, host: 8080
    master_config.vm.network :private_network, ip: "192.168.33.10"
  
    master_config.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/master.yml"
      #ansible.raw_arguments = "--check"
      ansible.inventory_path = "vagrant_ansible_inventory_master"
      ansible.verbose = "v"
    end
  end
  
  
  config.vm.define :node1 do |node1_config|
    node1_config.vm.box = "centos/7"
    node1_config.vm.box_url = "https://atlas.hashicorp.com/centos/boxes/7"
  
    node1_config.vm.network :private_network, ip: "192.168.33.20"
  
    node1_config.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/nodes.yml"
      #ansible.raw_arguments = "--check"
      ansible.inventory_path = "vagrant_ansible_inventory_node"
      ansible.verbose = "v"
    end
  end
  
  
  config.vm.define :node2 do |node2_config|
    node2_config.vm.box = "centos/7"
    node2_config.vm.box_url = "https://atlas.hashicorp.com/centos/boxes/7"
    
    node2_config.vm.network :private_network, ip: "192.168.33.30"
    
    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "1024"]
    end
  
    node2_config.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/nodes.yml"
      #ansible.raw_arguments = "--check"
      ansible.inventory_path = "vagrant_ansible_inventory_node"
      ansible.verbose = "v"
    end
  end
  
end