# Automation with Ansible

## Description

- This is an interactive playbook and it creates a new droplet on Digital Ocean.
- It also adds freshly created server to the inventory file.
- You can generate new tasks for the new server in the same playbook.

## Prerequisites

- Digital Ocean API Token

[Generate a New Token](https://cloud.digitalocean.com/account/api/tokens?i=da3295&preserveScrollPosition=true)

- SSH ID

[GET Request for SSH ID](https://docs.digitalocean.com/reference/api/api-reference/#tag/SSH-Keys)

## Writing the playbook

You can use "[digital_ocean](https://docs.ansible.com/ansible/2.9/modules/digital_ocean_module.html)" module from the original Ansible documentation to create a new droplet.

There are many other options and modules for you to check on "[community.digitalocen](https://docs.ansible.com/ansible/latest/collections/community/digitalocean/index.html)" to add more options for your droplet like tags, project, block storage, firewall etc.

# Introduction to Ansible Vault

Ansible Vault encrypts variables and files so you can protect sensitive content such as passwords or keys rather than leaving it visible as plaintext in playbooks or roles. 

## How it works?

First, you should create a playbook to store your keys, passwords etc. and give them variables. (EX: keys.yaml under ‘vars’ file)

To encrypt ‘keys.yaml’ file, run the following:                                            

```
ansible-vault encrypt vars/keys.yaml
```

Now, if you want to run you playbook which includes encrypted vars file, you need to give a password.

Use --ask-vault-pass to supply the vault password at runtime

```
ansible-playbook provision.yaml --ask-vault-pass
```
After supplying the password, Ansible decrypts the vault and runs the playbook with the decrypted data. 

You can edit the encrypted file with ```ansible-vault edit``` You can also ```rekey``` a file (change its password), ```create``` a new file, ```view``` an existing file, or ```decrypt``` a file.

All these commands work with one or multiple files .

```
ex: ansible-vault edit x.yaml y.yaml z.yaml
```

## Contribution

Feel free to clone this and contribute.

```
https://github.com/snurer/ansible_playbooks.git
```
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Thank you!





