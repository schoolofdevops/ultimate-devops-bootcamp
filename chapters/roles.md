### Roles for modular configurations

Now is the time to start creating modular, reusable library of code for application configurations. In this chapter, we are going to write such modular code, in the form of roles and setup application server.

We are going to create the roles with following specs,

* frontend
* catalogue
* cart

* Create roles directory

```
mkdir roles
```

* Generate role scaffolding using ansible-galaxy

```
ansible-galaxy init --offline --init-path=roles  frontend
```

* Validate

```
tree roles/
```

[output]

```
  roles/
    └── apache
        ├── defaults
        │   └── main.yml
        ├── files
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── README.md
        ├── tasks
        │   └── main.yml
        ├── templates
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml
```

### Playbooks to map hosts to roles

Create a playbook for app servers frontend.yaml , with following contents

```
  ---
  - hosts: frontend
    become: true
    roles:
      - frontend
```

```
  ansible-playbook frontend.yml

```

