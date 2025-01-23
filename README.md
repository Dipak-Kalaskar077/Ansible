# Ansible

Ansible is an open-source IT automation tool that helps in configuration management, application deployment, and task automation. It allows you to manage multiple servers without requiring manual intervention.

#### Common Use Cases:

**Server Configuration:** Install and configure Apache, MySQL, PHP, etc.<br>
**Software Deployment:** Automate application deployments on multiple servers.<br>
**Infrastructure as Code (IaC):** Provision cloud resources on AWS, Azure, or GCP.<br>
**Security & Compliance:** Ensure firewall rules, package updates, and user access controls.<br>
**CI/CD Integration:** Automate build and deployment processes with Jenkins, Git, and Docker.


#### Basic Working of Ansible:

**Control Node:** The machine where Ansible is installed.<br>
**Managed Nodes:** The servers that Ansible controls (without requiring an agent).<br>
**Inventory File:** A list of target servers defined in a simple text file.<br>
**Playbooks:** YAML files that contain the automation instructions.<br>
**Modules:** Predefined scripts that perform specific tasks (e.g., install a package, restart a service).

#### Example of Ansible Playbook

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
