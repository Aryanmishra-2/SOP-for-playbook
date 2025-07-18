# Standard Operating Procedure (SOP) for Executing Ansible Playbooks

## Table of Contents
- [Introduction](#introduction)  
- [Purpose](#purpose)  
- [Prerequisites](#prerequisites)  
- [Required Inputs](#required-inputs)   
- [Execution Steps](#execution-steps)  
- [Validation & Pre-Checks](#validation--pre-checks)   
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

| Step                     | Description                   | Command                                                                 |
|--------------------------|-------------------------------|-------------------------------------------------------------------------|
| Run Playbook             | Basic playbook execution      | `ansible-playbook -i inventory playbook.yml`                        |
| Run with Extra Variables | Pass variables via CLI        | `ansible-playbook -i inventory playbook.yml -e "env=dev version=1.0"` |
| Run with Vault Password  | Execute with vault-protected secrets | `ansible-playbook -i inventory playbook.yml --ask-vault-pass`       |

---
##  Validation & Pre-Checks
- Test Host Connectivity
```bash
ansible -i inventory all -m ping
```
---

 ## Troubleshooting Tips

| Issue                   | Cause                          | Fix                                                    |
|-------------------------|--------------------------------|---------------------------------------------------------|
| Permission Denied (SSH) | SSH key/user misconfiguration  | Use correct key and user                               |
| Missing Variable        | Variable not defined           | Define in `group_vars` or pass via `-e` on the CLI     |
| Vault Error             | Vault not decrypted properly   | Use `--ask-vault-pass` flag                            |
| Module Not Found        | Missing collection or role     | Run `ansible-galaxy collection install <name>`         |

---

## Best Practices

| No                                     | Description                                                                 |
|-----------------------------------------|-----------------------------------------------------------------------------|
| Use Roles                               | Modularize playbook logic using reusable role structures                    |
| Use Ansible Vault                       | Secure sensitive variables and credentials                                  |
| Validate in Staging                     | Test playbooks in non-production environments before rollout                |
| Use Tags                                | Run specific tasks or portions of a playbook using `--tags` and `--skip-tags` |
| Ensure Idempotency                      | Make sure playbooks can run multiple times without side effects             |

---
## Conclusion
This SOP ensures a standardized, secure, and efficient method for automating infrastructure tasks using Ansible Playbooks. Following these guidelines helps reduce manual errors, speed up deployments, and maintain consistency across environments. Always validate in test environments before production.

---

## Contact Information

| Name          | Email                                |
| ------------- | ------------------------------------ |
| Aryan Mishra  | aryan.mishra@mygurukulam.co          |

---

## References

| Name                       |         Resource                                                         |
|--------------------------------|----------------------------------------------------------------------|
| Official Ansible Documentation | [Link](https://docs.ansible.com/)                        |
| Ansible Galaxy Roles           | [Link](https://galaxy.ansible.com/)                    |
| Best Practices – Ansible Guide | [Link](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html) |
| Ansible Vault                  | [Link](https://docs.ansible.com/ansible/latest/user_guide/vault.html) |
| Dynamic Inventory Plugins      | [Link](https://docs.ansible.com/ansible/latest/plugins/inventory.html) |


---


