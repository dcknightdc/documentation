# What do I need?

- x86/x64 machine running any OS; 4G ram, SSD, quad core (recommended),
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) or similar virtualization software **(highly recommended with a minimum of 20GB hard disk space for the virtual disk image)**,
- Setting up VirtualBox and compile environment is easy following our [Vagrant tutorial](https://github.com/armbian/build/blob/master/README-Vagrant.md),
- when you don't want to build whole OS images (`KERNEL_ONLY=yes`) then [Docker](https://github.com/igorpecovnik/lib/pull/255#issuecomment-205045273), [systemd-nspawn](https://www.freedesktop.org/software/systemd/man/systemd-nspawn.html) or other containerization software can be used,
- **Only supported** compilation environment is [Ubuntu Xenial 16.04 x64](http://archive.ubuntu.com/ubuntu/dists/xenial-updates/main/installer-amd64/current/images/netboot/mini.iso) (**no other releases are supported**! It has to be exactly 16.04 otherwise default compiler versions might not match so if you're on an older Ubuntu release upgrade to 16.04 now, if you use a newer Ubuntu version start with 16.04 from scratch),
- installed basic system, OpenSSH and Samba (optional),
- superuser rights (configured `sudo` or root shell).

# How to start?

Login as root and run:

	apt-get -y -qq install git
	git clone --depth 1 https://github.com/igorpecovnik/lib
	cp lib/compile.sh .
	nano compile.sh # alter if necessary

Run the script

	./compile.sh

![](http://www.armbian.com/wp-content/uploads/2016/01/21.png)

### Supplying options via command line parameters
Instead of editing compile.sh to set options, you can set them by supplying command line parameters to compile.sh
Example:

    ./compile.sh BRANCH=next BOARD=cubietruck KERNEL_ONLY=yes PROGRESS_DISPLAY=plain RELEASE=jessie

Note: Option `BUILD_ALL` cannot be set to "yes" via command line parameter.
