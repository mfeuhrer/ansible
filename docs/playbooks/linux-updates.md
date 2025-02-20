#  Linux package updates

This playbook targets both apt and yum based distributions.

##  Quick run

	ansible-playbook ansible/playbooks/apt-common.yml

##  Current tasks

- Search for available updates
- Apply available updates
- Run package manager autoremove
- Reboot endpoints[^1]

[^1]: If any of the updates require a reboot, the endpoint will reboot, unless the host belongs to the [inventory group](../reference/inventory.md#alwayson) `always on`.