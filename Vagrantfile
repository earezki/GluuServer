Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "forwarded_port", guest: 9999, host: 9999
  config.vm.network "forwarded_port", guest: 9998, host: 9998
  #Use this network config when you have port collisions.
  #config.vm.network "private_network", ip: "172.16.0.10"
  
  config.vm.provider "virtualbox" do |vb|
     vb.memory = "3072"
	 vb.cpus = 2
	 vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
   end
  
   config.vm.provision "shell", inline: <<-SHELL
	 sudo su
	 echo "deb https://repo.gluu.org/ubuntu/ xenial main" > /etc/apt/sources.list.d/gluu-repo.list
	 curl https://repo.gluu.org/ubuntu/gluu-apt.key | apt-key add -
	 apt-get update
	 apt-get install gluu-server-3.1.3
	 apt-get install htop
  SHELL
  
end
