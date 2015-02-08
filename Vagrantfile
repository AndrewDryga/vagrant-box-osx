# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Box file URL
  config.vm.box = "http://files.dryga.com/boxes/osx-yosemite-0.2.0.box"

  # Default settings for this box (this string is safe to remove, since they already packed in box)
  # config.ssh.insert_key = false # Removes annoying message about public key replacement
  # config.vm.synced_folder ".", "/vagrant", :disabled => true # VirtualBox doesn't support Guest Additions for Mac OS X
  # vb.customize ["modifyvm", :id, "--cpuidset", "1","000206a7","02100800","1fbae3bf","bfebfbff"] # Fix HD mounting bug

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Don't boot with headless mode
  #   vb.gui = true
  #
  #   # Use VBoxManage to customize the VM. For example to change memory:
  #   vb.customize ["modifyvm", :id, "--memory", "4096"]
  # end
  #
  # View the documentation for the provider you're using for more
  # information on available options.

  # Enable provisioning with Puppet stand alone.  Puppet manifests
  # are contained in a directory path relative to this Vagrantfile.
  # You will need to create the manifests directory and a manifest in
  # the file default.pp in the manifests_path directory.
  #
  # config.vm.provision "puppet" do |puppet|
  #   puppet.manifests_path = "manifests"
  #   puppet.manifest_file  = "default.pp"
  # end
end
