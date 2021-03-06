## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: ansible-playbook filebeat-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available and reliabile, in addition to restricting flow to the network.
- _TODO: What aspect of security do load balancers protect? Load Balancers defends an organization against DDoS attacks

 - What is the advantage of a jump box? A jump box is a secure computer that all admins first connect to before launching any administrative task

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_Filebeat monitors log files, collects log events, and forwards them to Elasticsearch or Logstash
- _TODO: What does Metricbeat record?_Metricbeat records metrics and statistics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name                 | Function       | IP Address | Operating System |
|----------            |----------      |------------|------------------|
| Jump Box Provisioner | Gateway        | 10.0.0.4   | Linux            |
| Bradley-Elk-VM       | Elk Stack      | 10.2.0.4   | Linux            |
| Web-1                | DVWA Container | 10.0.0.8   | Linux            |
| Web-2                | DVWA Container | 10.0.0.9   | Linux            |
| Web-3                | DVWA Container | 10.0.0.11  | Linux

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox_ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_The machine allowed access to the ELK VM is the Jump Box Provisioner.  Its IP is 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name                 | Publicly Accessible | Allowed IP Addresses |
|----------            |---------------------|----------------------|
| Jump Box Provisioner | Yes                 |Home IP Address       |
| Web-1                | No                  |10.0.0.4              |
| Web-2                | No                  |10.0.0.4              |
| Web-3                | No                  |10.0.0.4              |
| Bradley-Elk-VM       | No                  |10.0.0.4              |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_The main advantage is you can put commands into more than one server from one playbook

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...Install docker.io
- ...Install python-pip
- ...Install docker


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_10.0.0.8, 10.0.0.9, 10.0.0.11

We have installed the following Beats on these machines:
- _Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Filebeat collects changes done, while Metricbeat collects metrics and statics


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _install-elk.yml_ file to _/etc/ansible_.
- Update the _hosts_ file to include IP address for Bradley-Elk-VM
- Run the playbook, and navigate to _http://20.81.160.162:5601/app/kibana#_ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_etc/ansible/roles# filebeat-playbook.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
- _Edit on /etc/ansible/host and add to the elkserver IP address
- _Which URL do you navigate to in order to check that the ELK server is running? www.{mypublicIP}:5601/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._