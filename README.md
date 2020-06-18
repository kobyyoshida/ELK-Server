## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the .yml file may be used to install only certain pieces of it, such as Filebeat.

  - Ansible-Playbooks: [elk.yml](elk.yml) and [filebeat-playbook.yml](filebeat-playbook.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

- Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- Filebeat collects log records
- Metricbeat collects statistics about the DVWA-VMs

The configuration details of each machine may be found below.

| Name      | Function     | IP Address | Operating System |
|-----------|--------------|------------|------------------|
| JumpBox   | Gateway      | 10.0.0.4   | Ubuntu 18.04     |
| DVWA-VM1  | Docker-DVWA  | 10.0.0.5   | Ubuntu 18.04     |
| DVWA-VM2  | Docker-DVWA  | 10.0.0.6   | Ubuntu 18.04     |
| DVWA-VM3  | Docker-DVWA  | 10.0.0.7   | Ubuntu 18.04     |
| DVWA-VM4  | Docker-DVMA  | 10.0.0.10  | Ubuntu 18.04     |
| ELK Server| ELK          | 10.0.0.9   | Ubuntu 18.04     |
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by SSH.
- The only machine able to connect to the Elk Server is JumpBox (10.0.0.4)

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | Local IP Address     |
| DVWA-VM1 | No                  | 10.0.0.5             |
| DVWA-VM2 | No                  | 10.0.0.6             |
| DVWA-VM3 | No                  | 10.0.0.7             |
| DVWA-VM4 | No                  | 10.0.0.10            |
|ELK Server| No                  | 10.0.0.9 and Local IP Address|
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![docker ps command](https://github.com/kobyyoshida/ELK-Server/blob/master/Images/docker_ps.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- DVWA-VM1 10.0.0.5
- DVWA-VM2 10.0.0.6
- DVWA-VM3 10.0.0.7
- DVWA-VM4 10.0.0.10

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the [filebeat.yml](filebeat.yml) and [metricbeat.yml](metricbeat.yml) files to /etc/ansible/roles/files/ directory.
- Update the [filebeat.yml](filebeat.yml),[metricbeat.yml](metricbeat.yml) and  to include the IP address of the ELK Server
- Update the ansible.cfg file to change the remote_user value to the username for playbooks.
- Run the playbook, and navigate to ELK Server to check that the installation worked as expected.
- To ensure the ELK Server is running, navigate to the URL that is the public IP Address of the ELK Server
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
