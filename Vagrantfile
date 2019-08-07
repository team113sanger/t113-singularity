# -*- mode: ruby -*-

Vagrant.configure("2") do |config|
  config.vm.box = "sylabs/singularity-3.2-ubuntu-bionic64"
	config.vm.box_version = "20190529.0.0"

	config.ssh.forward_x11 = true
	config.ssh.forward_agent = true

	config.vm.provider "virtualbox" do |vb|
        	vb.gui = false
	end

	config.vm.provision "shell", inline: <<-SHELL
		sudo apt-get update
		sudo apt-get install -y git
		mkdir -p ~/.ssh
		chmod 700 ~/.ssh
		ssh-keyscan -H github.com >> ~/.ssh/known_hosts
		ssh -T git@github.com
		git clone git@github.com:team113sanger/t113-singularity.git
	SHELL

#	config.vm.provision :reload
end