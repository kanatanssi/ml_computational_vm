# Virtual Machine for ML Basic Principles/Computational UI
## Prereqs:

    OBS! Not sure how well this thing works on Windows. I use a Mac.

Make sure you've got the following installed before you start:
    Oracle VirtualBox,
    Vagrant,
    Ansible

From this repo you'll need Vagrantfile, playbook.yml and the roles folder (or specific ones if you only want some of them idk (like, say, you're not doing ML basic principles.))

    TODO: Only install Opera if not already installed (keeps rolling back updates with provisioning)

Ps. the box takes a couple of gb of space I think. The hd for the vm probably caps at 10gb, so if you wish to use something bigger than that (say, Matlab, which is 11gb as far as I know, you'll need to do some magic to add another virtual hd to the Vagrantfile, which is unnecessarily complex. I will do this sooner or later myself.).

## Usage:

* open Terminal and navigate to the folder where you put Vagrantfile, playbook.yml and roles

* vagrant up

* a bunch of text should roll in your Terminal window. Wait for it to stop

* type "vagrant reload" to reboot the virtual machine

* **probably** (like 100%) you will then need to change the password for the user ubuntu. The default seems to be something weird

* type "vagrant ssh" to ssh into your machine

* in the virtual machine, type "sudo passwd ubuntu"

* enter a new password (whatever you like)

* open virtualbox management panel. Rightclick ubuntu-xenial machine. Choose "show"

* log in via gui :)

* open terminal (rightclick on desktop, choose "open terminal"), run "jupyter-notebook", computational us / malbp course repos should be downloaded under Desktop/code

    Stuff you might want to do:
    * change keyboard layout (click icon in left corner, select settings -> keyboard -> layout tab)
    * run ssh-keygen, add your ssh key to your github account
