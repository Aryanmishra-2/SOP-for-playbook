# Standard Operating Procedure (SOP) for Executing Ansible Playbooks

## Table of Contents
- [Introduction](#introduction)  
- [Purpose](#purpose)  
- [Prerequisites](#prerequisites)  
- [Required Inputs](#required-inputs)   
- [Execution Steps](#execution-steps)  
- [Validation & Pre-Checks](#validation--pre-checks)  
- [Post Execution Validation](#post-execution-validation)  
- [Troubleshooting Tips](#troubleshooting-tips)  
- [Best Practices](#best-practices)  
- [Contact Information](#contact-information)  
- [Conclusion](#conclusion)  
- [References](#references)  

---

## Introduction
This SOP provides a comprehensive guide to executing Ansible Playbooks for infrastructure automation and application deployment. It ensures standardized, reliable, and repeatable automation processes across environments.

---

## Purpose
The purpose of this SOP is to:
- Automate server provisioning and configuration.
- Minimize manual intervention and human error.
- Promote repeatability and consistency across development, staging, and production.

---

## Prerequisites
Ensure the following before running the playbook:
- Ansible is installed (`ansible --version`)
- SSH access is configured to all target hosts
- Python is installed on target machines
- Required roles/collections are available

---

## Required Inputs

| Parameter         | Description                                      | Example                         |
|------------------|--------------------------------------------------|----------------------------------|
| `inventory`       | Path to the inventory file                       | `./inventory/dev.ini`           |
| `playbook.yml`    | Main Ansible playbook to be executed             | `site.yml`                      |
| `extra_vars`      | Optional variables to override default ones      | `env=dev app_name=webapp`       |
| `vault_password`  | If using Ansible Vault for secrets               | `--ask-vault-pass`              |

---

## Execution Steps

## Run Playbook:
```bash ansible-playbook -i inventory playbook
```


