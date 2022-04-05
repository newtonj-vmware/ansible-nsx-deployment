# NSX Lab-Deployment using Ansible -WIP-

## NSX Compatibility
The following versions of NSX are supported:

* NSX-T 3.2 (Tested against 3.2.0.1)
* NSX-T 3.1 (Tested against 3.1.3.7)
* NSX-T 3.0 (Not Tested - Should Work)
* NSX-T 2.5.1 (Not Tested - Time for you to upgrade... seriously.. 2.5?!?!) 

## Prerequisites

Using Ansible-for-nsxt requires the following packages to be installated. Installation steps differ based on the platform (Mac/iOS, Ubuntu, Debian, CentOS, RHEL etc). Please follow the links below to pick the right platform.

* Ansible >= 2.9.x [Ansible Installation Documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
* Python3 >= 3.6.x [Python Documentation](https://www.python.org/downloads/)
* pip >= 9.x Python Installation [PIP installation](https://pip.pypa.io/en/stable/installing/)
* PyVmOmi - Python library for vCenter api. Installation via pip: [pyVmomi installation](https://pypi.org/project/pyvmomi/)
* OVF Tools >= 4.4.x - Ovftool is used for ovf deployment [OVFTool Download and Installation](https://code.vmware.com/web/tool/4.4.0/ovf)

## Installation

ansible-for-nsxt modules are distributed as Ansible Galaxy collection. Please use the following command to install it

```
ansible-galaxy collection install git+https://github.com/vmware/ansible-for-nsxt
```

Specify latest supported release branch

```
ansible-galaxy collection install git+https://github.com/vmware/ansible-for-nsxt.git,v3.2.0
```
