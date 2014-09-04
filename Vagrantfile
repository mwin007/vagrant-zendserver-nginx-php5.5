# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'yaml'

localconfig = YAML::load_file("./config.yml")
shared_folder = localconfig["shared_folder"]

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu14.04-x64-zendserver7-nginx-php5.5"
  config.vm.box_url = "https://s3-eu-west-1.amazonaws.com/zend-de-vagrant-boxes/ubuntu14.04-x64-zendserver7-nginx-php5.5.box"
  
  config.vm.network "private_network", ip: localconfig['ip']

  config.vm.hostname = localconfig['name']
  if ! shared_folder.nil?
    shared_folder.each do |sf|
      item = sf.last
      config.vm.synced_folder item['host'], item['guest'], rsync__exclude: ".git/"
    end
  end
  
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", localconfig['memory']]
    v.customize ["modifyvm", :id, "--name", localconfig['name']]
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
end
