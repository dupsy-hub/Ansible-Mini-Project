# Ansible-Mini-Project
Ansible Project: Inventory Management

Overview

This repository contains an Ansible Mini Project that automates the setup and configuration of a Linux environment. The playbook performs the following tasks:

- Creates an inventory file with at least two remote hosts.

- Creates a group named devops.

- Creates users and assigns them to the devops group.

- Creates directories and files with appropriate permissions.

- Updates system packages for CentOS and Ubuntu.

- Manages the Apache (httpd) service.

- Executes Bash scripts using Ansible.

- Runs Ansible ad-hoc commands to execute scripts.
- 

Project Structure
📁 ansible-mini-project

 ├── inventory            # Ansible inventory file
 
 ├── playbook.yml         # Ansible playbook
 
 ├── scripts
 
 │ ├── copy_passwd.sh   # Bash script for copying passwd file
 
 ├── README.md            # Project documentation

 Step-by-Step Implementation

1. Create an Inventory File
Create a file named inventory and include at least two remote hosts

2. Write the Ansible Playbook

3. Create a Bash Script
Create a script named copy_passwd.sh

4. Running the Playbook:
ansible-playbook playbook.yml -i inventory

5. Run Ad-hoc Commands
Check Connectivity:
ansible all -m ping -i inventory

Ensure the script is executable by running the following command on the control node:
chmod +x copy_passwd.sh

ansible all -i inventory -m copy -a "src=copy_passwd.sh dest=/tmp/copy_passwd.sh mode=0755" 

ansible all -i inventory -m shell -a "/tmp/copy_passwd.sh" 

