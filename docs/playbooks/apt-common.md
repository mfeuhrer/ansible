# Common configuration for apt based systems

This is the main configuration for baseline desired state on apt based linux.

##  Quick run

	ansible-playbook ansible/playbooks/apt-common.yml
## Current Tasks

- Install packages
	- apt-transport-https
	- ca-certificates
	- curl
	- gnupg
	- software-properties-common
	- ufw
	- snmpd
	- htop
	- git
- Remove packages
	- netadata
	- wazuh-agent
	- landscape-client
- Configure SNMP
	- Install extra monitoring modules for librenms