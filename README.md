# Bin-Homework-Github-Fundamentals
Bin Li's homework for Week 13-Github-Fundamentals

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  

![TODO: Update the path with the name of your diagram](https://github.com/PandaPooPoo888/Bin-Homework-Github-Fundamentals/blob/main/Diagrams/_BIN%20LI__12-Cloud-Security%20HW_.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. 
Alternatively, select portions of the above file may be used to install only certain pieces of it, such as Filebeat.

![TODO: Enter the playbook file](https://github.com/PandaPooPoo888/Bin-Homework-Github-Fundamentals/blob/main/Ansible/filebeat-playbook-yml.rtf)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

_TO DO: Load balancing ensures that the application will be highly available and reliable, in addition to restricting traffic to the network by distributing it across multiple servers.

- _TODO: What aspect of security do load balancers protect? It defends an organization against distributed denial-of-service (DDoS) attacks.
- _TODO: What is the advantage of a jump box? A Jump Box sits in front of other machines that are not exposed to the public internet.

- _TODO: Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- _TODO: What does Filebeat watch for?_Filebeat monitors log files and collects log events.
- _TODO: What does Metricbeat record?_Metricbeat records metrics and statistics and ships them to Elasticsearch or Logstash.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function      | IP Address | Operating System | Notes             |
|------------|---------------|------------|------------------|-------------------|
| jump-box   | Gateway       | 10.0.0.4   | Linux            | a nice VM gateway |
| web-1      | Protected VM  | 10.0.0.5   | Linux            |                   |
| web-2      | Protected VM  | 10.0.0.6   | Linus            |                   |
| web-3      | Protected VM  | 10.0.0.7   | Linux            |                   |
| ELK-Server | Protected VM  | 10.1.0.4   | Linux            |                   |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump-box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_13.82.144.251


Machines within the network can only be accessed by the SSH to the Jumpbox through port 22
- _TODO: Which machine did you allow to access your ELK VM? jump-box   What was its IP address?_104.42.199.56

A summary of the access policies in place can be found in the table below.

| Name               | Public Accessible     | Allowed IP Address    | Notes   |
|------------------|-------------------------|--------------------------|---------|
| jump-box        | Yes                             | 10.0.0.1                       |           |
| web-1.            | No                              | 10.0.0.5                       |           |
| web-2.            | No                              | 10.0.0.6                       |           |
| web-3.           |  No                              | 10.0.0.7                       |           |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because: 
That saves a lot of time.
- _TODO: What is the main advantage of automating configuration with Ansible?_One changes will change all VMs in one go, saves time. 

The playbook implements the following tasks:

- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- 1 - Create Virtual Network in Azure within the same Resource Group.
- 2 - Create network connect between the Virtual Networks.
- 3 - Create a new VM in the Vitrual Network, add VM to Ansible's hosts file.
- 4 - Create an Ansible Playbook that installs Docker and configures an ELK container. 
 - 5 - Run the Playbook to launch the container.
 - 6 - Set the ELK VM to restricted access (especially against Hassan).

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  


![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_10.1.0.5; 10.1.0.6; 10.1.0.7

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_metric beats and file beats

These Beats allow us to collect the following information from each machine:

- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.

_ Metric Beats takes the metrics and statistics and ships them to the output. 

_File Beats ships log files in an ELK type pipeline, it's like a logging agent, tailing and forwarding data 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ansible host file to /etc/ansible.
- Update the host file to include the internal IP address of web servers and ELK servers. 
- Run the playbook, and navigate to Kibana banana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? 

ansible-playbook pentest.yml

- _Where do you copy it?

Web VMs

- _Which file do you update to make Ansible run the playbook on a specific machine? 

The config file

- _ How do I specify which machine to install the ELK server on versus which to install Filebeat on?_

The config file


- _Which URL do you navigate to in order to check that the ELK server is running?

Filebeat installation page on the ELK server.


_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._


1

root@1accfd9794bd:/etc/ansible# ansible-playbook pentest.yml          

2

root@1accfd9794bd:/etc/ansible# ansible-playbook elk.yml

3

root@1accfd9794bd:/etc/ansible# ansible-playbook filebeat-playbook.yml


Final Note: It's Important I Get an A+

