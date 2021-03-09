# ansible-installer-serveur nginx
Ansible est un outil d'automatisation informatique. Il peut configurer des systèmes, déployer des logiciels et orchestrer des tâches informatiques plus avancées telles que des déploiements continus ou des mises à jour progressives sans temps d'arrêt. Ansible gère les machines sans agent. Il n'est jamais question de savoir comment mettre à niveau les démons distants ou de ne pas pouvoir gérer les systèmes parce que les démons sont désinstallés.

Cet outil a pour but d'automatiser certaines tâches pour l'installation de serveurs web(HTTP) nginx sur nos 2 serveurs distant.
# Pré-requis
    - 3 vm Centos8: 1 vm master ansible et 2 vm clients
    - Vous aurez besoin d'un accès SSH sur les cibles
OpenSSH est l'un des composants open source les plus évalués par les pairs, l'exposition à la sécurité est considérablement réduite.
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
 - créez un playbook format yaml.
Ansible playbooks sont écrits en utilisant le langage yaml donc créez un fichier .yml ou une extension yaml
 - vi nginx-install.yml
Les fichiers yaml commencent éventuellement par trois tirets (---)
La prochaine ligne immédiate commence par un seul tiret (-),Le nom est facultatif ici, les hosts attendent une valeur comme all ou group.

   - (-)name: nginx install & start services
   - hosts: all
  
Voulez-vous devenir un utilisateur root sur le serveur target become 
  - become: true

quelle action souhaitez-vous effectuer? spécifiez sous les tâches que nous utilisons ce playbook pour installer nginx
quel est le module pour installer nginx
  - tasks:
  - name: install nginx
  - yum:
  - name: nginx
  - state: latest
  - service:
  - name: nginx
  - start: started
  - 

