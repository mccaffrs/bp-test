# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "docker"
  ssh_public_key = File.read(File.join(Dir.home, ".ssh", "id_rsa.pub"))

  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    echo "#{ssh_public_key}" >> /home/vagrant/.ssh/authorized_keys
  SHELL
  end
  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "install-docker.yml"
	if File.file?(".vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory")
    ansible.inventory_path = ".vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory"
    ansible.verbose = "v"
  end
end
