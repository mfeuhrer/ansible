## Ansible Galaxy

Ansible supports externally and community maintained collections, which can be pre-defined playbooks, roles, modules or plugins. `ansible-galaxy` is the command used to control these. 

If a collection is required by a playbook, ensure the collection is installed by running:

	ansible-galaxy collection install $collectionName

To review what collections exist on your system, as well as those available within the universe, run:

	ansible-galaxy collection list

## Collections in use:

### borgbase

borgbase is a management layer on top of borg backup that makes using borg backup easier to use. Install with:

	ansible-galaxy collection install borgbase