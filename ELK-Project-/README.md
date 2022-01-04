## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO:  Diagrams Network Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: 

ANSWER== /etc/ansible/install-elk-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
ANSWER=== LB protects the system from DDoS attacks 
	  The advantage of a jump box is to give the user access in a more secure and monitored way		
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- _TODO: What does Filebeat watch for?_

ANSWER== Filebeat watches for log files/locations and collects log events 
- _TODO: What does Metricbeat record?_
ANSWER== Metricbeat records metric and statistical data from the operating system and from services running on the server

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  |10.0.0.1        | Linux |
| Web1     | Server   |10.0.0.7        | LINUX |
| Web2     | Server   |10.0.08         | LINUX |
| ELKVM    |ELK Server|10.1.0.4        | LINUX |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

ANSWER== 

Machines within the network can only be accessed by SSH.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

ANSWER== I allowed the JumpboxVM and the private/public IP is: 10.0.0.6/40.87.109.29

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 10.0.0.6    		|
| Web1     | No                  | 10.0.0.7                     |
| Web2     | No                  | 10.0.0.8                     |

ELKVM 	     No.                   10.1.0.4   

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

ANSWER== The main advantage of configuring a playbook is you can deploy multiple servers using a playbook

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker.io
- Install Python-pip
- Install docker container
- Launch docker container: ELK
- Use command: systctl -w vm.max_map_count=262144

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

ANSWER== 

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

ANSWER== 10.0.0.7/10.0.0.8

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

ANSWER== Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

ANSWER== Filebeat monitors log files and specific locations, also collecting log events and forwarding them too Elastisearch.
         Metricbeat collects the metrics of the operating system and the services on which server it is running

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to /etc/ansible.
- Update the configuration file to include...
- Run the playbook, and navigate to ELKVM to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
ANSWER== /etc/ansible/file/filebeat-configuration.yml

- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
ANSWER== edit the /etc/ansible/hosts file to add webserver/elkserver ip addresses

- _Which URL do you navigate to in order to check that the ELK server is running?
ANSWER== http://[your.ELK-VM.External.IP]:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

- 







