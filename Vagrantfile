Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"
  config.vm.box_download_insecure = true

  config.vm.define "vm01" do |vm01|
      vm01.vm.network "private_network", ip: "10.2.0.21"
      vm01.vm.synced_folder "share/", "/share"
      vm01.vm.provision "shell", inline: "cat /share/key01.pub >> .ssh/authorized_keys"
      vm01.vm.provision "shell", path: "./scripts/docker.sh"
      vm01.vm.provider "virtualbox" do |vb|
        vb.name = "vm01"
      end
  end

  config.vm.define "vm02" do |vm02|
    vm02.vm.network "private_network", ip: "10.2.0.22"
    vm02.vm.synced_folder "share/", "/share"
    vm02.vm.provision "shell", inline: "cat /share/key01.pub >> .ssh/authorized_keys"
    vm02.vm.provision "shell", path: "./scripts/docker.sh"
    vm02.vm.provider "virtualbox" do |vb|
      vb.name = "vm02"
    end
  end

  config.vm.define "vm03" do |vm03|
    vm03.vm.network "private_network", ip: "10.2.0.23"
    vm03.vm.synced_folder "share/", "/share"
    vm03.vm.provision "shell", inline: "cat /share/key01.pub >> .ssh/authorized_keys"
    vm03.vm.provision "shell", path: "./scripts/docker.sh"
    vm03.vm.provider "virtualbox" do |vb|
      vb.name = "vm03"
    end
  end
end