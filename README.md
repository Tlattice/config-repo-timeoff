### config-repo-timeoff
Configurations for time-off project.


## Repo structure
https://docs.ansible.com/ansible/2.8/user_guide/playbooks_best_practices.html#alternative-directory-layout

## Inventory
Dynamic inventory script:
```
wget https://raw.githubusercontent.com/ansible/ansible/stable-2.8/contrib/inventory/ec2.py
mv ec2.py inventories/timeoff/ec2.py
chmod +x inventories/timeoff/ec2.py
```

```
wget https://raw.githubusercontent.com/ansible/ansible/stable-2.8/contrib/inventory/ec2.ini
mv ec2.ini inventories/timeoff/ec2.ini
```

https://raw.githubusercontent.com/ansible/ansible/stable-2.8/contrib/inventory/ec2.ini
https://docs.ansible.com/ansible/2.8/user_guide/intro_dynamic_inventory.html#inventory-script-example-aws-ec2

### Usage

```
ansible -i inventories/timeoff/hosts --list-hosts
```
```
ansible -i inventories/timeoff/hosts jenkins -m ping
ansible-playbook -i nventories/timeoff/hosts <playbook>
```
```
ansible-playbook -i inventories/hosts.ini playbooks/install_jenkins.yaml
```

### Jenkins-git integration

- install plugin 'Github Pull Request Builder'
