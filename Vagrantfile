HOSTNAME = "ubuntu-xenial"
IP = "192.186.155.155"
# The size of the VM will be this + the 10gb that the Ubuntu box requires
DISKSIZE = "30" # + 10 gb

disk = './seconddisk.vdi'

$script = <<SCRIPT
echo "Install python"
sudo apt-get install python -y

#echo "Update sources"
#sudo apt-get update

#echo "Install gui"
#sudo apt-get install xubuntu-desktop -y 
SCRIPT

Vagrant.configure(2) do |config|

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  config.ssh.forward_agent = true

  config.vm.define "ubuntu-xenial" do |ubuntuxenial|
    ubuntuxenial.vm.box = "ubuntu/xenial64"
    ubuntuxenial.vm.network :private_network, ip: "#{IP}"
    ubuntuxenial.vm.hostname = "#{HOSTNAME}"
    #ubuntuxenial.vm.network "forwarded_port", guest: 8080, host: 8080

    ubuntuxenial.vm.provider :virtualbox do |vb|
#      vb.memory = 2048
      vb.memory = 4096
      vb.cpus = 1
      vb.name = "ubuntu-xenial"
#    end
#  end

# add seconddisk.vdi to give the box additional disk space.
#    if ! File.exist?(disk)
#      vb.customize ['createhd', '--filename', disk, '--variant', 'Standard', '--size', 110 * 1024]
#      vb.customize ['storageattach', "ubuntu-xenial",  '--storagectl', 'IDE', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', disk] #controller could be "SATA Controller", but showvminfo states the storage controller to be IDE
#    end
#  end
#  
#    if ! File.exist?(disk)
#      ubuntuxenial.vm.provision :shell, path: "bootstrap.sh"
#    end
# additional disk space stuff ends

  # Run above script
  config.vm.provision "shell", inline: $script

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = "vv"
  
  end
end