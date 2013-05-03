Vagrant.configure("2") do |config|
	config.vm.box = "centos63"
	config.vm.box_url = "http://db.tt/3ZoNiQjp"
	
	config.vm.network :forwarded_port, guest: 80, host: 8080
	config.vm.network :private_network, ip: "192.168.56.60"
	config.vm.hostname = "phpdev.local"
	config.vm.provider "virtualbox" do |v|
  		v.customize ["modifyvm", :id, "--memory", "2048"]
		v.customize ["modifyvm", :id, "--vram", "12"]
                v.customize ["modifyvm", :id, "--cpus", "2"]
	end
	config.vm.synced_folder "./project", "/project"
	

	config.vm.provision :puppet do |puppet|
		puppet.manifests_path = "manifests"
		puppet.manifest_file  = "init.pp"
		puppet.module_path = "modules"
	end

	
end