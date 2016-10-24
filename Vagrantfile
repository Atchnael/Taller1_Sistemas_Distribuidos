# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|


  config.vm.define :centos_web_server do |node|  	
     node.vm.box = "centos64_update"
     node.vm.network :private_network, ip: "192.168.56.101"
     node.vm.network "public_network", :bridge => "eth3", ip:"192.168.130.91", :auto_config => "false", :netmask => "255.255.255.0"
     node.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "512","--cpus", "1", "--name", "centos_web_server" ]
     end
     config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "apache"
     end	
  end


  config.vm.define :centos_web_node1 do |node|   
     node.vm.box = "centos64_update"
     node.vm.network :private_network, ip: "192.168.56.102"
     node.vm.network "public_network", :bridge => "eth3", ip:"192.168.130.92", :auto_config => "false", :netmask => "255.255.255.0"
     node.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "512","--cpus", "1", "--name", "centos_web_node1" ]
    end
    config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "apache"
    end 
  end


  config.vm.define :centos_web_node2 do |node|   
     node.vm.box = "centos64_update"
     node.vm.network :private_network, ip: "192.168.56.103"
     node.vm.network "public_network", :bridge => "eth3", ip:"192.168.130.93", :auto_config => "false", :netmask => "255.255.255.0"
     node.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "512","--cpus", "1", "--name", "centos_web_node2" ]
    end
    config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "apache"
    end 
  end



  config.vm.define :centos_database do |db|
     db.vm.box = "centos64_update"
     db.vm.network :private_network, ip: "192.168.56.104"
     db.vm.network "public_network", :bridge => "eth3", ip:"192.168.130.94", :auto_config => "false", :netmask => "255.255.255.0"
     db.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "512","--cpus", "1", "--name", "centos_database" ]
    end
    config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "postgres"
    end 
  end

end
