Vagrant.configure("2") do |config|
  # Base image Debian (gunakan Debian 11/12 yang stabil di Vagrant Cloud)
  BOX_IMAGE = "debian/bookworm64"

  # ==========================================
  # 1. Ansible Control Node (192.168.56.5)
  # ==========================================
  config.vm.define "control" do |node|
    node.vm.box = BOX_IMAGE
    node.vm.hostname = "control-node"
    node.vm.network "private_network", ip: "192.168.56.5"
    
    node.vm.provider "virtualbox" do |vb|
      vb.name = "ansible-control-node"
      vb.memory = "1024"
      vb.cpus = 1
    end

    # Otomatis install Ansible di dalam Control Node saat VM pertama kali menyala
    node.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y ansible sshpass curl git
    SHELL
  end

  # ==========================================
  # 2. Target VM 1: Web Server (192.168.56.10)
  # ==========================================
  config.vm.define "web" do |node|
    node.vm.box = BOX_IMAGE
    node.vm.hostname = "web-server"
    node.vm.network "private_network", ip: "192.168.56.10"
    
    node.vm.provider "virtualbox" do |vb|
      vb.name = "target-web-server"
      vb.memory = "1024"
      vb.cpus = 1
    end
  end

  # ==========================================
  # 3. Target VM 2: DB Server (192.168.56.11)
  # ==========================================
  config.vm.define "db" do |node|
    node.vm.box = BOX_IMAGE
    node.vm.hostname = "db-server"
    node.vm.network "private_network", ip: "192.168.56.11"
    
    node.vm.provider "virtualbox" do |vb|
      vb.name = "target-db-server"
      vb.memory = "1024"
      vb.cpus = 1
    end
  end
end