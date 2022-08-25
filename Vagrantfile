app = ENV['APP'] || 'linux'

Vagrant.configure("2") do |config|
  config.vm.hostname = "vagrant"
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.define "vagrant-#{app}"
  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
    vb.name = "vagrant-#{app}"
  end
  config.vm.network :private_network, ip: "192.168.168.168"
  config.vm.provision "ansible" do |ansible| 
    ansible.playbook="linux_playbooks/setup_new_server.yml" 
    ansible.extra_vars = {
      users_to_create: [],
      sudoers: []
    } 

  end 
end
