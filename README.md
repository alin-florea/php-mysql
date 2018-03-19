Infrastructure with Docker
   - Install Docker and Docker compose
   - create two containers with a docker:
        Apache / PHP using the ubuntu docker image: 16.04 on the Docker Hub, exposed port: 80
        Mysql using the ubuntu docker image: 16.04 on the Docker Hub, exposed port: 3306
   - Create link between the two containers
   - Create volumes for the two containers
        - apache: volume where there will be a php application / script
        - mysql: volume for mysql "data" folder
   - Deploy for a php application / script

###Ubuntu Instance. Prerequisites:
sudo usermod -a -G sudo "user"    #add user to the group sudo
sudo visudo
username ALL=(ALL) NOPASSWD: ALL  #remove password for sudo commands


apt-get update -y
apt-get upgrade -y
apt-get install openssh-server -y
apt-get install git -y
apt-get install net-tools -y
apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

apt-get install vim
apt-get install docker -y ; apt-get install docker.io -y ; apt-get install docker-compose -y ;

###Install Ansible

apt-get update
apt-get install software-properties-common
apt-add-repository ppa:ansible/ansible
apt-get install ansible

apt install python-pip
pip install --upgrade pip
pip install --upgrade setuptools
sudo pip install --ignore-installed --upgrade ansible
sudo pip install pyOpenSSL==16.2.0
apt-get install sshpass
ansible-container init (optional)

###Ansible Commands
sudo ansible all -m ping --ask-pass -vvv
sudo ansible all -m ping   -vvv
sudo ansible-playbook -i hosts lamp-playbook.yml

Ex.2:
docker-compose up --build -d
sudo netstat -lpn |grep :3306
sudo kill pid

###Configurari ansible.cfg
inventory      = /home/alin/Ansible/ansible-lamp-stack-playbook/hosts
library        = /usr/share/my_modules/
module_utils   = /usr/share/my_module_utils/
remote_port    = 22
roles_path     = /home/alin/Ansible/ansible-lamp-stack-playbook/roles
host_key_checking = False
sudo_flags = --set-home --stdin
log_path = /var/log/ansible.log
deprecation_warnings = False
