# Vagrant Ansible Setup for Prometheus and Grafana Monitoring
This repository contains code to automatically set up a virtual machine running Ubuntu 20.04 with Prometheus and Grafana installed and running, using Vagrant and Ansible.

## Requirements
- Vagrant
- VirtualBox
- Ansible
- Python
## Usage
- Clone the repository to your local machine.
- Navigate to the repository directory and run __vagrant up__ command.
- Wait for Vagrant to download the Ubuntu 20.04 box and run the provisioning script to install Docker and Docker Compose, as well as node exporter for Prometheus and the Prometheus and Grafana containers.
- Once the Vagrant provisioning is complete, you can access Grafana at http://localhost:3000. The default login credentials are 'admin/admin'. The dashboard 1860 will be preloaded with the metrics collected by node exporter running on the Ubuntu VM.
You can stop the virtual machine by running vagrant halt, and start it again by running vagrant up.
## Ansible Playbooks
The Ansible playbooks used to provision the virtual machine are included in the ansible directory of this repository. If you would like to modify the configuration of any of the components, you can edit these playbooks and then run vagrant provision to apply the changes.

## Configuration
The Vagrantfile uses the following configuration:

- Box: __generic/ubuntu2004__
- Docker version: __23.0.1__
- Docker Compose version: __1.25.0__
- Node exporter version: __1.2.2__
- Prometheus version: __2.43.0__
- Grafana version: __8.5.22__
