# This repository is used for installation of AWS Inspector agent 

## Run below commands to install and run awsagent
``` 
ansible-galaxy install geerlingguy.aws-inspector
```
* ### Create a file called hosts and add IP 
```
targets
127.0.0.1
```
* ### Create another file called aws.yaml
```
- hosts: all
  user: ec2-user
  become: yes
  become_method: sudo 
  roles:
    - geerlingguy.aws-inspector
```
* ### Finally run 
```
ansible-playbook -i hosts aws.yaml
```
