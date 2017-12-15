Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.56.250"
  config.vm.provision "ansible_local" do |ansible|
     ansible.verbose = "v"
     ansible.playbook = "vagrant.yml"
     ansible.sudo = true
  end
end
