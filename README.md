## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Playbook-file may be used to install only certain pieces of it, such as Filebeat.

  Install ELK: Enter the playbook file._
  Filebeat 
  Metricbeat 

This document contains the following details:
- Description of the Topology: file:///Users/mparker/Downloads/topology(1).svg
- Access Policies 
- ELK Configuration 
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting excess traffic to the network.
- _TODO: What aspect of security do load balancers protect denial service attacks? What is the advantage of a jump box Allows individuals to connect via remote access, while being secured from a single nod?

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Network traffic and system CPU Usage.
- _TODO: What does Filebeat watches for logged files and where the logs are stored.
- _TODO: What does Metricbeat record? Metricbeat checks the metrics of your computer like your CPU's

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| ELK      | Server   | 10.1.0.4   | Linux            
| Web 1    | Server   | 10.0.0.5   | Linux             |
| Web 2    | Server   | 10.0.0.6   | Linux             |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by Individual that have the SSH key.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address? Jumpbox 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |  20.185.194.225      |
| ELK      | Yes                 |  40.122.159.94       |
| Web      | No                  |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? Running an Ansible playbook once automatically connects it to other systems

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- .  The playbooks implements five tasks
- ...     - Installs docker.io
          - Installs python-pip
          - Install Docker container (ELK)
          - Expand the memory sysctl -w vm.max_map_count=262144
          - Launch the Container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines: Web 1 and Web 2
- _TODO: List the IP addresses of the machines you are monitoring_ 10.0.0.5 | 10.0.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ Metricbeats and Filebeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

Metricbeat collects CPU or memory 
Filebeat monitors log files and were this log files are sent

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Playbook file to /etc/ansible.
- Update the Config file to include - ELK VM Address 
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Filebeat/Metricebeat Where do you copy it?/etc/ansible/roles
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? Run the playbook With my Machines Internal I.P. Address
- _Which URL do you navigate to in order to check that the ELK server is running? I.P.    http://20.185.194.225:5601/app/kibana  the two groups web serve or elk server 

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
