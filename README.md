# Cisco Router Configuration Backup Ansible

## Overview
This project automates the backup of running configurations
from Cisco IOS routers using Ansible.

## Features

- SSH-based router connectivity
- Cisco IOS running configuration backup
- Support for multiple routers
- Timestamped backup filenames
- Reusable Ansible role
- Centralized backup storage
- Credential encrypted using Ansible Vault

## Technologies Used

- Ansible
- Ansinle Vault
- Cisco IOS
- SSH
- YAML
- GNS3
- Ubuntu

## Project Structure

cisco-ansible-portfolio/
│
├── backups/
│
├── inventory/
│   ├── hosts.yml
│   └── group_vars/
│       └── cisco_routers/
│           ├── main.yml
│           └── vault.yml
│
├── playbooks/
│   └── backup.yml
│
├── roles/
│   └── cisco_backup/
│       ├── defaults/
│       │   └── main.yml
│       └── tasks/
│           └── main.yml
│
├── ansible.cfg
├── requirements.yml
├── .gitignore
└── README.md

## Requirements

- Ansible
- ansible.netcommon collection
- cisco.ios collection
- SSH access to Cisco IOS routers

## Usage

1. Configure the router inventory.
2. Set the required SSH credentials.
3. Verify SSH connectivity.
4. Run the backup playbook.
5. Check the backups directory.

## How It Works

1. Ansible reads the router inventory.
2. Group variables define the Cisco IOS connection settings.
3. Ansible Vault provides the encrypted router credentials.
4. The backup playbook executes the Cisco backup role.
5. Ansible connects to the router over SSH.
6. The running configuration is collected.
7. The configuration is saved in the local backup directory using a timestamped filename.

## Run the Playbook

ansible-playbook playbooks/backup.yml