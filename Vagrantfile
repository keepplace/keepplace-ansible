
# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/vivid64"
#  config.vm.box_url = "http://files.vagrantup.com/vivid64.box"

  config.vm.network :public_network

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--name", "MyCoolApp", "--memory", "1024",  "--cpus", "4", "--cpuexecutioncap", "90"]
  end

  # Shared folder from the host machine to the guest machine. Uncomment the line
  # below to enable it.
#  config.vm.synced_folder "../../youtube-audio-dl", "/webapps/youtube-audio-dl/youtubeadl"

  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "vagrant.yml"
    ansible.host_key_checking = false
    ansible.verbose = "vvvv"
  end
end