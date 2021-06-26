# Code-Bootcamp
This is a repository of various projects
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Diagram.png https://github.com/Ferdish0/Code-Bootcamp/blob/main/Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

  - ansibleplaybook.yml._

This document contains the following details:
- This is a topology with a web server behind a load balancer and a jumpbox that is behind a firewall
- Current access policies are an open port 80 and 5601 allow rdp and ssh into web servers and an open conection for the ip  172.72.118.152
- ELK Configuration is 3 web vms
  - Beats in Use
  - 3 Machines Being Monitored
- The Ansible Build can be executed using the ansibleplaybook.yml which can be used to implement new security groups.


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting overload to the network.
- A load balancer will help protect one of the most vital aspects of the web which is availability. A jump box is also important as it is a hardened machine that can allow a controlled access to the web servers 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the rules and system logs.
-File beat is monitoring and gathering all logs from its location as specified
- Meanwhile Metric beat collects metrics and statistics

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web 1    | Server   | 10.0.0.7   | Linux            |
| Web 2    | Server   | 10.0.0.6   | Linux            |
| Web 3    | Server   | 10.0.0.13  | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump BIx machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 172.72.118.152

Machines within the network can only be accessed by port 80 or 5601.
- Dvma container can be accessed by ip address from Homepc ip 172.72.118.152 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
| Home Pc  | No                  | 172.72.118.152       |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Allows the employees to run daily tasks much more easily and efficeint

The playbook implements the following tasks:
- Install Docker
- Install Elastic Search
- Install Logstash
- Install Kibana
- Ship any necessary data


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Ip 10.0.0.7, 10.0.0.6, 10.0.0.13

We have installed the following Beats on these machines:
- Web vm 1-3

These Beats allow us to collect the following information from each machine:
- Beats collect the logs environments and document them with  metadata from hosts, Docker and Kubernetes, and cloud providers before shipping it to the Elastic Stack. It can also collect additional information like file locations.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

- The ansible is the filebook which is copied onto the remote hosts.
- The filebeat and the inventory file will need to be updated in order to update. It is possible to install onto a specific server with a server_name
- In this case "Ipadress"/app/kibana#/home
