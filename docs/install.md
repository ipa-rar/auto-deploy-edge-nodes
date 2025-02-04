# Installation & Requirements
1. Install Ansible as desired based on what is specified in [their official documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).
It can be with your OS packet manager, or even through PIP.
2. OpenSSH server is required for every single machine. Therefore make sure to have it,
or install it by running:
```bash
sudo apt install openssh-server
```
3. In the master machine, create for Ansible an ssh key to ensure connection with
the remotes. Give it the desired name, comment, and no passphrase. In this example
the name and comment will be "ansible".
```bash
ssh-keygen -t ed25519 -C "ansible"
```
4. Copy the new generated ssh-key into the remote machines.
```bash
ssh-copy-id -i `file .pub` `username@ip_address`
```

Steps 2 and 4 could be setup instead at the time of the RPI Ubuntu installation and 
configuration steps.
