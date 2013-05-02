# LAMP stack setup based on CentOS 6.3 with Vagrant / Puppet

This installs:

- Apache
- MySQL
- PHP
- phpMyAdmin

## Installation

1. Install VirtualBox

	Download from [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads). Remember to download the VirtualBox Extension Pack.

2. Install Vagrant
	
	Download from [http://downloads.vagrantup.com](http://downloads.vagrantup.com/).

3. Clone this repo into a local folder

	```bash
$ git clone git@github.com:TempleStudiosInc/TS_Vagrant_LAMP.git phpdev
```

4. Start Vagrant

	`cd` into the checked out folder to start the VM:

	```bash
$ vagrant up
```

## Usage

Update your host operating system's hosts file with the following entry:

```bash
192.168.56.60 phpdev.local
```

In windows, the file is located at:

```bash
C:/Windows/System32/Drivers/etc/hosts
```

In Linux, the file is located at:

```bash
/etc/hosts
```

Now, you can reach the webroot with `http://phpdev.local` or `http://localhost:8080`.

To login into the VM type
```bash
$ vagrant ssh
```

To stop the VM:
```bash
$ vagrant suspend
```

To halt the VM:
```bash
$ vagrant halt
```

To destroy the VM:
```bash
$ vagrant destroy
```

The phpMyAdmin URL: `http://phpdev.local/phpmyadmin` or `http://localhost:8080/phpmyadmin`.

***Note:*** The MySQL username is `root` and the root password is `password`. To change the default, edit `manifests/db.pp`.


Based on the excellent work from [Michael Cheng](https://github.com/miccheng/vagrant-lamp-centos63/).