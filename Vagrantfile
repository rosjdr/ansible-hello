Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/bionic64"
  config.vm.box_download_insecure=true

  config.vm.define "ansible" do |ansible|
    ansible.vm.network "private_network", ip: "192.168.56.50"
    ansible.vm.provision "shell", 
      inline: "apt update && \
              apt install -y software-properties-common && \
              add-apt-repository --yes --update ppa:ansible/ansible && \
              apt install -y ansible"
  end

  config.vm.define "host" do |host|
    host.vm.network "private_network", ip: "192.168.56.51"
    host.vm.provision "shell", 
      inline: "cat "
  end

end