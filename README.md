# rpi-ansible
Ansible playbooks to automate setting up a Raspberry Pi

## Configuration

1. Fill out [hosts](hosts) file.
1. Fill out [vault.yml](group_vars/all/vault.yml).
1. Encrypt vault: `ansible-vault encrypt group_vars/all/vault.yml`

## Set Up a New Pi

```
ansible-playbook -vvKk playbooks/setup.yml
```

The `-Kk` prompts for ssh & sudo password. This is necessary for the initial setup, as the password has not yet been set to `custom_user_pass`.

## Lock Down a Pi
```
ansible-playbook -vv playbooks/security.yml
```

## Just Upgrade Packages
```
ansible-playbook -vv playbooks/upgrade.yml
```