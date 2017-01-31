## A Ubuntu 16.04 specific Ansible playbook

**To run the playbook issue:**

```ansible-playbook -i <dev|prod|stage> [-K] environment_deploy.yml [--tags "a[,b[,...]]"| --skip-tags "a[,[b,...]]"]```

Please use ```ansible-playbook --help``` to get complete list of options.  

The playbook is mainly intended to be run as unprivileged user which exists on Ansible control host and has ssh keys acceptable by root user on all hosts under control.

### **WARNING! When no tags related options specified, Ansible will try to run whole playbook which may be dangerous and/or time consuming!**

**Tags available:**

- ```pass``` - set root password, if root access is not enabled requires sudo password (```-K```)
- ssh - allow ssh root access, if root access is not enabled requires sudo password (```-K```)
- root_keys - add ssh keys to hosts' /root/.ssh.authorized_keys, , if root access is not enabled requires sudo password (```-K```)
- repo_keys - add repo keys
-
