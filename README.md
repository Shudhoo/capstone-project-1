
# Capstone Project - 1 

This is my Capstone Project 1, which covers a couple of DevOps tools and their integration with Jenkins, known as an automation server. In this project, I configured my Jenkins Master and Jenkins Slave using Ansible. I cloned a repository from GitHub and created my own branches. After installing Jenkins, I connected the nodes with the Jenkins Master to establish communication between them, allowing specific jobs to run on specific nodes. For example, a push to the develop branch will test the code on the test-server node, and a push to the master branch will test the code and deploy it to the prod-server node to serve end users.

## Flow Diagram
![image alt](https://github.com/Shudhoo/capstone-project-1/blob/7e8cad96a75f3f43897ad17e150d7da00f246d0c/t.png)

## Prerequisites

* To have an AWS Account
* AWS IAM User created with minimal permissions required

### Commands to Install Ansible on Jenkins-Master

```bash
 sudo apt update && sudo apt upgrade -y
sudo apt install software-properties-common

sudo add-apt-repository --yes --update ppa:ansible/ansible

#Install Ansible
sudo apt install ansible -y

#Validate Ansible:
ansible –-version
```
#### After installing Ansible, create the myinv file inside the Ansible location and create a playbook just like I have created in the above repository. After that, run the Playbook with the following command.
```bash
ansible-playbook Playbook -i /etc/ansible/myinv --user <username> --ask-pass
```
#### This will configure software like Java & Docker on the Jenkins-Slave.

## Reference

 - [End-to-End Documentation of Project](https://drive.google.com/file/d/1OptGZCrvH9tAtH8h3GzOQ3XfNxWHvXDw/view?usp=sharing)
