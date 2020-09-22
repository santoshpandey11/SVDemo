### CICD on kubernestes cluster

### Solution Implementation
## Infrastructure for kubernetes
spin up VM with centos with At least 8 GB of RAM and 15 GB of free hard disk space for the virtual machines. ensure port 22, 8080 and 8080 is available for traffic
Software Installations and commands:
update  hosts: PIP in file setup-Git-Jenkin-Docker-Vargrant-Vbox.yaml
Run below command on host: 
- yum install  wget ;
- yum install curl ;
- yum install ansible;
- sh setup-Git-Jenkin-Docker-Vargrant-Vbox.yaml
 thescript setup-Git-Jenkin-Docker-Vargrant-Vbox.yaml will install:
-Vagrant 2.2.6
-VirtualBox 6.1.6 
-Python
-git
-jenkins

configure virtual machine to start automatically
define below variables at /etc/default/virtualbox
 VBOXAUTOSTART_DB=/etc/vbox
 VBOXAUTOSTART_CONFIG=/etc/vbox/vbox.cfg
 content of vbox.cfg:
 # Default policy is to deny starting a VM, the other option is "allow".
 default_policy = deny
 # Create an entry for each user allowed to run autostart
 myuserid = {
 allow = true
 }
- restart VM


cd ansible-vbox-vagrant-kubernetes
command- vagrant up 
This command spins up  2 slave node with a single master
K8S-M-1 at eth1: 192.168.50.11
K8S-N-1 at eth1: 192.168.50.12
K8S-N-2 at eth1: 192.168.50.13
vboxnet0 virtual iface: 192.168.50.1

Application available at http://<IP host>/80


