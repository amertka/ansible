# 🚀 Enterprise Ansible Automation Repository

![Ansible](https://img.shields.io/badge/Ansible-Automation-red)
![IaC](https://img.shields.io/badge/IaC-Infrastructure%20as%20Code-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success)

---

## 📌 Overview

This repository contains a comprehensive, modular, and production-ready **Ansible automation framework** designed to provision, configure, and manage infrastructure across multiple environments.

It follows Infrastructure as Code (IaC) best practices and is structured for scalability, reusability, and CI/CD integration.

---

## 🎯 Key Features

- ✅ Modular role-based architecture  
- ✅ Multi-environment support (dev / staging / production)  
- ✅ Custom and external Ansible collections  
- ✅ Secure secrets management with Ansible Vault  
- ✅ CI/CD friendly structure  
- ✅ Idempotent and reusable playbooks  
- ✅ Designed for production-grade infrastructure  

---

## 📁 Repository Structure

```bash
.
├── ansible.cfg
├── inventories/
│   ├── dev/
│   ├── staging/
│   └── production/
├── group_vars/
├── host_vars/
├── playbooks/
│   ├── site.yml
│   ├── bootstrap.yml
│   ├── deploy.yml
│   └── ...
├── roles/
│   ├── common/
│   ├── docker/
│   ├── kubernetes/
│   ├── postgresql/
│   ├── monitoring/
│   └── ...
├── collections/
│   └── requirements.yml
├── files/
├── templates/
└── README.md
```

---

## ⚙️ Requirements

| Requirement | Version |
|------------|----------|
| Ansible    | >= 2.14  |
| Python     | >= 3.9   |
| SSH Access | Required |
| OS         | Linux/macOS (Control Node) |

Install Ansible:

```bash
pip install ansible
```

Optional tools:

```bash
pip install ansible-lint yamllint
```

---

## 📦 Install Dependencies

### Install Collections

```bash
ansible-galaxy collection install -r collections/requirements.yml
```

### Install Roles (if using Galaxy roles)

```bash
ansible-galaxy role install -r requirements.yml
```

---

## 🌍 Environment Structure

Each environment has its own isolated inventory:

```
inventories/
  ├── dev/
  ├── staging/
  └── production/
```

Example inventory file:

```yaml
all:
  hosts:
    server1:
      ansible_host: 192.168.1.10
```

---

## ▶️ Usage

### Run Full Infrastructure

```bash
ansible-playbook -i inventories/production/hosts.yml playbooks/site.yml
```

### Run Specific Environment

```bash
ansible-playbook -i inventories/dev/hosts.yml playbooks/site.yml
```

### Run Specific Playbook

```bash
ansible-playbook -i inventories/staging/hosts.yml playbooks/deploy.yml
```

### Limit to Specific Host

```bash
ansible-playbook playbooks/site.yml \
  -i inventories/dev/hosts.yml \
  --limit server1
```

### Run Specific Tags

```bash
ansible-playbook playbooks/site.yml --tags docker
```

---

## 🔐 Secrets Management

Sensitive data is encrypted using **Ansible Vault**.

### Encrypt a file

```bash
ansible-vault encrypt group_vars/production/secrets.yml
```

### Edit encrypted file

```bash
ansible-vault edit group_vars/production/secrets.yml
```

### Run playbook with vault

```bash
ansible-playbook playbooks/site.yml \
  -i inventories/production/hosts.yml \
  --ask-vault-pass
```

Or use password file:

```bash
--vault-password-file .vault_pass
```

⚠️ Never commit plain-text secrets.

---

## 🧪 Testing & Validation

### Syntax Check

```bash
ansible-playbook --syntax-check playbooks/site.yml
```

### Dry Run

```bash
ansible-playbook playbooks/site.yml \
  -i inventories/dev/hosts.yml \
  --check
```

### Show Differences

```bash
--diff
```

### Linting

```bash
ansible-lint
```

---

## 🏗 Role Structure Standard

Each role follows Ansible best practices:

```
roles/
  my_role/
    ├── tasks/
    ├── handlers/
    ├── defaults/
    ├── vars/
    ├── templates/
    ├── files/
    ├── meta/
    └── README.md
```

### Best Practices

- Keep roles independent
- Use `defaults/main.yml` for configurable variables
- Avoid hardcoded values
- Support tags
- Maintain idempotency

---

## 🔄 CI/CD Integration

This repository is ready for integration with:

- GitHub Actions
- GitLab CI
- Jenkins
- Self-hosted runners

Example CI validation step:

```bash
ansible-playbook --syntax-check playbooks/site.yml
ansible-lint
```

---

## 🧩 Collections Management

Collections are defined in:

```
collections/requirements.yml
```

Example:

```yaml
collections:
  - name: community.general
  - name: ansible.posix
```

Install:

```bash
ansible-galaxy collection install -r collections/requirements.yml
```

---

## 🔐 Security Best Practices

- Use SSH keys (disable password auth)
- Use Ansible Vault
- Apply least privilege principle
- Avoid storing secrets in repository
- Use environment-based separation
- Restrict inventory access

---

## 🚀 Example Use Cases

This repository supports:

- 🖥 Server bootstrap
- 🐳 Docker installation & configuration
- ☸ Kubernetes cluster provisioning
- 🗄 PostgreSQL setup
- 📊 Monitoring stack deployment
- 🔁 CI/CD automation
- 🔐 Security hardening
- 🌐 Application deployment

---

## 📌 Workflow Recommendation

1. Bootstrap servers
2. Configure base system (common role)
3. Install runtime (Docker / Kubernetes)
4. Deploy databases
5. Deploy applications
6. Configure monitoring
7. Run validation

---

## 🤝 Contributing

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Open Pull Request
5. Follow role structure standards

---

## 📄 License

This project is licensed under the MIT License.

---

## 👤 Maintainer

**Amertka DevOps Yar (ADY)**

---

## ⭐ Support

If you find this repository useful:

- ⭐ Star the repository
- 🛠 Submit issues for improvements
- 🤝 Contribute new roles

---

# 🏁 Final Notes

This repository is designed to be:

- Scalable  
- Secure  
- Production-ready  
- Enterprise-grade  

Infrastructure as Code done right.

