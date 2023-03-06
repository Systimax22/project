# project
 Проектная работа


Отказоустойчивый кластер для Wordpress.

 Состав кластера:

Haproxy + keepalived
194.58.88.133

Nginx + php 
192.168.10.50
192.168.10.60

Mysql galera cluster + haproxy

192.168.10.30
192.168.10.40

Backup server - 192.168.10.100


Все виртуальные машины развернуты в Proxmox, для доступа к серверам поднят OpenVPN сервер.


Для развертывания кластера, необходимо 7 виртуальных машин.

После копирования ключа, выполняется 

ansible-playbook -i inventory software_install.yml
