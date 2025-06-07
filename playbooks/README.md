# Playbooks

Playbooks for baseline server configuration

## Usage

```yaml
---
- name: Run baseline configuration
  #include: scalified.baseline.playbook
  import_playbook: scalified.baseline.playbook
  vars:
    baseline_hosts: all
```

## Variables

| Variable         | Description              | Default Value | Required |
|------------------|--------------------------|---------------|----------|
| `baseline_hosts` | Target hosts or groups   | `all`         | No       |
