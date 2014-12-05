Sasstellite
==============

A sass setup for templates in the Constellation Satellite system.

Getting up and running
----------------------

The steps below will set up a local development environment with compass to watch and compile sass files.

Without Virtual Server
----------------------

Create a new directory to work in.

if git is not installed install it now.

  $sudo apt-get install -y git

Clone the github repo

  $ git clone https://github.com/dekanbro/sasstellite.git

If compass and sass are not installed install them now

  $ sudo gem install compass
  
  $ sudo gem install sass

Now start up compass.

  $ compass watch

You are now ready to edit the files in the sass folder the will automatically be compiled into css in the css folder.


Using Virtual Server
--------------------

First you will need the following installed.

*VirtualBox_
*Vagrant_

.. _VirtualBox: https://www.virtualbox.org/
.. _Vagrant: https://www.vagrantup.com/

Create a new directory to work in.

In this directory create another directory called Projects. Now run the command

  $ vagrant init hashicorp/precise32

This will create a new file call Vagrantfile. Set a folder that will be shared on your local machine and the server. This will allow you too use your favorite editor and file manager. Edit this file with a new line after config.vm.box

  config.vm.synced_folder "Projects/", "/home/vagrant/Projects"

You are now ready to start your new virtual server. From the current directory type.

  $ vagrant up

This will tack a few minutes to run. Now type:

  $ vagrant ssh

From this new prompt cd into Projects and download the sasstellite github repo. First install git.

  $ sudo apt-get install -y git

  $ git clone https://github.com/dekanbro/sasstellite.git

This will download the repo into a sasstellite folder.

Now we need to install compass to watch and compile these files.

  $ sudo gem install compass
  
  $ sudo gem install sass

Now start up compass.

  $ compass watch

You are now ready to edit the files in the sass folder the will automatically be compiled into css in the css folder. THe files will be accessible from the Projects folder on your local machine.
