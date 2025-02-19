# Configuration for apt based proxmox guests

This playbook is meant to be run against apt based proxmox guest virtual machines. 

Untested (and likely not needed) for lxc containers.

##  Quick run

	ansible-playbook ansible/playbooks/apt-proxguest.yml

## Current Tasks

- Installs and starts qemu-guest-agent service
- Removes open-vm-tools if found