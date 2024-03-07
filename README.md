1 ansible is setup on local machine with that we are able to handle multiple remote 
servers
2 it is an automation tool maintained by redhat python
3 
4 why need automation?
5 let consider there are 4 servers and need to install apache software setup
6 then ansible installed on local machine and write configuration to connect to 4 
severs.
7 
8 how anible works?
9 module: small program to do task eg intall nginx,upgrade,start server,create file
10 inventory: the server details stored in inventory
11 playbook : it is yaml file.to perform perticular task
12 
13 handlers in ansible
14 whenever there is chnages in firewall that time handlers run and trigger by notify
15 handlesr execute at end of programme
16 used to restart services , reload configurations
17 handlers executed when another task triggers a change
18 
19 ANSIBLE ROLES
20 
21 it is structured way of grouping together various functionalities and
22 making it easy to reuse and share common setup tasks.
23 
24 ansible-galaxy init role_name
25 ansible-galaxy init httpd-setup
26 
27 ansible galaxy
28 it is galaxy website for finding downloading sharing roles
29 
30 ansible ad hoc tasks
31 
32 ansible<host-pattern>-m<module>-a"<module arguments>"-u<username>-backup
33 ansible myserver -m command -a "df-h"
34 
35 ansible localhost -m ping
36 ansible all -m ping
37 ansible 10.211.55.9 -m copy -a "src=/home/atish/atiishfile dest=/tmp/script 
mode=0777" -b --ask-become-pass
38 ansible all -m service -a "name=nginx state=reloaded"
39 ansible all -m shell -a "/tmp/script/q12.sh"
40 ansible all -m command -a "df-h"
41 ansible all -m apt -a "name=vim state=present"
