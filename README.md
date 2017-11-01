# Virtual Machine for ML Basic Principles/Computational UI
## Prereqs:
´´´
OBS! Not sure how well this thing works on Windows. I use a Mac.
´´´

Make sure you've got the following installed before you start:
´´´
Oracle VirtualBox
Vagrant
Ansible
´´´

From this repo you'll need Vagrantfile, playbook.yml and the roles folder (or specific ones if you only want some of them idk (like, say, you're not doing ML basic principles.))

Also, in order to ssh and pull/commit to git you'll need to have ssh keys added to a github account
´´´
OBS! the box uses ssh key forwarding during provisioning at least, not sure if the ssh agent persists after provisioning, could be you need to add your boxes ssh key to your github account
´´´
Ps. the box takes a couple of gigabytes of space I think. The hd for the vm probably caps at 10gb, so if you wish to use something bigger than that (say, Matlab, which is 11gb as far as I know, you'll need to do some magic to add another virtual hd to the Vagrantfile, which is unnecessarily complex. I will do this sooner or later myself.).

## Usage:

- open Terminal and navigate to the folder where you put Vagrantfile, playbook.yml and roles

- vagrant up

- a bunch of text should roll in your Terminal window and eventually a gui for the virtual machine should open

-- If the previous fails, then there could be something wrong with your installation of VirtualBox or Vagrant, you might be experiencing connection issues or it might just be a random fail! Try again with vagrant up --provision just to be sure :)
-- also you might be unable to log in with the default ubuntu user with the default password "password"
-- to change the password, ssh into your newly created ubuntu virtual machine with: vagrant ssh
