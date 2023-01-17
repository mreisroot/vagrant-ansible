# Máquina Vagrant padronizada pelo Ansible

Neste projeto, há a criação de uma máquina virtual Ubuntu pelo Vagrant que é padronizada pelo Ansible.

## Preparando e executando a automação

Após a criação da máquina, há uma sequência de comandos que realizará as seguintes etapas:

1. Atualizar os repositórios do Ubuntu

2. Instalar o Ansible

3. Executar as instruções descritas no arquivo **playbook.yml** através do comando 

`ansible-playbook --connection=local playbook.yml`

## Resultados

Após a execução das instruções do playbook, o servidor terá:

1. Algumas ferramentas de administração de redes e de sistemas:

- vim

- curl

- telnet

- unzip

- wget

- net-tools

- htop

- nmap

2. Um hostname definido

3. Um usuário criado

4. O servidor web Nginx instalado, que servirá a API do site [VIACEP](https://viacep.com.br)

## Como usar este projeto

Para criar a máquina virtual Vagrant, execute o comando:

`vagrant up`

Para acessar a API servida pelo Nginx, digite na barra de pesquisa de um navegador web:

`<ip_do_servidor>/site.html`

No caso deste projeto, a pesquisa ficará assim:

`192.168.15.55/site.html`

Altere o endereço IP de acordo com a sua rede no arquivo **Vagrantfile**.
