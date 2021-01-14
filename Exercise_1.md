# EXERCISE 1

## Inventory

| Hostname | Group | IP |
|:---------|:------|:---|
| control.ansible.loc | control | 192.168.33.100 |
| web1.ansible.loc | webservers | 192.168.33.10 |
| web2.ansible.loc | webservers | 192.168.33.20 |
| proxy.ansible.loc | proxy | 192.168.33.30 |
| database.ansible.loc | database | 192.168.33.40 |


## Questions

- Install Ansible on control node
- Create a path on control node with all configuration and playbooks (`/home/vagrant/ansible`)
- Copy defaut file `ansible.cfg` in local project path
- Change path where Ansible search for roles in `roles` in local path
- Change the default Ansible inventory in `inventory` in local path
- Disable privilege escalation by default
- Ansible should connect to nodes using `vagrant` user
- Create the `inventory` file as in inventorty table
- Test all hosts with Ansible ping
