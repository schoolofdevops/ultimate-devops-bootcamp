### Applying common configurations to all hosts

In this section we are going to running comman playbook for all host. we have alredy have inventory as part of of environment file. when we apply code is always from of playbook.

```
---
  - name: common configurations for all nodes
    hosts: all
    become: true
    roles:
      - common
```

this playbook defines for the common role

roles/common/tasks/main.yml

```
---
# tasks file for common
- import_tasks: packages-Debian.yml
  when: ansible_os_family == 'Debian'

- import_tasks: env-Debian.yml
  when: ansible_os_family == 'Debian'

- import_tasks: supervisor.yml
  when: ansible_os_family == 'Debian'

```

apply commom palyvook


```
ansible-playbook common.yaml
```
