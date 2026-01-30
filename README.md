# Ansible Setup – DevOps Technical Test

## Overview
This repository contains an Ansible project used to provision and deploy a Node.js application on an AWS EC2 instance.  
The setup follows infrastructure automation best practices, including idempotent playbooks, key-based SSH access, and process management using PM2.
This repository covers Part A of the deployment. Part B (Docker, CI/CD, Kubernetes) is available in a separate repository.

---

## Environment
- Target OS: Ubuntu 22.04 LTS
- Cloud Provider: AWS EC2
- Configuration Management: Ansible
- Application Runtime: Node.js
- Process Manager: PM2

---

## Requirements
- Ansible 2.x or newer
- SSH key-based access to the target server
- AWS EC2 instance (Ubuntu 22.04)

---

## Inventory
The inventory is defined in `inventory.ini` and includes the following host group:

- **app_servers**  
  Application servers hosting the Node.js application.

---

## Ansible Configuration
Ansible behavior is configured via `ansible.cfg` with the following settings:
- SSH key-based authentication
- Default remote user: `ubuntu`
- Privilege escalation enabled using `sudo`
- Host key checking disabled for automation simplicity

---

## SSH Access
SSH access to the target server is configured using a private key.  
The private key location is defined in `ansible.cfg`.

---

## Project Structure
ansible.cfg     # Ansible configuration
inventory.ini   # Inventory definition
runtime.yml     # Runtime setup (Node.js, PM2)
deploy.yml      # Application deployment via PM2
