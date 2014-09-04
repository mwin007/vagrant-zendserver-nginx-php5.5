Zend Server 7 and Vagrant
=========

After downloading Vagrantfile and config.yml.dist, please make sure that you rename config.yml.dist to config.yml and that the settings in the config suit your needs.

This is what you get
----------------
Ubuntu 14.04 x64, with a preinstalled Zend Server 7, Apache and PHP 5.5.
Zend Server is not bootstrapped after initial install, which means that you have to open Zend Server GUI in your browser (http://#your-vm-ip#:10081) and follow the wizard. If you choose the 'development' mode, the browser toolbar Z-Ray will be set up automatically.
