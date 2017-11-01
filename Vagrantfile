HOSTNAME = "ubuntu-xenial"
IP = "192.186.155.155"


$script = <<SCRIPT
# Uh. Run once. Then spoon feed the above commands
# These are old. Ignore

echo "Install python"
sudo apt-get install python -y

#echo "Update sources"
#sudo apt-get update

#echo "Install gui"
#sudo apt-get install xubuntu-desktop -y 
SCRIPT

Vagrant.configure(2) do |config|

  config.vm.define "ubuntu-xenial" do |ubuntuxenial|
    ubuntuxenial.vm.box = "ubuntu/xenial64"
    ubuntuxenial.vm.network :private_network, ip: "#{IP}"
    ubuntuxenial.vm.hostname = "ubuntu-xenial"
    #crossbow.vm.network "forwarded_port", guest: 8080, host: 8080

    ubuntuxenial.vm.provider :virtualbox do |vb|
      vb.memory = 2048
      vb.cpus = 1
      vb.name = "ubuntu-xenial_2"
    end
  end

  # Run above script
  config.vm.provision "shell", inline: $script

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  
  end
end