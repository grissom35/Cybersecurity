## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  
![Network Diagram](https://github.com/grissom35/Cybersecurity/blob/main/Network_Diagram/network_diagram.png)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the config file may be used to install only certain pieces of it, such as Filebeat.
[ELK Playbook](https://github.com/grissom35/Cybersecurity/blob/main/Ansible/Install-elk.yml)
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box? availability // to allow for a single secured point of entry to server
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the resources and system log files.
- _TODO: What does Filebeat watch for? modifcations to the critical system config files and logs
- _TODO: What does Metricbeat record? unexpected changes to the system resource utilization
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
| Name     | Function  | IP Address | Operating System |
|----------|-----------|------------|------------------|
| Jump Box | Gateway   | 10.0.0.4   | Linux            |
| VM1      |     VM    | 10.0.0.5   | Linux            |
| VM2      |     VM    | 10.0.0.6   | Linux            |
| ELK      |   SIEM    | 10.1.0.4   | Linux            |
### Access Policies
The machines on the internal network are not exposed to the public Internet. 
Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP address -- 73.204.62.188
Machines within the network can only be accessed by Jumpbox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address? Again... Jumpbox --> 10.0.0.4
A summary of the access policies in place can be found in the table below.
| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 73.204.62.188        |
| VM       | No                  | 10.0.0.4             |
| VM       | No                  | 10.0.0.4             |
### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? Allows to configure and administer multiple machines at the same time. 
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
- Install Docker.io
- Expand memory usage
- Download and install docker image
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  
[Docker PS](https://github.com/grissom35/Cybersecurity/blob/main/Linux/docker_ps.png)
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring -- 10.0.0.5 && 10.0.0.6
We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed -- filebeat && metricbeat
These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
- Metricbeat -- collects statistics regarding system resource usage eg: cpu percentage, memory percentage
- Filebeat -- Monitors for changes to critical system log and config files eg: syslog or shadow
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 
SSH into the control node and follow the steps below:
- Copy the config file to VM.
- Update the hosts file to include desired IP addresses
- Run the playbook, and navigate to the VM to check that the installation worked as expected.
_TODO: Answer the following questions to fill in the blanks:
- _Which file is the playbook? Where do you copy it? YAML and place it in the playbooks directory
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? update the hosts file and specify the VM IP addresses in the servers or groups categories
- _Which URL do you navigate to in order to check that the ELK server is running? ELK server public IP on port 5601
