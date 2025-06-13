# Ansible Baseline Collection

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build](https://github.com/Scalified/ansible-baseline/actions/workflows/build.yml/badge.svg)](https://github.com/Scalified/ansible-baseline/actions)
[![Release](https://img.shields.io/github/v/release/Scalified/ansible-baseline?style=flat-square)](https://github.com/Scalified/ansible-baseline/releases/latest)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-scalified.baseline-blue.svg)](https://galaxy.ansible.com/scalified/baseline)

An Ansible collection for basic server setup and configuration tasks. This collection provides essential roles for initializing and configuring servers with common baseline settings

## Requirements

- **Ansible:** >= 2.15.0
- **Python:** >= 3.6
- **Target OS:** Debian
- **Privileges:** Most roles require `become: true` (sudo access)

## Installation

### Ansible Galaxy

```bash
ansible-galaxy collection install scalified.baseline
```

### Git Repository

```bash
ansible-galaxy collection install git+https://github.com/scalified/ansible-baseline.git
```

### Requirements File

`requirements.yml`:
```yaml
---
collections:
  - name: scalified.baseline
    version: ">=1.0.0"
```

```bash
ansible-galaxy collection install -r requirements.yml
```

## Usage

### Playbooks

```yaml
---
- name: Run baseline configuration
  #include: scalified.baseline.playbook
  import_playbook: scalified.baseline.playbook
  vars:
    baseline_hosts: all
```

#### Variables

| Variable         | Description              | Default Value | Required |
|------------------|--------------------------|---------------|----------|
| `baseline_hosts` | Target hosts or groups   | `all`         | No       |

### Roles

```yaml
---
- name: Configure servers
  hosts: all
  roles:
    - scalified.baseline.system
```

#### Variables

| Variable          | Description                       | Default Value        | Required |
| ----------------- | --------------------------------- | -------------------- | -------- |
| `system_hostname` | Hostname to set on target servers | `{{ ansible_host }}` | No       |


## License

```
MIT License

Copyright (c) 2025 Scalified

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

## Support

* [Scalified](http://www.scalified.com)
* [Scalified Official Facebook Page](https://www.facebook.com/scalified)
* <a href="mailto:info@scalified.com?subject=[Ansible Baseline Collection]: Proposals And Suggestions">Scalified Support</a>

---

**Made with ❤️ by [Scalified](http://www.scalified.com)**
