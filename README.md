# Roadmap
Welcome to my DevOps learning roadmap! This document chronicles my exploration and growth in the world of DevOps, a field that bridges the gap between software development and IT operations. In this roadmap, I aim to outline the key milestones I've reached, the tools and technologies I've learned, and the challenges I've faced along the way. From understanding the fundamentals of Continuous Integration and Continuous Deployment (CI/CD) to mastering cloud services and container orchestration, each step has brought me closer to becoming a proficient DevOps engineer. Join me as I document my progress, share valuable resources, and reflect on my experiences. I hope this roadmap serves not only as a personal guide but also as an inspiration for others embarking on a similar journey.

## Operating System (Ubuntu)

## Programming Language (Python)

## Scripting (Bash Scripts)

## Version Control Systems
### Git
#### Installation
`sudo apt install git`

#### Walkthrough
Note : to continue this tuto, you need to have an account in a VCS hosting like GITHUB (refer to the GITHUB section for more details)
1. Init the repo
`git init`
2. Config git (so when you commit git complains)
```
git config --global user.name ""
git config --global user.email ""
```
3. To check the current status of your local repo version
`git status`    
4. To see the changes 
`git diff changed_file_name`
5. To stage the changed file
`git add changed_file_name` if you run git status again
6. Stage the changes
`git commit -m "comment"`
7. Push the changes to the remote server
`git push origin master`

## VCS Hosting (Github)

## Services
### Nginx
Nginx is an HTTP web server, reverse proxy, content cache, load balancer, TCP/UDP proxy server, and mail proxy server. Originally written by Igor Sysoev and distributed under the 2-clause BSD License.
1. Installation using docker
```
sudo docker pull nginx
sudo docker run --name nginxserver -p 80:80 -d nginx
```
2. Installation using docker compose
TODO


## Networking (HTTP, HTTPS, SSL/TLS, SSH, DNS)

## Containers (Docker)

## Configuration Management
### Ansible

#### Defintion
Ansible automates the management of remote systems and controls their desired state. Ansible provides open-source automation that reduces complexity and runs everywhere. Using Ansible lets you automate virtually any task. Ansible environments have three main components:
- Control node : A system on which Ansible is installed. You run Ansible commands such as ansible or ansible-inventory on a control node.
- Inventory : A list of managed nodes that are logically organized. You create an inventory on the control node to describe host deployments to Ansible.
- Managed node : A remote system, or host, that Ansible controls.
Here are some common use cases for Ansible:
- Eliminate repetition and simplify workflows
- Manage and maintain system configuration
- Continuously deploy complex software
- Perform zero-downtime rolling updates

#### Installation
1. Install ansible on system (Ubuntu):
`apt install ansible`
2. Install ansible using pip
`pip install ansible`

#### Setting up SSH
1. Connect to each slave node from the controller node, answer "yes" to initial connection prompt
`ssh user@ip-address` yes and then put the password
2. In the controller node, create an SSH key pair (with a passphrase) for a normal user account
`ssh-keygen -t ed25519 -C "Default"`
3. In the controller node, create an SSH key pair (without passphrase) that is specific to Ansible
`ssh-keygen -t ed25519 -C "Ansible"`
4. Copy both public keys to each slave node
`ssh-copy-id -i ~/.ssh/key_name.pub ip-address` and then put the password

#### SSH Agent Cheat
1. Get the process that cache the passphrase
`eval $(ssh-agent)`
2. Verify the deamon
`ps aux | grep pid`
3. To escape the passphrase verification 
`ssh-add`
4. To make this permanent
`alias ssha='eval $(ssh-agent) && ssh-add`
5. Or even more ..., ny adding this alias to the .bashrc file.

## Provisioning (Terraform)

## CI/CD (Jenkins)

## Orchestration (Kubernetes)

## Cloud provider (AWS)

## Logs Management (ELK) 

## App Monitoring (Prometheus)

## Infrastructure Monitoring (Grafana)
