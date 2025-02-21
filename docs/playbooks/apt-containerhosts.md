# Configuration for apt based container hosts

This playbook is meant to be run against machines expected to be running docker applications.

## Quick run

	ansible-playbook ansible/playbooks/apt-containerhosts.yml
## Current tasks

- Install distribution accurate official Docker repository gpg key
- Configure distribution accurate official Docker repo
- Install packages
	- python3
	- python3-pip
	- python3-dateutil
	- python3-docker
	- docker-ce
- Configure docker SNMP modules
- Restart SNMP