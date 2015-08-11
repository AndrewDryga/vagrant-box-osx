# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # Use box from Atlas
  config.vm.box = "AndrewDryga/vagrant-box-osx"

  # Use box from url (if Atlas is down)
  # config.vm.box = "http://files.dryga.com/boxes/osx-yosemite-0.2.1.box"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended when using box from Atlas.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP. This is required to create NFS shared folder.
  # config.vm.network "private_network", ip: "192.168.99.33"

  # Share an additional folder to the guest VM via Network Shared Folder.
  # You can find it at ```/vagrant``` on guest VM.
  # config.vm.synced_folder ".", "/vagrant",
  #   id: "vagrant-root",
  #   :nfs => true,
  #   :mount_options => ['nolock,vers=3,udp,noatime']

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine. You might want to turn 3D accelerating to speed-up VM GUI.
    # vb.gui = true

    # Customize the amount of memory on the VM:
    # vb.memory = "4096"

    # Customize motherboard chipset
    # vb.customize ["modifyvm", :id, "--chipset", "ich9"]

    # Customize NAT DNS
    # v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    # v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end

  # Enable provisioning with a shell script.
  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo chown -R vagrant:admin /Library/Caches/Homebrew
  #   brew update
  #   npm update
  #   echo 'vagrant' | brew cask update
  #   sudo /usr/sbin/DevToolsSecurity --enable
  # SHELL

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
