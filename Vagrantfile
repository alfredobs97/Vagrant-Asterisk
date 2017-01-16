Vagrant.configure("2") do |config|
  config.vm.define "Asterisk" do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.box_url = "https://atlas.hashicorp.com/ubuntu/boxes/trusty64"
    config.vm.hostname = "Asterisk"

    config.vm.network :"public_network"
    config.vm.synced_folder "asterisk", "/home/vagrant/asterisk"

    config.vm.provision :ansible do |ansible|
    ansible.playbook = "tasks/tasks.yml"
    end

   config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "Asterisk"]
    end
  end
end
