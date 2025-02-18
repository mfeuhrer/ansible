# Ansible Configuration

Nothing too complicated here. Exmaple config found [here](../resources/ansible/ansible.cfg).
You'll want to make sure this file is in your ansible user's home directory.

## Customizations

If you use a different username for ansible, change this line:

        remote_user = ansible

Modify this line to change where your inventory file can be found:

		inventory = $HOME/hosts