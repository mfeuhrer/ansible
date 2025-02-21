# Ansible Configuration

Nothing too complicated here. Example config found [here](https://github.com/mfeuhrer/ansible/blob/main/resources/ansible/ansible.cfg).
You'll want to make sure this file is in your ansible user's home directory.

## Customizations

### remote_user

This directive tells ansible what username to use when accessing a remote machine. 

If you want to use a different username, change this value.

	remote_user = ansible

### inventory

This directive tells ansible which file to use as the default inventory.

	inventory = $HOME/hosts
## Options

### python interpreter

By default, ansible will autodetect the in-user versions of python on managed devices. If no version is specified for use, ansible will throw a warning in the logs that the interpreter on the endpoint may change between runs. I don't care for the clutter in my logs. 

	interpreter_python = auto_silent

auto_silent tells ansible to suppress the warning and accept the default behavior.