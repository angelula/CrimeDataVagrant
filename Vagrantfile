Vagrant.configure("2") do |config|
  config.vm.box = "artem-sidorenko/mint-18.1-cinnamon"
  config.vm.network "forwarded_port", guest: 9000, host:9000, protocol: "tcp"
  config.vm.network "forwarded_port", guest: 3000, host:8080, protocol: "tcp"
  config.vm.network "forwarded_port", guest: 22, host:222, protocol: "tcp"
  config.vm.synced_folder ".", "/vagrant", type: "nfs", :mount_options => ["dmode=755","fmode=755"]
  
  config.vm.provider :virtualbox do |vb|
    vb.gui = true
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--vram", "128"]
    vb.customize ["modifyvm", :id, "--graphicscontroller", "vboxvga"]
    vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
    vb.customize ["modifyvm", :id, "--hwvirtex", "on"]
    vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    vb.memory = 4096 
    vb.cpus = 2
  end
end
