# ansible

## Inventory is file to provide all hosts/nodes
Ansible default install 2.9 version on AMI's we weill get python2
Always go with latest version, which can be installed from tools/ansible/install.sh

#ansible -i inv all  --list-hosts --> to list all hosts

# ANSIBLE PREDEFINED VARIABLES

# ansible_user 
#ansible_password 

Variable should be passed to ansible by using the flag -e

e.g. ansible -i Inv all -e ansible_user=username -e ansible_pass=pswd
1000's of module available : -m shell, -m yum, -m service

##### Ansible can be executed in 2 ways:
1. Manual Approach : ansible command
2. Automated Approach : ansible playbook

## Automated approcah : This uses playbook
Paybook are written in YAML
