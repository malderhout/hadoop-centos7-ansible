# Change ip is necessary
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "malderhout/centos7"
  config.vm.network :private_network, ip: "192.168.50.200"
  config.vm.hostname = "localhost"
  config.vm.network “forwarded_port”, guest: 50070, host: 50070

  # configuration for Ansible.
  config.vm.provision "ansible" do |ansible|
    ansible.raw_arguments = "-i hosts"
    ansible.playbook = "playbook.yml"
    # Run commands as root.
    ansible.sudo = true
  end
end
