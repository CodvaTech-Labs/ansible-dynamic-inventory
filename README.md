# Ansible Dynamic Inventory
## Refer below steps if you want to rub ansible playbook on dynamic inventory

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Features
- Dynamic Inventory
- Target inventory as per tages

## Ref Link
- https://medium.com/xebia-engineering/automating-ansible-dynamic-inventory-with-jenkins-on-aws-26dfc4147887
- https://devopscube.com/setup-ansible-aws-dynamic-inventory/


ansible-inventory command will return all ec2 instances in AWS Console

```sh
[root@ip-172-31-15-249 ec2-user]# ansible-inventory --graph -i /etc/ansible/aws_ec2.yaml
@all:
  |--@aws_ec2:
  |  |--ec2-15-206-88-239.ap-south-1.compute.amazonaws.com
  |  |--ec2-35-154-226-152.ap-south-1.compute.amazonaws.com
  |  |--ec2-35-154-234-63.ap-south-1.compute.amazonaws.com
  |--@tag_Name_Jenkins_Server:
  |  |--ec2-35-154-226-152.ap-south-1.compute.amazonaws.com
  |--@tag_Name_demo_ansible:
  |  |--ec2-15-206-88-239.ap-south-1.compute.amazonaws.com
  |--@tag_Name_tomcat_node:
  |  |--ec2-35-154-234-63.ap-south-1.compute.amazonaws.com
  |--@tag_appname_cicidemo:
  |  |--ec2-35-154-234-63.ap-south-1.compute.amazonaws.com
  |--@tag_env_prod:
  |  |--ec2-35-154-234-63.ap-south-1.compute.amazonaws.com
  |--@ungrouped:
[root@ip-172-31-15-249 ec2-user]# 
```


ansible all -m command will ping all connected target IPs

```sh
[root@ip-172-31-15-249 ansible]# ansible all -m ping -i /etc/ansible/aws_ec2.yaml
```

We can use tags if we want to targt only specific IPs as below 

```sh

[root@ip-172-31-15-249 ansible]# ansible tag_appname_cicidemo -m ping -i /etc/ansible/aws_ec2.yaml

```

Ansible Playbook execution as per tags on AWS EC2 instances
```sh

#Ansible playbook - Run parameter
ansible-playbook demo.yml -i /etc/ansible/aws_ec2.yaml -e "host_name=tag_Name_Dashboard_Dev"

```




