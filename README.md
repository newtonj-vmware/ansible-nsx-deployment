# NSX Lab-Deployment using Ansible -WIP-
Please note this is a Work in Progress (WIP) - All files are set to run on the Ansible Control System (local) and is currently NOT using an ansible.cfg file.
Not all Remove playbooks work (Tier0 removal)

However it will fully deploy a NSX environment from nothing to fully deployed T0s/T1s and segments connected to either. 

## NSX Compatibility
The following versions of NSX are supported:

* NSX-T 4.0 (Tested against 4.0.1) [8/17/2022]
* NSX-T 3.2 (Tested against 3.2.0.1 & 3.2.1) [5/19/2022]
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
Pulling master collection due to error in the v3.2.0 branch
ansible-galaxy collection install git+https://github.com/vmware/ansible-for-nsxt.git,master
```
## Usage

Please do NOT populate the answerfile.yml, so that you can use git pull to get latest files.   Save file with deployment name e.g. mylab01-answerfile.yml
A Copy of the answerfile.yml is also located in the example directory

Use the -e @mylab01-answerfile.yml for deployments - 
Example: ansible-playbook -e @answerfile-lab1.yml -e nsx_liscense="XXXXX-XXXXX-XXXXX-XXXXX-XXXXX" deploy-nsx-32.yml  (Add different license)
