# Ansible Playbooks

This repository can be cloned to an ansible control server. 

When paired with an appropriately configured inventory file, devices can be configured how I like them. 

## Repository Structure

### docs

Documentation tree. This is where how-to's and explanations are stored. 

### playbooks

Self-explanatory. These are the defintions. 

### resources

Files and templates used by the playbooks on the remote machines. Playbooks will fail if this is missing.

## Quick Start

1. Install the ansible if you haven't already.
	
		sudo apt install ansible

2. Log into your ansible control node as the user you want to run playbooks as. (I like `ansible` as a user.)

		su ansible

3. Download this repository

		cd ~/
		git clone https://github.com/mfeuhrer/ansible.git

4. Create an SSH keypair if you don't already have one[^1]

		ssh-keygen

	Copy it to the resources folder:

		cp ~/.ssh/id_rsa.pub ~/ansible/resources/.ssh/id_rsa.pub

5. Create a [inventory file](./docs/inventory.md), using the supported tags found in the docs folder.

		nano ~/hosts

6. Copy (or simlink) [ansible.cfg](./docs/ansible.cfg.md) from the resources folder to your ansible user's home folder.

		cp ~/ansible/resources/ansible/ansible.cfg ~/ansible.cfg

	or

		ln -s ~/ansible/resources/ansible/ansible.cfg ~/ansible.cfg

7. You are now ready to run playbooks. Try the following command to validate connectivity to your hosts.

		ansible all -m ping


[^1]: If you're me, you'll use the existing keypair. Conveniently the correct [id_rsa.pub](./resources/.ssh/id_rsa.pub) is already in this repo!