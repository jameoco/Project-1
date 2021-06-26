# Project-1
Project components completed up to project 1. this includes Linux Bash, Ansible Playbooks, Network Diagrams and other code based projects.
​
Automated ELK Stack Deployment
​
The files in this repository were used to configure the network depicted below.<br>
<br>
​
![image](https://user-images.githubusercontent.com/80502251/123496829-54b14f00-d5e7-11eb-98c1-80f0fffbe4a7.png)<br>
<br>

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above or alternatively, select portions of the Ansible file may be used to install only certain pieces of it, such as Filebeat.
​
- https://github.com/jameoco/Project-1/blob/main/Ansible/Install-ELK.yml
- https://github.com/jameoco/Project-1/blob/main/Ansible/Filebeat-Playbook.yml
- https://github.com/jameoco/Project-1/blob/main/Ansible/metricbeat-playbook.yml<br>

This document contains the following details:  
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
​
​
### Description of the Topology
​
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.<br>
​
load balancing achieves a greater amount of reliability by ensuring web traffic has access to redundant web servers. if 1 of the 2 web servers goes down or has any issues handling the amount of traffic coming in the load balancer will automatically switch to the backup web server to allow consistent access.<br> 
​
additionally, a Jumpbox was added to the network. This is added as an additional layer of security insulating the network from the rest of the internet. We can control who has access to the jumpbox through IP and port management reducing the risk of breaches.<br>
​
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Jumpbox and system Network.
- Filebeat is used to monitor log files or locations you specify, collects log events, then logs them within elasticearch or Logstash for indexing
- Metricbeat is used for collecting informatuion of the operating system and services running on the server.<br>
 <br>
The configuration details of each machine may be found below.<br>

<br>

| Name       | Function   | IP Address | Operating System |
|------------|------------|------------|------------------|
| Jump Box   | Gateway    | 10.0.0.2   | Linux            |
| Web-1      | Webserver  | 10.0.0.3   | Linux            |
| Web-2      | Webserver  | 10.0.0.4   | Linux            |
| Elk Server | Monitoring | 10.2.0.4   | Linux            |
​
### Access Policies
​
The machines on the internal network are not exposed to the public Internet. Only the jump-box Provisioner machine can accept connections from the Internet.<br>
<br>
Access to the jump box provisioner machine is only allowed from the following IP addresses:<br>
-My public IP address. 73.229.20.24<br>
<br>
Machines within the network can only be accessed by the Jumpbox.<br>
-the jumpbox public ip was used. 13.82.29.87<br>
<br>
A summary of the access policies in place can be found in the table below.<br>
<br>

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 73.229.20.24         |
| Web-1    | No                  | 10.0.0.2             |
| Web-2    | No                  | 10.0.0.2             |
| Elk-Svr  | No                  | 10.0.0.2             |
​
### Elk Configuration
​
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Automating using ansible is highly preferable for this type of situation. To type out the full set of code alone can take several minutes if you know it by heart. To have to do that over and over for every new machine being added to the network can be cumbersome. This allows us to automate the process and to it at the click of a button. Also, we can edit these setups as we may only want some of these services on some new VM’s or we may want to add additional services to other VM’s. ansible allows us to have custom builds and keep them ready to go at a moment’s notice. 
<br>
​

The playbook implements the following tasks:
- Install Docker.io
- Install pip3
- Install Docker Python Module
- Increase Memory
- Download and Launch A Docker ELK Container
- Enable Service Docker on Boot
​
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
​
![image](https://user-images.githubusercontent.com/80502251/123497296-eae67480-d5e9-11eb-96f5-f90c58364d53.png)
​
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 10.0.0.3
- Web-2 10.0.0.4
​
### We have installed the following Beats on these machines:
- Filebeat
- Metricbeat <br>

​
These Beats allow us to collect the following information from each machine:
- Filebeat - will log files or locations specified, collect log events, then log them within elasticearch or Logstash for indexing
- Metricbeat - will be used for collecting informatuion of the operating system and services running on the server.
​
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: <br>
​
SSH into the control node and follow the steps below:
- Copy the Install-ELK.yml file to /etc/ansible.
- Update the  Hosts file to include ELK and Webserver ip addresses
- Run the playbook, and navigate to new ELK Kibana website to check that the installation worked as expected. do this by typing in the ELK_publicip_IP:5601 into a webbrowser. if it takes you to the home page for that ip it is working properly.
​
## Commands to install and run playbook:
- cd /etc/ansible
- nano ELK-Install.yml
- cd nano hosts
- change webservers and ELK IP addresses
- change webservers ip address for new web server
- change ELK to new ELK server IP
- ansible-playbook install-elk.yml (https://github.com/jameoco/Project-1/blob/main/Ansible/Install-ELK.yml)
- ansible-playbook filebeat-playbook.yml (https://github.com/jameoco/Project-1/blob/main/Ansible/Filebeat-Playbook.yml)
- ansible-playbiook metricbeat.yml (https://github.com/jameoco/Project-1/blob/main/Ansible/metricbeat-playbook.yml)
- go to web browser and type http://elkserverip:5601/app/kibana
