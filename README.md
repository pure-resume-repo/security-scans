# Ansible Configurations for Security and Updates

This repository contains various Ansible configuration files aimed to help you manage both security settings and system updates on Ubuntu machines.

## Table of Contents

Overview
Repository Structure
Files
Updates.yml
ufw.yml
Security_scan.yml
Summary_of_steps.org
Usage
## Overview

These Ansible playbooks are designed to automate various tasks relating to system updates and security scans.

## Repository Structure

.
|-- .git
|-- .gitignore
|-- lynis_latest_report
|-- .pre-commit-config.yaml
|-- README.md
|-- .secrets.baseline
|-- security-scans-results
|-- security_scan.yml
|-- summary_of_steps.org
|-- ufw.yml
|-- updates.yml
## Files
### Updates.yml
This Ansible playbook is used for updating system packages. It performs tasks such as:
- Updating and upgrading APT packages
- Upgrading specific packages like `snapd` and `python3-pip`
- Running `snap refresh`
- Autocleaning the package manager
[View Updates.yml](./updates.yml)
### ufw.yml
This playbook is designed to configure UFW (Uncomplicated Firewall) rules. It includes tasks like:
- Installing UFW if not already installed
- Resetting UFW rules
- Denying all incoming and outgoing traffic by default
- Allowing specific outgoing traffic on ports like 80, 443, 22, etc.
[View ufw.yml](./ufw.yml)
### Security_scan.yml
This playbook performs various security scans on the system:
- Starting `nessusd` service
- Running `clamscan`
- Executing Lynis security scan
[View Security_scan.yml](./security_scan.yml)
### Summary_of_steps.org
This Org file summarizes the steps for security updates and maintenance. It's a handy guide for manual procedures related to updates and security scans.
[View Summary_of_steps.org](./summary_of_steps.org)
## Usage
To run an individual playbook, navigate to the directory containing the `.yml` file and execute:
```
ansible-playbook <name-of-playbook.yml>
```
For example, to run the `updates.yml` playbook:
```
ansible-playbook updates.yml
```
**Note**: Depending on the tasks, you might need to run the playbook with sudo permissions:
```
sudo ansible-playbook <name-of-playbook.yml>
```
```
