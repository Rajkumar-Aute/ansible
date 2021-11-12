# ansible
### after build master server
login into Master node and create user, (note - do not use default ubuntu user)
* create user "devops"
``` sudo adduser devops ```
* set password to the user
``` sudo passwd devops ```
* add sudo permission with no password
``` sudo visudo ```
* * update the below line in visudo file 
* * devops ALL=(ALL:ALL) NOPASSWD:ALL
* then create ssh key
``` ssh-keygen ```
  press enter for all options
* copy the ssh key to each of the nodes
``` ssh-copy-id devops@<ip-address-of-node> ```
* to test the connection
``` ssh <ip-address-of-node> ```
* * it should login without password


## Host inventory file,
* inventory file is used to mention hosts/servers to deploy the application
* we can select the inventory file using **anbile-playbook -i <inventory-file>** option. 
* The file can be written in ini / yaml format.
```ini
[web-servers]
192.168.1.10
[db-server]
192.168.1.20

```yaml
---
all:
  hosts:
    192.168.1.1
  children:
    web-servers:
      hosts:
        192.168.1.10
    db-servers:
      hosts:
        192.168.1.20
```
* we can list the host using
```
ansible -i <inventory-file> all --list-hosts
```
* we can set range of host ex - [01:100]
* official doc [reffer hear](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)






