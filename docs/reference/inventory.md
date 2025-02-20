# The Inventory

## Groups

In my playbooks, I try to target groups over individual hosts. This helps keep the playbooks flexible and scalable. 

This section aims to specify what groups I work with, and what the intent behind them is.

### `[linux]`

The linux tag is a parent group that contains any valid linux architechtures, organized by package manager. 

Playbooks that target this group should only reference common linux tasks, and should not expect any distro-specific software.

This is useful for [tasks like adding users](playbooks/linux-common.md). 

Currently defined as:

	[linux:children]
	apt
	yum

### `[apt]`

The apt tag is a group that contains valid Operating Systems that use apt as a package manager. 

Playbooks that target this group should expect common apt functions, runtimes, and commands to be available. 

Useful for [installing packages and controlling repositories](playbooks/apt-common.md). 

Currently defined as:

```
[apt:children]
ubuntu
debian
ubuntu_lxc
```

### `[proxmoxguest]`

This group contains linux virtual machines running on proxmox hosts. There is probably a better way to target these devices however.

Playbooks targeting this group can expect a virtual machine (not an lxc) running on a proxmox hypervisor.

Useful for things like [ensuring `qemu-guest-agent` is installed and running](playbooks/apt-proxguest.md). 


Currently defined as:

```
[proxmoxguest:children]
mox
kubeservers
```

### `[containerhosts]`

The containerhosts group contains groups of machines that use common docker components. 

Playbooks that target this group should expect a working Docker installation.

Useful for [making sure `docker` components are ready for monitoring](playbooks/apt-containerhosts.md).

Currently defined as:

```
[containerhosts:children]
docker
kubeservers
```

### Specific Distros 

*ex:`[Debian]`, `[Ubuntu]`, `[ubuntu_lxc]`*

A tag for a specific distribution is a group that contains only hosts running that distribution. 

Playbooks that target a specific distro group should expect the receiving device to be running that flavor of linux. 
*e.g.* referencing the `ubuntu` group should result in a list that contains *only* Ubuntu devices.

These groups are currently populated directly with hostnames.

### Specific Softwares

*ex: `[borgbackup]`, `[npm]`, `[docker]`*

Tags for specific software will install and manage that software on any endpoints defined.

Playbooks that target these groups should expect the software to be installed (or should be doing the installing).

These groups are currently populated directly with hostnames.

### `[alwayson]`

Hosts defined under this group are expected to not reboot during regular maintenance jobs. 

Mostly a trust thing. 

Useful for [applying patches and controlling reboots](linux-updates.md).