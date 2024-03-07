ansible is setup on local machine with that we are able to handle multiple remote servers.it is an automation tool maintained by redhat python 
why need automation?
let consider there are 4 servers and need to install apache software setup then ansible installed on local machine and write configuration to connect to 4 severs.
 
module: small program to do task eg intall nginx,upgrade,start server,create file
inventory: the server details stored in inventory
playbook : it is yaml file.to perform perticular task

handlers in ansible
whenever there is chnages in firewall that time handlers run and trigger by notify
handlesr execute at end of programme
used to restart services , reload configurations
handlers executed when another task triggers a change
 
ANSIBLE ROLES
it is structured way of grouping together various functionalities and making it easy to reuse and share common setup tasks.

ansible-galaxy init role_name
ansible-galaxy init httpd-setup

ansible galaxy -->it is galaxy website for finding downloading sharing roles 
ansible ad hoc tasks
ansible<host-pattern>-m<module>-a"<module arguments>"-u<username>-backup
ansible myserver -m command -a "df-h"
ansible localhost -m ping
ansible all -m ping
ansible 10.211.55.9 -m copy -a "src=/home/atish/atiishfile dest=/tmp/script 
mode=0777" -b --ask-become-pass
ansible all -m service -a "name=nginx state=reloaded"
ansible all -m shell -a "/tmp/script/q12.sh"
ansible all -m command -a "df-h"
ansible all -m apt -a "name=vim state=present"
