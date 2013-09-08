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
<mymachine>$ git clone https://github.com/rogeriopradoj/tuto-vagrant-composer-symfony2 ~/tuto-vagrant-composer-symfony2
<mymachine>$ cd ~/tuto-vagrant-composer-symfony2/vagrant
<mymachine>$ vagrant plugin bundle
    # with this you ensure that all plugins needed by Vagrant are installed
<mymachine>$ vagrant up
<mymachine>$ vagrant ssh
    # now you're inside the VM

<vm>$ cd /var/www/
<vm>$ composer install
    # answer the database_password with `root`,
    # other questions you can just hit enter

<vm>$ exit
    # now you're back to your machine
```

After that all is ready to be tested via your prefered browser, at this address: [http://symfony2.localhost]()

### Prefer a Asciicast?


<script type="text/javascript" src="http://ascii.io/a/5349.js" id="asciicast-5349" async></script>

Ascii.io: [http://ascii.io/a/5349](http://ascii.io/a/5349).

I've tried, now I want to clean this mess up
--------------------------------------------

Ok, we know that we are using VM in order to don't mess our own system, right?
So, after you tried everything, why not just clean the mess? Let's go:

```bash
<mymachine>$ cd ~/tuto-vagrant-composer-symfony2/vagrant
<mymachine>$ vagrant destroy
    # now your VM has gone away
<mymachine>$ cd ~
<mymachine>$ rm -rf ~/tuto-vagrant-composer-symfony2
    # and now the cloned files has gone too
```

That's it!

See ya!

[@rogeriopradoj](https://github.com/rogeriopradoj)
