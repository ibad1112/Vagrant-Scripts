Vagrant.configure("2") do |config|
  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/bionic64"
    web.vm.hostname = 'web'
    web.vm.box_url = "https://app.vagrantup.com/ubuntu/boxes/bionic64"

    web.vm.network :private_network, ip: "192.168.56.101"
    web.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh"
    web.vm.network "forwarded_port", guest: 80, host: 8080



    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "web"]
      v.gui = true
    end
    
    web.vm.provision "shell", inline: <<-SHELL
     apt-get update
     apt-get install -y apache2
    SHELL
 
 end


  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/bionic64"
    db.vm.hostname = 'db'
    db.vm.box_url = "https://app.vagrantup.com/ubuntu/boxes/bionic64"

    db.vm.network :private_network, ip: "192.168.56.102"
    db.vm.network :forwarded_port, guest: 22, host: 10222, id: "ssh"

    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "db"]
      v.gui = true
    end
  end

end




 
 
