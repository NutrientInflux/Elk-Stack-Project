# Elk-Stack-Project
First Project for Cybersecurity certification class

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- Load balancers protect from DDoS attacks by shifting attack traffic. Jump box gives access to the user from single node which can be secured and monitored.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.
- Filebeat monitors log files or locationsa nnd collects log events.
- Metricbeat takes metrics and statistics and ships them to specified output.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    |Webserver | 10.0.0.5   | Linux            |
| Web-2    |Webserver | 10.0.0.6   | Linux            |
| ElkStack |ElkServer | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by home network IP
- Jump box. IP 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | Home Ip    |
| Web-1    | No                  | 10.0.0.4             |
| Web-2    | No                  | 10.0.0.4             |
| Elkstack | No                  | 10.0.0.4             |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- Install: docker.io
- Install: python-pip
- Install: docker
- Command: sysctl -w vm.max_map_count=262144
- Launch docker container: elk

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
![image (8)](https://user-images.githubusercontent.com/89425182/146650303-6aaf7ac9-7490-4066-8542-277bfb0f8063.png)
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5 & 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat

These Beats allow us to collect the following information from each machine:
- Filebeat centralizes and forwards log data. The information is then forwarded to Elasticsearch which provides a GUI that simplifies monitoring
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the host file to include webserver IP's and ELKserver IP
- Run the playbook, and navigate to HTTP://<ELKserver_public_IP>:5601 to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- the .yml file is the playbook and should be coppied to /etc/ansible/filebeat-configuration.yml
- Edit the /etc/ansible/host file to add webserver/elkserver IP addresses
- _Which URL do you navigate to in order to check that the ELK server is running?
