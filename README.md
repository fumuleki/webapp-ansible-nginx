# ansible-installer-serveur nginx
Cet outil a pour but d'automatiser certaines tâches sur l'installation de serveurs web(HTTP) nginx sur nos 2 nodes distant.
# Pré-requis
Vous aurez besoin d'un accès SSH sur les cibles
# Installation
    - yum update -y
    - yum install epel-release -y 
    - yum install ansible -y
# Configuration
vous devez créer l'inventaire et playbook
 - [linux]
 - 192.168.0.46
 - 192.168.0.47
 - [linux:vars]
 - ansible_user=root
 - ansible_password=root
 - créer un cluster (1 vm ansible et 2 vm clients)
 - créer un playbook format yaml.
