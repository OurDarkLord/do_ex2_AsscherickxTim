Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"


  	config.vm.define "www1" do |www1|
        www1.vm.hostname = "www1.dev"
        www1.vm.network :private_network, ip: "192.168.2.3"
        www1.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
        www1.vm.network "forwarded_port", guest: 22, host: 3333, auto_correct: true
    end

    config.vm.define "www2" do |www2|
        www2.vm.hostname = "www2.dev"
        www2.vm.network :private_network, ip: "192.168.2.4"
        www2.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
        www2.vm.network "forwarded_port", guest: 22, host: 4444, auto_correct: true
    end

    config.vm.define "bl" do |bl|
        bl.vm.hostname = "bl.dev"
        bl.vm.network :private_network, ip: "192.168.2.5"
        bl.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
        bl.vm.network "forwarded_port", guest: 22, host: 5555, auto_correct: true
        bl.vm.network "forwarded_port", guest: 80, host: 8000, auto_correct: true
    end
    config.vm.define "mgr" do |mgr|
        mgr.vm.hostname = "mgr.dev"
        mgr.vm.network :private_network, ip: "192.168.2.6"
        mgr.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
        mgr.vm.network "forwarded_port", guest: 22, host: 6666, auto_correct: true
        mgr.vm.provision "shell", path: "hosts.sh"
        mgr.vm.provision "shell", path: "mgr.sh"

    end

end