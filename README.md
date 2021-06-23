# Elk-Project
Creation of a cloud network
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/1v_CsvZGQxGR3Z813AzilQG2OrnCzgkF9/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above or can be run individually. For instance, you are able to go into the files directory, located in the /etc/ansible and run the filebeat-playbook.yml. 

This document contains the following details:
- Description of the Topologyc
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly protected, in addition to restricting traffic to the network.
- What aspect of security do load balancers protect? Load Balancers protect servers from being overloaded. If one server goes out, traffic can be redistributed. 

- What is the advantage of a jump box? The jump box secures access to administrative tasks.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.

- What does Filebeat watch for? Filebeat watches and monitors the log files and locations which users specify and records.

- What does Metricbeat record? Metricbeat records data on the operating system and applications.

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System   |
|----------|----------|------------|------------------  |
| Jump Box | Gateway  | 10.0.0.4   |Linux (ubunto 18.04)|
| Webb-1   | Server   | 10.0.0.7   |Linux (ubunto 18.04)|
| Web-2    | Server   | 10.0.0.6   |Linux (ubunto 18.04)|
| ElkMach  | Monitors | 10.1.0.4   |Linux (ubunto 18.04)|

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- IP: My personal IP

Machines within the network can only be accessed by JumpBox Provisioner.
- Which machine did you allow to access your ELK VM? Only the JumpBox Provisioner has access to the ELK VM. IP is 10.1.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | My personal IP       |
| Webb-1   | No                  |  10.0.0.4            |
| Web-2    | No                  |  10.0.0.4            |
| ElkMach  | No                  |  10.0.0.4            |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it seals it from vulnerabilities.
- A main advantage of automating with Ansible

The playbook implements the following tasks:
- Install docker.io
- Install pip3
- Install docker python module
- Increase the virtual memory
- Download and launch the docker

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://drive.google.com/file/d/1Sl5fkO52Nh1CS2k2rOvaCNoYx5ZyStXq/view?usp=sharing


### Target Machines & Beats

This ELK server is configured to monitor the following machines:
- Webb-1 10.0.0.6
- Web-2 10.0.0.7

We have installed the following Beats on these machines:
- Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- The Beats allow us to collect data about log events and users as well as collect statics and metrics on our 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Playbook file to Ansible.
- Update the host file to include webserver and ELK.
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.


These are the specific commands the user will need to run to download the playbook, update the files, and run the playbook.

