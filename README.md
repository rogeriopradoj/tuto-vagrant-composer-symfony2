Tutorial - Configure a virtual machine for Symfony with Vagrant
===============================================================

Folowing the tutorial from [Screenfony](https://www.youtube.com/user/screenfony) at
[https://www.youtube.com/watch?v=LfUubn4PrlI](https://www.youtube.com/watch?v=LfUubn4PrlI).

![screenfony logo](http://www.screenfony.com/wp-content/uploads/2012/04/logo1.png "screenfony logo")

They teach how to use [Vagrant](http://www.vagrantup.com/) to configure a VM
for [Symfony](http://symfony.com/) installed via [Composer](http://getcomposer.org/).

![vagrant logo](http://www.vagrantup.com/images/logo_vagrant-81478652.png "vagrant logo") + ![composer logo](http://getcomposer.org/img/logo-composer-transparent.png "composer logo") = ![symfony logo](http://symfony.com/images/common/logo/logo_symfony_header.png "symfony logo")

Important
---------

Some things were changed from the original tutorial:

- I've moved all my vagrant related files into vagrant folder, even
  Vagrantfile. Wherefore, synced folder config is a little different.
- I'm using [fgrehm/bindler](https://github.com/fgrehm/bindler) to manage
  plugins used in Vagrantfile. So, install bindler before trying to use
  this Vagrantfile
- I've changed the hostname to `symfony101.localhost`. This way, with the
  help of the plugin [smdahlen/vagrant-hostmanager](https://github.com/smdahlen/vagrant-hostmanager),
  Vagrant include the hostname automatically in both /etc/hosts (VM and
  my machine).
- Even after successfully boot, my browser was always getting the `default
  apache vhost` response, instead of `symfony101.localhost`. So, I disabled
  the default vhost, and, after all, everything worked fine.

Wanna try?
----------

So, if you wanna try, do the following:

```bash
$ git clone https://github.com/rogeriopradoj/tuto-vagrant-composer-symfony2 ~/tuto-vagrant-composer-symfony2
$ cd ~/tuto-vagrant-composer-symfony2
$ composer install
$ vagrant up
```

That's it!

See ya!

[@rogeriopradoj](https://github.com/rogeriopradoj)
