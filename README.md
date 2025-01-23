# Ansible

Ansible is an open-source IT automation tool that helps in configuration management, application deployment, and task automation. It allows you to manage multiple servers without requiring manual intervention.

## Common Use Cases:

Server Configuration: Install and configure Apache, MySQL, PHP, etc.
Software Deployment: Automate application deployments on multiple servers.
Infrastructure as Code (IaC): Provision cloud resources on AWS, Azure, or GCP.
Security & Compliance: Ensure firewall rules, package updates, and user access controls.
CI/CD Integration: Automate build and deployment processes with Jenkins, Git, and Docker.


## Basic Working of Ansible:

Control Node: The machine where Ansible is installed.
Managed Nodes: The servers that Ansible controls (without requiring an agent).
Inventory File: A list of target servers defined in a simple text file.
Playbooks: YAML files that contain the automation instructions.
Modules: Predefined scripts that perform specific tasks (e.g., install a package, restart a service).

## Example of Ansible Playbook

    - name: Install Apache on Ubuntu
        hosts: webservers
        become: yes
    tasks:
    - name: Install Apache
      apt:
        name: apache2
        state: present
    - name: Start Apache Service
      service:
        name: apache2
        state: started
