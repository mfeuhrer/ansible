# Configuration for apt based container hosts

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