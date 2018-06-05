ENV["LC_ALL"] = "en_US.UTF-8"

SUBNET_PREFIX = "172.168.110."
MASTER_IP = SUBNET_PREFIX+"10"

MASTER_MEM = 1024
MASTER_CPUS = 1

Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/xenial64"

    config.vm.define "webserver" do |webserver|
        webserver.vm.provider :virtualbox do |vb|
            vb.name = "linux-playground"
            vb.memory = MASTER_MEM
            vb.cpus = MASTER_CPUS
        end
        webserver.vm.hostname = "server.nogada.dev"
        webserver.vm.network :private_network, ip: MASTER_IP
        webserver.vm.synced_folder "./", "/vagrant", type: "nfs"
    end


end