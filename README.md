# Ansible Project Skeleton & NTP Configuration

A modular **Ansible automation repository** for quickly generating new playbook skeletons and managing time synchronization across hosts.

## 📌 Features

### 1️⃣ Create Playbook Structure
- Scaffold a complete Ansible project with standard directories and files.
- Auto-generate inventory files for multiple environments.
- Pre-fill role subdirectories with starter `main.yml` files.

### 2️⃣ Configure NTP / Chrony
- Install and configure NTP or Chrony.
- Set system timezone.
- Enable & start the service.
- Verify sync status with clear output.

---

## 📂 Repository Layout
```
.
├── create_playbook_structure.yml   # Generate new project skeleton
├── ntp_playbook.yml                 # Configure time sync services
├── inventory/
│   └── ntp_hosts                    # Hosts for NTP role
├── roles/
│   ├── create_playbook_structure/   # Playbook generator role
│   └── ntp/                         # NTP configuration role
└── README.md
```

---

## 🚀 Quick Start

### Create New Project Skeleton
```bash
ansible-playbook create_playbook_structure.yml
```
Follow the prompts to set **project path** and **name**.

### Deploy NTP/Chrony Config
```bash
ansible-playbook ntp_playbook.yml -i inventory/ntp_hosts
```

---

## ⚙️ Variables
Set in `roles/ntp/defaults/main.yml` or override via inventory:
```yaml
ntp_package: chrony
ntp_config: /etc/chrony.conf
ntp_service: chronyd
ntp_timezone: "UTC"


