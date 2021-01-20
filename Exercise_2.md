# EXERCISE 2

## Inventory

| Hostname | Group | IP |
|:---------|:------|:---|
| control.ansible.loc | control | 192.168.33.100 |
| web1.ansible.loc | webservers | 192.168.33.10 |
| web2.ansible.loc | webservers | 192.168.33.20 |
| proxy.ansible.loc | proxy | 192.168.33.30 |
| database.ansible.loc | database | 192.168.33.40 |


## Questions

- Use ad hoc command to get all mounts and all block devices for all hosts in inventory
- Use ad hoc command to check if `crond` service is up on `web1.ansible.loc`
- Use ad hoc command to display `/etc/motd` for all hosts
- Use ad hoc command to get the facts variabile name of memory free and ip address of `eth1`
- Create a playbook that change the file hosts of all servers. This playbook should add a line for every host in inventory:

    `192.168.33.10 web1.ansible.loc web1`

  You should get IP address and name from facts and/or special Ansible variables.

  Use `lineinfile` module for this exercise.

- Create a playbook to install `developments tools` and `system roles`
- Create a playbook to change the content of `/etc/motd`, with the following line:

    _This hosts is a webserver_

  The line should change foreach group in inventory: control, webservers, proxy, database
