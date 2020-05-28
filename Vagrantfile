Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.define :master do |master|
     master.vm.hostname = 'master'
     #master.vm.network "private_network", ip: "192.168.10.1"
     master.vm.provider :libvirt do |v|
       v.memory = 1024
       v.qemu_use_session = false
       v.cpus = 1
     end
   end
  config.vm.define :node do |node|
     node.vm.hostname = 'node'
     #node.vm.network "private_network", ip: "192.168.10.2"
     node.vm.provider :libvirt do |v|
       v.memory = 1024
       v.cpus = 1
       v.qemu_use_session = false
     end
   end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "setup-ansible.yml"
  end
end
