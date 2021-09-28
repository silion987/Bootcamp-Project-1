## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

(<a href="Diagrams/HW 13 Diagram.drawio.png">Images/diagram_filename.png</a>)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - <a href="https://github.com/silion987/Bootcamp-Project-1/blob/main/Ansible/filebeat-playbook.yml">Filebeat Playbook</a> 

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting unauthorized access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the server files and system metrics.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.1.0.4   | Linux            |
| Web-1    | Server   | 10.1.0.7   | Linux            |
| Web-2    | Server   | 10.1.0.6   | Linux            |
| Elk-Serve| Siem     | 10.0.0.1   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Web 1-2 machines can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
10.1.0.4 Jump Box

Machines within the network can only be accessed by 10.1.0.4.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 71.199.1.231         |
| Web 1/2  | Yes/no              | 52.183.1.41/10.1.0.4 |
| ELK      | No                  | 10.1.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it is repeatable without deviation.

The playbook implements the following tasks:
- Installs Docker.io, pip3, and Docker Python Module
- Increases and use of virtual memory
- Sets up a docker ELK container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(Images/docker-elk-container.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web 1 and 2 at IP addresses 10.1.0.7, and 10.1.0.6

We have installed the following Beats on these machines:
- File and Metric beats are installed and watching these web servers

These Beats allow us to collect the following information from each machine:
- Filebeat is here to help admins keep and monitor logs coming out of these servers. While Metricbeat helps our admins keep a solid eye on the performance of the servers. This is helpful to make sure our uptime stays high.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the id_rsa file to .ssh.
- Update the Elk-Server Networking file to include your IP address to get into it
- Run the playbook, and navigate to 20.106.75.116:5601/app/kibana to check that the installation worked as expected.
