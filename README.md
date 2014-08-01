Mac OS X Mavericks Vagrant box for VirtualBox
=========================
This is a issue tracker for OS X Mavericks Vagrant box, which can be found on [direct link](http://files.dryga.com/boxes/osx-mavericks-0.1.0.box)(it might be slow). (VagrantCloud refused to host this package.)

Box was tested only on VirtualBox. Mainly, I made it to build our iOS applications via CI-server.

Hosting issues
--
I can't host this image on VagrantCloud anymore, since Apple didn't let them to distribute VMs with their softare, you can use direct link to the box instead.

Warning
--
VirtualBox support for Mac OS X is experimental. More information can be found in [official docs](https://www.virtualbox.org/manual/ch03.html#intro-macosxguests).

What's included?
--
* [Homebrew](http://brew.sh/)
* [Homebrew Cask](https://github.com/phinze/homebrew-cask)
* Puppet (without puppetmaster)
* XCode 5.1
* XCode Command Line Tools

Known issues
--
* Do not turn 3D acceleration on, or your Box will start retuning aborted condition and would not not start in headless mode
* VirtualBox doen's have Guest additions for Mac OS X, so you can't have shared folders. Instead you can use normal network shared folders
* Apple's EULA states that you can install your copy on your actual Apple-hardware, plus up to two VMs running on your Apple-hardware. So using this box on another hardware is may be illigal

Tips to build you'r own box
--
Main think you should remember is that you need latest VirtualBox version BEFORE you start installation. Process of installation is pretty straight forward (as on usual Mac), but you need to erase virtual drive during installation via Disk Utilities. After that just follow [Vagrant guide](https://docs.vagrantup.com/v2/boxes/base.html) to create base box and [another one](https://docs.vagrantup.com/v2/virtualbox/boxes.html) to package it.

Sometimes you need to [rebuild VirtualBox kernel extensions](https://gist.github.com/AndrewDryga/9880938) before installing OS on VM.

Helpful links (most of them are outdated):
--
- [Script to create Mac OS installer image](http://ntk.me/2013/12/01/iesd/)
- [Templates to create Host](https://github.com/timsutton/osx-vm-templates)
- [And guide to use it](http://grahamgilbert.com/blog/2013/08/23/creating-an-os-x-base-box-for-vagrant-with-packer/)
- [Another guide by Lifehacker](http://lifehacker.com/5583650/run-mac-os-x-in-virtualbox-on-windows/all)
- [Legal question](http://www.tomshardware.co.uk/answers/id-1802838/illegal-run-osx-virtual-box.html)
- [How to disable default mounting of shared folder](https://github.com/mitchellh/vagrant/issues/1004)
