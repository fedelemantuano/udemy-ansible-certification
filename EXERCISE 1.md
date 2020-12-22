# EXERCISE 1

## Inventory

| Hostname | Group | IP |
|:---------|:------|:---|
| control.ansible.loc | webservers | 192.168.10.100 |
| web1.ansible.loc | webservers | 192.168.10.10 |
| web2.ansible.loc | webservers | 192.168.10.20 |
| proxy.ansible.loc | webservers | 192.168.10.30 |
| database.ansible.loc | database | 192.168.10.40 |


## Questions

- Install Ansible on control node (yum and pip)
- Create a path on control node with all configuration and playbooks
- Copy defaut file `ansible.cfg` in local project path
- Change path where Ansible search for roles in `roles` in local path
- Change the default Ansible inventory in `inventory` in local path
- Disable privilege escalation by default
- Ansible should connect to nodes using `vagrant` user
- Create SSH keys to use with Ansible. Change `ansible.cfg`
- Add a second disk to `web1.ansible.loc`
- Create the `inventory` file as in inventorty table