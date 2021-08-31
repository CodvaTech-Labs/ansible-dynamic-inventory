# ansible-dynamic-inventory
ansible-dynamic-inventory

[root@ip-172-31-15-249 ansible]# ansible-inventory --graph -i /etc/ansible/aws_ec2.yaml
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
