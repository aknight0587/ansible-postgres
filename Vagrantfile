Vagrant.configure("2") do |config|
  config.vm.define "ubuntu" do |ubuntu|
   ubuntu.vm.box = "ubuntu/xenial64"
   ubuntu.vm.network "private_network", ip: "192.168.56.250"
   ubuntu.vm.provision "ansible_local" do |ansible|
     ansible.verbose = "v"
     ansible.playbook = "postgres.yml"
     ansible.sudo = true
  end
 end
  config.vm.define "centos" do |centos|
   centos.vm.box = "bento/centos-7.4"
   centos.vm.network "private_network", ip: "192.168.56.251"
   centos.vm.provision "shell",
     inline: "sudo yum install -y libselinux-python"
   centos.vm.provision "shell",
     inline: "sudo yum groupinstall -y \"Development tools\""
   centos.vm.provision "ansible_local" do |ansible|
     ansible.verbose = "v"
     ansible.playbook = "postgres.yml"
     ansible.sudo = true
  end
 end
end
