Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-6.8"
  config.vm.network "private_network", ip: "192.168.56.250"
  config.vm.provision "shell",
     inline: "sudo yum install -y libselinux-python"
  config.vm.provision "shell",
     inline: "sudo yum groupinstall -y \"Development tools\""
  config.vm.provision "ansible_local" do |ansible|
     ansible.verbose = "v"
     ansible.playbook = "vagrant.yml"
     ansible.sudo = true
  end
end
