# -*- mode: ruby -*-
# vim: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
# config.vm.box_check_update = true
# config.vbguest.auto_update = false
	
	

  
  config.vm.define "test3", primary: true do |w|
    w.vm.hostname = 'test3'
    w.vm.network "private_network", ip: "192.168.100.10"
	w.vm.provider :virtualbox do |v|
		v.name = "test3"
		v.customize ["modifyvm", :id, "--cpus", 1, "--memory", "1024"]

    end

	w.vm.provision "ansible" do |ansible|
	    ansible.limit = "all"
		ansible.inventory_path = "./inventory"
		ansible.playbook = "ansible/web.yml"
        ansible.become = "true"
        ansible.verbose = "v"
	end
	
  end


  
end

