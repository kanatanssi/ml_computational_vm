# Virtual Machine for ML Basic Principles/Computational UI
    OBS! Not sure how well this thing works on Windows. I use a Mac.
    TODO: Only install Opera if not already installed (keeps rolling back updates with provisioning)
## Prereqs:

    Make sure you've got the following installed before you start:
    Oracle VirtualBox,
    Vagrant,
    Ansible

From this repo you'll need Vagrantfile, playbook.yml and the roles folder (or specific ones if you only want some of them idk (like, say, you're not doing ML basic principles.))

Ps. the box takes a couple of gb of space I think. The hd for the vm probably caps at 10gb, so if you wish to use something that requires bigger than that (say, Matlab, which is an extra 3-4gb as far as I know) you'll need to do some magic to add another virtual hd to the Vagrantfile (which is unnecessarily complex. I will do this sooner or later myself.).

## Stuff installed:
    * python 2.7
    * xubuntu
    * git
    * Visual Studio Code
    * Opera browser (asks for update when you first start it) (and Firefox as a default, but it's slow af)
    * python things:
        * python-dev
        * python-numpy
        * python-scipy
        * python-matplotlib
        * python-pip
        * pylint
        * ipython
        * ipython-notebook
        * virtualenv
        * pillow
        * jupyter
    * Following course repos:
        * https://version.aalto.fi/gitlab/junga1/MLBP2017Public.git
        * https://github.com/eth-ait/ComputationalInteraction17
        * plus my own repos for the said courses because I'm lazy
## Vm specs (change in Vagrantfile if you want):
* max 10gb hd I think
* cpu 1 core
* 8192mb memory
* name: ubuntu-xenial

## Usage:
* open Terminal and navigate to the folder where you put Vagrantfile, playbook.yml and roles. Create vm with:
        ```
        vagrant up
        ```
* a bunch of text should roll in your Terminal window. Wait for it to stop, then reboot the vm with:
        ```
        vagrant reload
        ```
* **probably** (like 100%) you will then need to change the password for the user ubuntu. Ssh to your machine with:
        ```
        vagrant ssh
        ```
* on the virtual machine, change the password with:
        ```
        sudo passwd ubuntu
        ```
* open virtualbox management panel (on local). Rightclick ubuntu-xenial machine. Choose "show"

* log in to vm via gui :)

* open terminal (rightclick on desktop, choose "open terminal"), run jupyter with:
        ```
        jupyter-notebook
        ```
* computational us / malbp course repos should be downloaded under Desktop/code

## Stuff you might want to do:
* change keyboard layout (click icon in left corner, select settings -> keyboard -> layout tab)
* run ssh-keygen, add your ssh key to your github account
