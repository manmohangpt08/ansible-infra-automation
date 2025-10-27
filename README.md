## Project
Name: ansible-infra-automation  
Purpose: Automate provisioning, installation and basic verification of Druid, Kafka, Zookeeper, MySQL and related system packages.

## Quick Overview
- What is Ansible?
    - Ansible is an open-source automation tool for provisioning, configuration management, and application deployment. It uses simple YAML playbooks, connects over SSH (agentless), and is designed to be idempotent and easy to read.
- This repo contains playbooks, roles, inventories, and templates to automate provisioning and basic setup for Druid, Kafka, Zookeeper, MySQL, and related system packages.
- Key folders:
    - `inventory/` — host inventories (e.g., `clusterInventory`)
    - `playbooks/` — Ansible playbooks (e.g., `installDruid.yml`, `kafkaInstall.yml`, `mysqlSetup.yml`, `zkInstall.yml`)
    - `roles/` — reusable roles (`druid/`, `kafka/`, `mysql/`, `zookeeper/`) with tasks/templates/files

## Prerequisites
- Linux server(s) (Debian/Ubuntu or RHEL/CentOS)
- Java 11 (OpenJDK)
- Python 3.x (for Ansible)
- curl, wget, tar, unzip, rsync, mysql-client
- Optional: Ansible >= 2.9, docker/podman for testing

- Check versions:
    - java -version
    - python3 --version
    - ansible --version

## CI / CD checks
- ansible-lint
- ansible-playbook --syntax-check

## Run a playbook (with inventory and verbose output):
- ansible-playbook -i inventory/clusterInventory playbooks/first_pb.yml -vv
- ansible-playbook -i inventory/clusterInventory playbooks/copyfile.yml -vv
- ansible-playbook -i inventory/clusterInventory playbooks/install_packages.yml -vv
- ansible-playbook -i inventory/clusterInventory playbooks/zkInstall.yml -vv
- ansible-playbook -i inventory/clusterInventory playbooks/kafkaInstall.yml -vv
- ansible-playbook -i inventory/clusterInventory playbooks/mysqlSetup.yml -vv
- ansible-playbook -i inventory/clusterInventory playbooks/installDruid.yml -vv