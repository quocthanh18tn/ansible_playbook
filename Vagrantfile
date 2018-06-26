# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure('2') do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = 'bento/ubuntu-16.04'
  config.ssh.insert_key = false


  config.vm.provider :virtualbox do |v|
    v.memory = 256
    v.linked_clone = true
  end

  config.vm.define 'web1' do |web|
    web.vm.hostname = 'web1.ersolution.net'
    web.vm.network :forwarded_port, guest: 80, host: 8080
  end

  config.vm.define 'web2' do |web|
    web.vm.hostname = 'web2.ersolution.net'
    web.vm.network :forwarded_port, guest: 80, host: 8081
  end

  config.vm.define 'db1' do |db|
    db.vm.hostname = 'db1.ersolution.net'
    db.vm.network :forwarded_port, guest: 80, host: 8082
  end

  config.vm.provision :ansible do |ans|
    ans.playbook = 'provisioning/playbook.yml'
  end
end
