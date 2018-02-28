# Soubirous

# Setup
There are 2 options to serve the website, [without Homestead](#setup-without-homestead) and [with Homestead](#setup-with-homestead). To learn more about Homestead and decide which one is more comfortable and appropriate for you, read [this](https://laravel.com/docs/5.6/homestead#introduction).
## Setup without Homestead
1. Install Composer. Follow [this guide](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx) if you use Linux or OSX and [this guide](https://getcomposer.org/doc/00-intro.md#installation-windows) if you use Windows.
2. Clone the repository
3. Open terminal/command line and go to the folder of the repository. Run these commands:
   ```
   composer update
   php artisan key:generate
   ```
4. To start the web server, run:
   ```
   php artisan serve
   ```
5. Done! You can access the website via your web browser:
   ```
   http://localhost:8000
   ```


## Setup with Homestead
1. Install virtual machine, choose one based on your preference [VirtualBox 5.2](https://www.virtualbox.org/wiki/Downloads), [VMWare](https://www.vmware.com/), [Parallels](https://www.parallels.com/products/desktop/) or [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v). 

   To use the VMware provider, you will need to purchase both VMware Fusion / Workstation and the [VMware Vagrant plug-in](https://www.vagrantup.com/vmware). Though it is not free, VMware can provide faster shared folder performance out of the box.

   To use the Parallels provider, you will need to install [Parallels Vagrant plug-in](https://github.com/Parallels/vagrant-parallels). It is free of charge.

2. Install [Vagrant](https://www.vagrantup.com/downloads.html).
3. Install The Homestead Vagrant Box, by running a command:
   ```
   vagrant box add laravel/homestead
   ```
   When asked about the provider, choose accordingly based on what virtual machine you have installed in #1
4. Install Composer. Follow [this guide](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx) if you use Linux or OSX and [this guide](https://getcomposer.org/doc/00-intro.md#installation-windows) if you use Windows.
5. Clone the repository
6. Open terminal/command line and go to the folder of the repository. Run these commands:
   ```
   composer update
   php artisan key:generate
   php vendor/bin/homestead make
   ```
7. To serve the website in vagrant, run:
   ```
   vagrant up
   ```
8. Done! You can access the website via your web browser:
   ```
   http://192.168.10.10
   ```
9. __*[OPTIONAL]*__ You may want to add the domain for your site to the `hosts` file in your machine to make it easier for you to access the site using a domain instead of an IP Address. The  hosts file will redirect requests for your Homestead sites into your Homestead machine. On Mac and Linux, this file is located at `/etc/hosts`. On Windows, it is located at  `C:\Windows\System32\drivers\etc\hosts`. The lines you add to this file will look like the following: 
   ```
   192.168.10.10  homestead.test
   ```
   Make sure the IP address listed is the one set in your `Homestead.yaml` file located in your root folder of the repository. Once you have added the domain to your hosts file and launched the Vagrant box you will be able to access the site via your web browser:
   ```
   http://homestead.test
   ```
