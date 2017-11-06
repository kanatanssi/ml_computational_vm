# Virtual Machine for ML Basic Principles/Computational UI
## Prereqs:

    OBS! Not sure how well this thing works on Windows. I use a Mac.

Make sure you've got the following installed before you start:
    Oracle VirtualBox,
    Vagrant,
    Ansible

From this repo you'll need Vagrantfile, playbook.yml and the roles folder (or specific ones if you only want some of them idk (like, say, you're not doing ML basic principles.))

    TODO: download and install:
    * Anaconda or scipy

Ps. the box takes a couple of gb of space I think. The hd for the vm probably caps at 10gb, so if you wish to use something bigger than that (say, Matlab, which is 11gb as far as I know, you'll need to do some magic to add another virtual hd to the Vagrantfile, which is unnecessarily complex. I will do this sooner or later myself.).

## Usage:

* open Terminal and navigate to the folder where you put Vagrantfile, playbook.yml and roles

* vagrant up

* a bunch of text should roll in your Terminal window and eventually a gui for the virtual machine should open

* if no GUI, then type "vagrant reload" to reboot the virtual machine.

* probably you will then need to change the password for the user ubuntu. The default seems to be something

* type "vagrant ssh" to ssh into your machine

* in the virtual machine, type "sudo passwd ubuntu"

* enter a new password (whatever you like, even blank is kinda okay)

* log in via gui :)

If the previous fails, then there could be something wrong with your installation of VirtualBox or Vagrant, you might be experiencing connection issues or it might just be a random fail! Try again with vagrant up --provision just to be sure :)

If the GUI does not show up, head to the VirtualBox management window, right click the "ubuntu-xenial" box and select "Show".
