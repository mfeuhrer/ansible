# Ansible Configuration

Nothing too complicated here. Example config found [here](https://github.com/mfeuhrer/ansible/blob/main/resources/ansible/ansible.cfg).
You'll want to make sure this file is in your ansible user's home directory.

## Customizations

If you use a different username for ansible, change this line:

	remote_user = ansible

Modify this line to change where your inventory file can be found:

	inventory = $HOME/hosts
## Options

### python interpreter

	interpreter_python = auto_silent

By default, ansible will autodetect the in-user versions of python on managed devices. If no version is specified for use, ansible will throw a warning in the logs that the interpreter on the endpoint may change between runs. I don't care for the clutter in my logs. 