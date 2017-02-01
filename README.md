## Kinda Lorem Ipsum Ubuntu 16.04 cluster specific Ansible playbook 0:-)

**Run the playbook:**

```ansible-playbook -i <dev|prod|stage> environment_deploy.yml [--tags "a[,b[,...]]"| --skip-tags "a[,[b,...]]"]```

Please use ```ansible-playbook --help``` to get complete list of options.  

The playbook is mainly intended to be run as unprivileged user which exists on Ansible control host and has ssh keys acceptable by root user on all hosts under control.

### **WARNING! When no tags related options specified, Ansible will try to run whole playbook which may be dangerous and/or very time consuming!**

**Tags available:**

- ```upgrade``` - dist-upgrade, reboot and wait for hosts to come up **disable it in most cases!**
- ```ssh``` - add/revoke ssh keys to hosts' /root/.ssh.authorized_keys, useful
- ```repos``` - add/remove apt repos, keys, update cache, useful
- ```ntp``` - ntp related stuff, needed very seldom, no harm
- ```zabbix``` - zabbix related stuff, needed very seldom, no harm

**TBD**: Add revoke/remove functionality to ssh and repos
