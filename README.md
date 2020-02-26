# pfsense-vagrant
Contains example vagrant file and pfsense config file to bring up my vagrant virtualbox pfsense machine.

Box can be found here: https://app.vagrantup.com/ksklareski/boxes/pfsense-ce

Usernames for webconfig are admin/vagrant and vagrant/vagrant. Obviously this is not secure for production.

Vagrant file copies config.xml to the pfsense box for provisioning. Customize that file as you see fit, or create a config that you need on a running pfsense box and export it.

Sometimes the box will lock up and not be accessible via webgui or ssh. A reload seems to fix that for me.

Ensure that the number of interfaces defined in the config.xml is less than or equal to the number of interfaces defined in the vagrantfile. Otherwise the pfsense box will enter the intial config and Vagrant will be unable to provision the box.

You can create new interfaces in the vagrantfile and then configure them aftwards in the pfsense webgui.

The installed config on the box has one NAT interface and one private interface on 192.168.222.1/24.