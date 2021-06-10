Net

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Yaml file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Apache2.yml pentest.yml filebeat.yml metricbeat.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
Load balancer protect from DDos attacks. A jump adds an extra layer of security and abstraction when connecting to other severs.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_ Filebeat watches log files locations and events.
- _TODO: What does Metricbeat record?_ Metricbeat collects stats and collects metrics from services running on a server

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.8   | Ubuntu 18.4      |
| Web-1    |  docker  | 10.0.0.4   | Ubuntu 18.4      |
| Web-2    |  dc/dvwa | 10.0.0.5   | Ubuntu 18.4      |
|Elk Server|  elk/con | 10.2.0.4   | Ubuntu 18.4      |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_ 10.0.0.8 10.0.0.4 10.0.0.5 10.2.0.4  

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_ Jump Box 10.0.0.8 Web-1 10.0.0.4 Web-2
10.0.0.5

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses      |
|----------|---------------------|---------------------------|
| Jump Box |     No              | 10.0.0.4 10.0.0.5 10.2.0.4|
|  Web-1   |     No              | 10.2.0.4 10.0.0.5 10.0.0.8|
|  Web-2   |     No              | 10.0.0.4 10.2.0.4 10.0.0.8|
|  ELK     |     No              | 10.0.0.8 10.0.0.4 10.0.0.5|                   |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ It free's up user time by automating certain tasks

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- 
- First create Elk Manchine and V-Net and peer with other machines
- setup container on elk
- run filebeat.yml and metricbeat.yml
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ 10.0.0.5 10.0.0.4

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ filebeat.yml metricbeat.yml

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._ Filebeat collects log data, Metricbeat collects metric data from seveices on the server 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ the ansible.cfg file
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to 
 install the ELK server on versus which to install Filebeat on?_
 you Update the hosts file and add IP's on under websevers and the elksever hash or unhash as needed.
- _Which URL do you navigate to in order to check that the ELK server is running? http://23.96.233.50:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._