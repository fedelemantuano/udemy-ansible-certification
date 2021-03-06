# EXERCISE 3

## Inventory

| Hostname | Group | IP |
|:---------|:------|:---|
| control.ansible.loc | control | 192.168.33.100 |
| web1.ansible.loc | webservers | 192.168.33.10 |
| web2.ansible.loc | webservers | 192.168.33.20 |
| proxy.ansible.loc | proxy | 192.168.33.30 |
| database.ansible.loc | database | 192.168.33.40 |


## Questions

- Install and configure NTP client with role `rhel-system-roles.timesync`.
  Setup it for fast initial synchronization with following server:
   - 0.it.pool.ntp.org
   - 1.it.pool.ntp.org
   - 2.it.pool.ntp.org
   - 3.it.pool.ntp.org

  Run the playbook on all hosts.

- Make a role that install and configure `firewalld`. The role should enable service and open a ports list. Set as default port 80/TCP.
  If you want, you can see the [linux-system-roles-firewall](https://github.com/linux-system-roles/firewall) implementation.

- Make a playbook that uses the `firewall` role and opens port 80/TCP. Then install web server Apache and adds the file `/var/www/html/index.html`.
  This file should have a line with hostname and IP address of eth1:

  _This is web1.ansible.loc server on ip address 192.168.33.10_

  Run the playbook on `webservers` group.

- Make a playbook that use [geerlingguy.haproxy](https://galaxy.ansible.com/geerlingguy/haproxy) to install and configure [HAProxy](http://www.haproxy.org/). This playbook should balance the webservers in group inventory on port 80/TCP. Remember to open port 80/TCP with your role.

- Make a playbook that use [geerlingguy.postgresql](https://galaxy.ansible.com/geerlingguy/postgresql) to install and configure [PostgreSQL](https://www.postgresql.org/).

  Use the role firewall to open the PostgreSQL port (5432/TCP).

  Create a database `udemy` and a user `udemy_user` with password `udemy_password`. This user should connect to database from control node, so you should install `postgresql` and bind database server to `*`. To do that you should use `postgresql_global_config_options` variable and use `listen_addresses` option.

  It's also important change a line of default role variable `postgresql_hba_entries`:

  ```
  postgresql_hba_entries:
    ...
    - {type: host, database: all, user: all, address: '192.168.33.0/24', auth_method: md5}
    ...
  ```

  Then try to connect to database from control node with the following command:

  ```
  [vagrant@control ansible]$ psql -h database.ansible.loc -d udemy -U udemy_user
  Password for user udemy_user:
  psql (9.2.24)
  Type "help" for help.

  udemy=>
  ```
