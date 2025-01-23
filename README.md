# Ansible

Ansible is an open-source IT automation tool that helps in configuration management, application deployment, and task automation. It allows you to manage multiple servers without requiring manual intervention.

### Common Use Cases:

**Server Configuration:** Install and configure Apache, MySQL, PHP, etc.<br>
**Software Deployment:** Automate application deployments on multiple servers.<br>
**Infrastructure as Code (IaC):** Provision cloud resources on AWS, Azure, or GCP.<br>
**Security & Compliance:** Ensure firewall rules, package updates, and user access controls.<br>
**CI/CD Integration:** Automate build and deployment processes with Jenkins, Git, and Docker.


### Basic Working of Ansible: 

**Control Node:** The machine where Ansible is installed.<br>
**Managed Nodes:** The servers that Ansible controls (without requiring an agent).<br>
**Inventory File:** A list of target servers defined in a simple text file.<br>
**Playbooks:** YAML files that contain the automation instructions.<br>
**Modules:** Predefined scripts that perform specific tasks (e.g., install a package, restart a service).

### Example of Ansible Playbook

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

### Install Ansible on Ubuntu

    sudo apt install software-properties-common -y
    sudo add-apt-repository --yes --update ppa:ansible/ansible
    sudo apt install ansible -y

#### Ansible Path

    cd /etc/ansible

#### Activatation the ansible.cfg file

    sudo -i
    cat /etc/ansible/ansible.cfg
    
Copy the command given in ansible.cfg file

     Since Ansible 2.12 (core):
    # To generate an example config file (a "disabled" one with all default settings, commented out):
    #               $ ansible-config init --disabled > ansible.cfg
    #
    # Also you can now have a more complete file by including existing plugins:
    # ansible-config init --disabled -t all > ansible.cfg

    # For previous versions of Ansible you can check for examples in the 'stable' branches of each version
    # Note that this file was always incomplete  and lagging changes to configuration settings

    # for example, for 2.9: https://github.com/ansible/ansible/blob/stable-2.9/examples/ansible.cfg

This Command will give you **full ansible.cfg file**

#### Create Host Instance 

1) AWS > EC2 > Launch Instance > Name(Host) > Create

2) add Host Instance IP in Host file at `` nano /etc/ansible/host 

**Host file look like this**

    # This is the default ansible 'hosts' file.
    #
    # It should live in /etc/ansible/hosts
    #
    #   - Comments begin with the '#' character
    #   - Blank lines are ignored
    #   - Groups of hosts are delimited by [header] elements
    #   - You can enter hostnames or ip addresses
    #   - A hostname/ip can be a member of multiple groups

    # Ex 1: Ungrouped hosts, specify before any group headers:

    ## green.example.com
    ## blue.example.com
    ## 192.168.100.1
    ## 192.168.100.10

    ***Add you Host IP Here***

    # Ex 2: A collection of hosts belonging to the 'webservers' group:

    ## [webservers]
    ## alpha.example.org
    ## beta.example.org
    ## 192.168.1.100
    ## 192.168.1.110

    # If you have multiple hosts following a pattern, you can specify
    # them like this:

    ## www[001:006].example.com

    # You can also use ranges for multiple hosts: 

    ## db-[99:101]-node.example.com

    # Ex 3: A collection of database servers in the 'dbservers' group:

    ## [dbservers]
    ##
    ## db01.intranet.mydomain.net
    ## db02.intranet.mydomain.net
    ## 10.25.1.56
    ## 10.25.1.57


    # Ex4: Multiple hosts arranged into groups such as 'Debian' and 'openSUSE':

    ## [Debian]
    ## alpha.example.org
    ## beta.example.org

    ## [openSUSE]
    ## green.example.com
    ## blue.example.com

    
![Ansible Working](/ansible%20working.png)

![](/download.png)

![](/ansible_inv_start.png)

