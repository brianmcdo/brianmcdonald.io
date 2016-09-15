Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
  config.vm.provision :docker
  config.vm.provision :docker_compose, run: "always"

  config.vm.synced_folder ".", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
      vb.name = "brianmcdonald.io"
      vb.customize ["modifyvm", :id, "--memory", "1536"]
      vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end
end