# Install required plugins
required_plugins = ["vagrant-hostsupdater"]
required_plugins.each do |plugin|
    exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
end

Vagrant.configure("2") do |config|
    config.vm.define "python" do |py|
      py.vm.box = "ubuntu/bionic64"
      py.vm.network "private_network", ip: "192.168.10.112"
      py.hostsupdater.aliases = ["control.local"]
      py.vm.synced_folder "environment1", "/home/vagrant/environment"
      py.vm.synced_folder "stuffneeded", "/home/vagrant/stuffneeded"
      py.vm.synced_folder "Downloads", "/home/vagrant/Downloads"

      py.vm.provision :ansible_local do |ansible|
        ansible.playbook       = "/home/vagrant/environment/theinitialplaybook.yml"
        ansible.verbose        = true
        ansible.install        = true
      end
      py.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
      end
    end
end
