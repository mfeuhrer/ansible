# Quick Start

The steps below will get a fresh system up and running with ansible quickly.

## Install ansible 

If you haven't already[^1].

	sudo apt install ansible

## Change user

You'll want an account that can run python and ssh out. It's best to have a dedicated user.[^2]

(I like `ansible` as a user.)

	su ansible

## Download this repository

	cd ~/
	git clone https://github.com/mfeuhrer/ansible.git

## Create an SSH keypair 
if you don't already have one.[^3]

	ssh-keygen

 Copy it to `authorized_keys` in the resources directory:

	echo ~/.ssh/id_rsa.pub > ~/ansible/resources/.ssh/authorized_keys

## Create an [inventory file](resources/inventory.md)
using the supported tags found in the docs folder.

	nano ~/hosts

## Ansible.cfg
Copy (or simlink) [ansible.cfg](resources/ansible.cfg.md) from the resources folder to your ansible user's home folder.

	cp ~/ansible/resources/ansible/ansible.cfg ~/ansible.cfg

or

	ln -s ~/ansible/resources/ansible/ansible.cfg ~/ansible.cfg

## Test Connections

You are now ready to run playbooks. Try the following command to validate connectivity to your hosts.

	ansible all -m ping


[^1]: Obviously I prefer debian based systems. 

[^2]: If you don't already have an account for this, one of my playbooks is an example of creating a user account at scale. You could use that playbook and target only your ansible host to create the user.

[^3]: If you're me, you'll use the existing keypair. Conveniently the correct [authorized_keys](https://github.com/mfeuhrer/ansible/blob/main/resources/.ssh/authorized_keys) file is already in this repo!