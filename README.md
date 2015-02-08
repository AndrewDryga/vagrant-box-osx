Mac OS X Vagrant box for VirtualBox
=========================
This is a issue tracker for OS X Vagrant boxes, which can be found in Download section

Box was tested only on VirtualBox with Mac OS as a host. Mainly, I made it to build our iOS applications via CI-server.

Downloads
--
Since VagrantCloud can't host this images, you can use direct links to download them. Download speed may be slow.

* Mac OS X Maverics 10.9 (XCode 5.1): [v0.1.0, direct link](http://files.dryga.com/boxes/osx-mavericks-0.1.0.box)
* Mas OS X Yosemite 10.10 (XCode 6.1): [v0.2.0, direct link ](http://files.dryga.com/boxes/osx-yosemite-0.2.0.box)

Setting up
--
1. Install [Vagrant](https://docs.vagrantup.com/v2/installation/) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads);
2. ```cd``` into your project directory;
3. Run ```vagrant init http://files.dryga.com/boxes/osx-yosemite-0.2.0.box```;
4. Your Vagrantfile should be ready as soon as Vagrant downloads box;
5. Start VM by calling ```vagrant up```.

Warning
--
VirtualBox support for Mac OS X is experimental. More information can be found in [official docs](https://www.virtualbox.org/manual/ch03.html#intro-macosxguests).

What's included?
--
* [Homebrew](http://brew.sh/)
* [Homebrew Cask](https://github.com/phinze/homebrew-cask)
* Puppet
* XCode 5.1/6.1
* XCode Command Line Tools

How to accept the Xcode License from the CLI
--

This step can be skipped if you have already accepted the Xcode license or
installed an unmolested version of `git`/etc..

If you see a warning like the following:

```shell
$ git


Agreeing to the Xcode/iOS license requires admin privileges, please re-run as root via sudo.
```

Run this command:
```shell
sudo xcodebuild -license accept
```

Then verify that the license warning is gone:
```shell
# sanity check
$ git --version
git version 1.8.5.2 (Apple Git-48)
```

Known issues
--
* Do not turn 3D acceleration on, or your Box will start retuning aborted condition and would not start in headless mode
* VirtualBox doen's have Guest additions for Mac OS X, so you can't have shared folders. Instead you can use normal network shared folders
* Apple's EULA states that you can install your copy on your actual Apple-hardware, plus up to two VMs running on your Apple-hardware. So using this box on another hardware is may be illigal
* If you face VM freezed on message ```hfs mounted macintosh hd on device root_device``` then you need to set cpuidset inside your Vagrantfile: ```vb.customize ["modifyvm", :id, "--cpuidset", "1","000206a7","02100800","1fbae3bf","bfebfbff"]```

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
