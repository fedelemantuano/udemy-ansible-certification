# EXERCISE 4

## Inventory

| Hostname | Group | IP |
|:---------|:------|:---|
| control.ansible.loc | control | 192.168.33.100 |
| web1.ansible.loc | webservers | 192.168.33.10 |
| web2.ansible.loc | webservers | 192.168.33.20 |
| proxy.ansible.loc | proxy | 192.168.33.30 |
| database.ansible.loc | database | 192.168.33.40 |


## Questions

- Create a vault file `udemy_users.yml` in `vars` folder with a list of users:

  ```
  udemy_users:

  - name: udemy1
    password: udemy1
    shell: /bin/bash

  - name: udemy2
    password: udemy2
    shell: /bin/sh

  - name: udemy3
    password: udemy3
    shell: /bin/zsh
  ```

  To encrypt this file use the password `udemy_to_change`.

- Use the correct command to rekey the vault file with the new password `u4emy!`.

- Create a playbook that use the vault password and create the users.
  The password of users should be converted into password hash with `password_hash` filter passing `SHA512` function.
  When run the playbook use a file to decrypt the vault, without to prompt password.
  Run the playbook on control node.
