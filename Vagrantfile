# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = 'trusty-server-cloudimg-amd64'
  config.vm.box_url = 'https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box'

  #config.vm.network :forwarded_port, guest: 80, host: 3080

  config.vm.provider "virtualbox" do |vb|
    # Don't boot with headless mode
    vb.gui = true

    # Use VBoxManage to customize the VM. For example to change memory:
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end

  config.vm.provision "ansible" do |ansible|
    ENV["ANSIBLE_COW_SELECTION"] ||= "random"
    ansible.playbook = "provisioning/site.yml"
    ansible.verbose = "v"
    ansible.tags = ENV["ANSIBLE_TAGS"] if ENV["ANSIBLE_TAGS"]
  end

  config.vm.define "vm1" do |vm1|
   vm1.vm.hostname = "vm1"
   vm1.vm.network :private_network, ip: "192.168.50.11"
   vm1.vm.network :private_network, ip: "192.168.11.11"
  end

  config.vm.define "vm2" do |vm2|
   vm2.vm.hostname = "vm2"
   vm2.vm.network :private_network, ip: "192.168.50.12"
   vm2.vm.network :private_network, ip: "192.168.12.12"
  end
end
