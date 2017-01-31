## A Ubuntu 16.04 specific Ansible playbook

To run the playbook issue:

```ansible-playbook -i <dev|prod|stage> -u <user> [-u root |-u <user> <-K>] environment_deploy.yml [--tags "a[,b[,...]]"| --skip-tags "a[,[b,...]]"]```

Please use ```ansible-playbook --help``` to get complete list of options.  

The playbook is mainly intended to be run as unprivileged user which has access to Ansible control host and all hosts under control.

### ***WARNING! When no tags related options specified, the playbook will try to run all roles which may be dangerous and/or time consuming!***


Tags available:
```pass``` - set root password, if root access is not enabled requires ```-u <user> -K```
ssh - allow ssh root access, if root access is not enabled requires -u <user> -K
root_keys - add ssh keys to hosts' /root/.ssh.authorized_keys, if root access is not enabled requires -u <user> -K
repo_keys - add repo keys
