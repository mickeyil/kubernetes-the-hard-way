Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  vm_names = ["jumpbox", "server", "node-0", "node-1"]
  vm_names.each_with_index do |name, index|
    config.vm.define name do |node|
      node.vm.hostname = name
      node.vm.network "private_network", ip: "192.168.56.#{10 + index}"

      node.vm.provider "virtualbox" do |vb|
        vb.name = name
        vb.memory = 2048
        vb.cpus = 2
      end
    end
  end
end