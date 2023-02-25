Vagrant.configure("2") do |config|

  # Definir provider e alocar recursos
  config.vm.provider "virtualbox" do |v|
    v.name = "vagrant_ansible"
    v.cpus = 1
    v.memory = 1024
    v.gui = false
  end

  # Definir hostname, SO e rede
  config.vm.hostname = "ubuntu"
  config.vm.box = "ubuntu/jammy64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "private_network", ip: "192.168.56.11"

  # Compartilhando a pasta que contém o playbook e as roles do Ansible
  config.vm.synced_folder "./ansible", "/ansible"

  # Instalar o Ansible
  config.vm.provision "shell", path: "provision.sh"

  # Instalando e executando o Ansible na VM
  config.vm.provision "ansible_local" do |ansible|
    ansible.provisioning_path = "/ansible"
    ansible.playbook = "playbook.yml"
  end

end
