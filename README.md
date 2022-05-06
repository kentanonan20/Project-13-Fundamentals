# Project-13-Fundamentals
Project 13: Ansible YML, Bash scripts
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Project13 Diagram](https://user-images.githubusercontent.com/34134757/167068256-f1fdbd1f-dcfc-44e2-8e01-7ca4906f8c9d.png)


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  /etc/ansible/install-elk-playbook.yml

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
What aspect of security do load balancers protect? What is the advantage of a jump box?
  -Load balancers protects the system from DDoS attacks by shifting attacks
  -Load balancers contribrutes to Availability aspect of security.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the changes and system logs.
  What does Filebeat watch for?
    -Filebeat watches for any information in the file system which has been changed.
    -Filebeat watches for log files and collects log events.
   What does Metricbeat record?
    -Metricbeat takes the metrics and statistics collects and ships them to the output it specifies.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    | Server   | 10.0.0.8   | Linux            |
| Web-2    | Server   | 10.0.0.10  | Linux            |
| Elk-Proj.| ElkServer| 10.0.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Add whitelisted IP addresses- Public IP address changes everytime when the VM is on/off. Public IP 20.222.51.51

Machines within the network can only be accessed by _____.
Which machine did you allow to access your ELK VM? What was its IP address?
 -Jumpbox VM with its provate IP address 10.0.0.4
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 10.0.0.4             |
| Web-1    | No                  | 10.0.0.8             |
| Web-2    | No                  | 10.0.0.10            |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
What is the main advantage of automating configuration with Ansible?
  -It allows you to deploy to multiple servers using a playbook.
The playbook implements the following tasks:
- Install docker.io
- Install Python-pip
- Install docker container
- Launch docker container:elk
- sysctl -w vm.max_map_count=262144

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.


![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
