# System

Configures basic system settings such as:

  * hostname

## Usage

```yaml
---
- name: Configure servers
  hosts: all
  roles:
    - scalified.baseline.system
```

## Variables

| Variable          | Description                       | Default Value        | Required |
| ----------------- | --------------------------------- | -------------------- | -------- |
| `system_hostname` | Hostname to set on target servers | `{{ ansible_host }}` | No       |
