# Common linux configurations

This playbook is only designed to set configuration items that are applicable to any linux system.

##  Quick run

	ansible-playbook ansible/playbooks/linux-common.yml

## Current Tasks

- Set hostname based on inventory hostname
- Create ansible user account
	- Grant passwordless sudo access
	- Ensure ssh public key is current
- Create warpgate user account
	- Ensure ssh public key is current