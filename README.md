# Enterprise Automated Server Patching Framework

An enterprise-grade, cross-platform Ansible automation framework for safe, predictable, and audited server patching.

## Features
* **Cross-Platform:** Native support for RHEL/Amazon Linux (`dnf`/`yum`) and Debian/Ubuntu (`apt`).
* **Pre-Patching Health Checks:** Validates disk space (>20% required) and records running services.
* **Smart Reboots:** Automatically detects if a kernel update requires a reboot and handles it gracefully.
* **Post-Patching Validation:** Compares pre/post package states and ensures critical services are back online.
* **Rolling Updates:** Patches nodes sequentially (`serial: 1`) to prevent infrastructure downtime.

## Directory Structure
```text
.
├── ansible.cfg                # Core Ansible configurations
├── hosts.yml                  # YAML-based dynamic/static inventory
├── site.yml                   # Master execution playbook
├── group_vars/
│   └── all.yml                # Global variables (services, security toggles)
├── logs/                      # Automated execution logs
└── roles/
    ├── pre_checks/            # System health baseline tasks
    ├── patching/              # OS-agnostic patching logic
    └── post_checks/           # Verification and reporting