Vagrant.require_version ">= 2.2.7"

Vagrant.configure("2") do |config|
  config.vm.define "pp_master" do |pp_master|
    pp_master.vm.box = "ubuntu/xenial64"
    pp_master.vm.hostname = 'master'
    pp_master.vm.network :private_network, ip: "172.20.10.15"
    
    pp_master.vm.provision "get_pp_pkgs", type: "shell",
      inline: "wget https://apt.puppetlabs.com/puppet6-release-xenial.deb"
  
    pp_master.vm.provision "add_pp_pkgs", type: "shell",
      inline: "sudo dpkg -i puppet6-release-xenial.deb"
    
    pp_master.vm.provision "update_pkgs", type: "shell",
      inline: "sudo apt-get update -y"
    
    pp_master.vm.provision "install_pp_server", type: "shell",
      inline: "sudo apt-get install puppetserver -y"
  end

  config.vm.define "pp_node01" do |pp_node01|
    pp_node01.vm.box = "ubuntu/xenial64"
    pp_node01.vm.hostname = 'node01'
    pp_node01.vm.network :private_network, ip: "172.20.10.16"

    pp_node01.vm.provision "get_pp_pkgs", type: "shell",
      inline: "wget https://apt.puppetlabs.com/puppet6-release-xenial.deb"
  
    pp_node01.vm.provision "add_pp_pkgs", type: "shell",
      inline: "sudo dpkg -i puppet6-release-xenial.deb"
    
    pp_node01.vm.provision "update_pkgs", type: "shell",
      inline: "sudo apt-get update -y"
    
    pp_node01.vm.provision "install_pp_server", type: "shell",
      inline: "sudo apt-get install puppet-agent -y"
  end
end