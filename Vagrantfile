Vagrant.require_version ">= 2.2.7"

Vagrant.configure("2") do |config|
  config.vm.define "pp_master" do |pp_master|
    pp_master.vm.box = "ubuntu/xenial64"
    pp_master.vm.hostname = 'master'
    pp_master.vm.network :private_network, ip: "172.20.10.15"
    pp_master.vm.provision "shell" do |enable_pp|
      enable_pp.inline = "wget https://apt.puppetlabs.com/puppet6-release-bionic.deb"
      enable_pp.inline = "sudo dpkg -i puppet6-release-bionic.deb -y"
      enable_pp.inline = "sudo apt-get update -y"
      enable_pp.inline = "sudo apt-get install puppetserver -y"
    end
  end
  config.vm.define "pp_node01" do |pp_node01|
    pp_node01.vm.box = "ubuntu/xenial64"
    pp_node01.vm.hostname = 'node01'
    pp_node01.vm.network :private_network, ip: "172.20.10.16"
  end
end