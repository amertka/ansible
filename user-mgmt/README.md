# Ansible Role: Interactive Linux User Management

[![Ansible Role](https://img.shields.io/badge/ansible-role-5A5A5A?style=flat&logo=ansible)](https://galaxy.ansible.com/)
[![License](https://img.shields.io/badge/license-BSD-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/iranak/user-mgmt/graphs/commit-activity)

An **interactive, menu-driven Ansible role** for comprehensive Linux user management. This role provides a CLI-based interactive interface for managing users, groups, SSH keys, and sudo privileges across your infrastructure.

## 📋 Table of Contents
- [Features](#-features)
- [Requirements](#-requirements)
- [Interactive Operation](#-interactive-operation)
- [Role Variables](#-role-variables)
- [Default Configuration](#-default-configuration)
- [Example Playbook](#-example-playbook)
- [Operation Guides](#-operation-guides)
- [Security & Compliance](#-security--compliance)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

## ✨ Features

- **🖥️ Interactive Menu System** - User-friendly CLI interface with numbered options
- **👤 Complete User Lifecycle** - Create, update, and delete user accounts
- **👥 Advanced Group Management** - Pre-defined groups (developers, devops) with specific GIDs
- **🔐 Secure Password Policies** - Configurable password complexity and aging policies
- **🗝️ SSH Key Management** - Deploy and manage authorized SSH keys
- **⚡ Sudo Privileges** - Granular sudo access control with secure sudoers.d management
- **📊 Comprehensive Audit Logging** - Track all user management operations with retention policies
- **🛡️ Security Hardened** - Configurable UID ranges, password policies, and lockout settings
- **⚙️ Multiple Shell Options** - Support for various shells with descriptive names
- **⏱️ Timeout Control** - Configurable operation timeout for long-running tasks

## 📦 Requirements

### Ansible
- Ansible 2.9 or higher
- Python 3.6+ on control node and managed hosts

### Target Hosts
| Distribution | Versions |
|-------------|----------|
| RHEL/CentOS | 7, 8, 9 |
| Ubuntu | 18.04, 20.04, 22.04, 24.04 |
| Debian | 10, 11, 12 |
| Amazon Linux | 2, 2023 |

### Privileges
- `become: yes` (root/sudo access required on target hosts)

## 🎮 Interactive Operation

When you run the playbook, you'll be presented with this interactive menu:
