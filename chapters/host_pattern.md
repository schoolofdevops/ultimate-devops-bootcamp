### Inventories and host patterns

In this section we are going to Deploy applications frontend , carts and catalogue. The part of the code is alredy avaible that repo. we have alredy cloned. we just provide some commom configuration.


Following is our recommended layout for organizing your ansible code. There are a couple of alternatives as discusses on [official documentation](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#directory-layout)

```
ansible
   |\
   | |_ environments
   |         \
   |          |_ dev
   |          |
   |          |_ prod
   |
   |
   |\
   | |_ group_vars
   |        \
   |         |_ all
   |         |
   |         |_ dev
   |         |
   |	     |_ prod
   |
   |\
   | |_ roles
   |        \
   |         |_ app1
   |         |
   |         |_ app2
   |
   |
   |\
   | |  
   |  \
   |   |_ playbook1.yml
   |   |
   |	 |
   |   |_ playbook2.yml
   |
   |
   |
   |_ _ ansible.cfg


```

This is the place where you would add your inventories

```
ansible 
   \
     environments
            \
             |_ dev
	     |
	     |_ prod
```

then try to ping using following command

```
ansible all -m ping
```
[output]

```
lb | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
frontend | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
carts | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
catalogue | SUCCESS => {
    "changed": false,
  
```

patterns


```
ansible 'frontend' -m ping

ansible 'dev' -m ping

ansible 'dev:!frontend' -m ping

ansible 'carts:frontend' -m ping

```

