# Quickstart guide
A more detailed documentation follows, starting from [Contents](#Contents) section.

To get things moving follow these steps:
* Install **gb-chroot** with `host` USE flag on _host_ and without it into _target_ system 
* Configure `/etc/conf.d/gb-chroot` at the _host_ and `/etc/gb-chroot.conf` at the _target_
* With `gb-install core2 amd64` you can create new chroot, named **core2** and using **amd64** stage3 (should be already downloaded) as a source
* Configure the just-created _chroot_ as required
* Use `gb-send-portage` on a _target_ to populate _chroot_ potage directories
* Use `gb-upgrade-host` to upgrade everything
* Use `gb-enter chroot_name emerge @host_name` to install all the required software in _chroot_ and build corresponding binpkgs
* Install `rsyncd` into host and configure it to serve portage tree
* Install your preferred web-server into host and configure it to serve binpkgs
* Configure _target_ systems to sync and get binpkgs from _host_
* Add `gb-update-host` into `cron` using one of the supplied templates
* At a later time use `gb-emerge anything` on _target_ to start compiling a binpkg in _chroot_ and then immediately emerge it on _target_ if succeded

# Contents
- [Quickstart guide](#quickstart-guide)
- [Contents](#contents)
- [Terminology](#terminology)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Available scripts](#available-scripts)
- [Creating chroot](#creating-chroot)
- [Managing chroot](#managing-chroot)
- [**gb-chroot** service](#gb-chroot-service)
- [Managing target](#managing-target)
- [Managing host](#managing-host)
- [Emerging packages](#emerging-packages)
- [Using ccache](#using-ccache)
- [Building Linux kernel](#building-linux-kernel)

# Terminology
**Host** is a system, that hosts all chroots. It could be a bare system, a KVM-guest.

**Target** is a system, which benefits from building `binpkgs` elsewhere. Could be a number of similar systems, sharing portage configuration.

**Chroot** is a chroot environment, created within _host_ system. It is a replica of _target_ system in a way that it has identical configuration and all the packages, that are present on a _target_. 
# Prerequisites
If you're planning to compile binpkgs for a different architecture, you might require qemu, supporting user-mode.

If your _host_ is a kvm-guest and you're plannig using qemu user-mode, you might need to enable nested virtualization.
# Installation
[gb-chroot](https://github.com/PF4Public/gentoo-overlay/tree/master/app-admin/gb-chroot) could be found in [::pf4public](https://github.com/PF4Public/gentoo-overlay/) Gentoo overlay.

**gb-chroot** should be installed with USE flag `host` into _host_ system and without it (default option) into _target_ and consequently _chroot_ systems.
# Available scripts

# Creating chroot
# Managing chroot
# **gb-chroot** service
# Managing target
# Managing host
# Emerging packages
# Using ccache
# Building Linux kernel


