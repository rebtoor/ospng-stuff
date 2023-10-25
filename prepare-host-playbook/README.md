# prepare-host-playbook

## About this playbook

This playbook will help a user to prepare an environment to test the EDPM deployment.

## Requirements

- A recent ansible-core version (2.14.x)
- A Fedora 38 based hypervisor (untested with other OS yet, untested with nested virtualization)
- A passwordless key based ssh root access to that hypervisor (or with another user that can escalate privileges without password)

## Prepare the inventory

- In the `inventory` file, replace the value of `ansible_host` with the address of the hypervisor on both `remoteHost` and `remoteHostUser` lines. If the available user isn't root, change the `ansible_user` value ***only for the `remoteHost` line***, but you need to be sure that that user can escalate privileges without any password.

## Launch the playbook

`ansible-playbook prepare-host-playbook.yml`

...wait :)

## Try to login to remote host with new user

```
ssh ospng@$REMOTEHOST
```

## Issues and collaboration

File an issue here on github if you encounter any problems

Feel free to open PR with patches!