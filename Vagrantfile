# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	config.vm.box = 'mvbcoding/awslinux'

  config.ssh.insert_key = false
	config.ssh.forward_agent = true

	if Vagrant.has_plugin?("vagrant-proxyconf")
		config.proxy.http = ENV['http_proxy']
		config.proxy.https = ENV['http_proxys']
		config.proxy.no_proxy = "localhost,127.0.0.1"
	end

	config.vm.define "couch.local" do |m|
		m.vm.provider :virtualbox do |virtualbox|
			virtualbox.customize ["modifyvm", :id, "--memory", "2048"] 
		end
		m.vm.network "private_network", ip: "33.33.33.21" 
		#m.vm.network :forwarded_port, guest: 53639, host: 53639
	end
end
