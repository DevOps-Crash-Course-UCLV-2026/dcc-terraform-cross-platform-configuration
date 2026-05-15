# Project: Terraform Cross-Platform Configuration

## Overview

Your task is to automate the setup of **HashiCorp Terraform** on your local machine using **Ansible**. You will build a single Playbook that intelligently detects the host OS and applies the correct installation logic, ensuring an idempotent and "ready-to-work" environment.

---

## Requirements & Logic

Your Ansible Playbook (`setup-terraform-YOUR_USERNAME.yml`) must handle the following scenarios based on the target's **OS Family**:

### 1. For Linux (Debian/Ubuntu)
You must follow the official HashiCorp repository method:
* **Dependencies:** Ensure `gnupg` and `software-properties-common` are installed.
* **Security:** Add the official HashiCorp GPG key and verify the fingerprint.
* **Repository:** Add the HashiCorp repository to the system's sources list.
* **Installation:** Update the cache and install the latest `terraform` package.

### 2. For Windows
You must leverage the power of the Chocolatey package manager:
* **Automation:** Use the `community.windows.win_chocolatey` module to install Terraform.
* **Persistence:** Ensure the environment PATH is updated so the command is recognized by the terminal.

### 3. Validation (Smoke Test)
Regardless of the OS, the Playbook must:
* Execute `terraform -version`.
* Capture the output using the `register` keyword.
* Print a success message using the `debug` module only if the command succeeds.

## How to Submit Your Work

1.  **Fork this Repository**
2.  **Clone Your Fork**
3.  **Develop a solution**
4.  **Commit & Push**
5.  **Submit a Pull Request (PR)**