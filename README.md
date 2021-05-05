# Ansible role for common Ubuntu maintenance and configuration
This role is for configuring and maintaining
Ubuntu hosts. Common tasks include:
- apt updates and package management
- pip updates
- timezone configuration
- DNS configuration (optional)
- prerequisites for common Ansible modules

# Requirements
Provisioning host:
- ansible 2.9 or later

Host that will be configured:
- Ubuntu 18.04 or later

# How to use this role
### Method 1: Install using ansible-galaxy
The most robust way to install this role is to use ansible-galaxy,
which is installed with ansible by default. ansible-galaxy is effectively a package manager for ansible. It installs roles
from the community, or from private git repos, into your local machine for use in your playbooks.

Start by adding this role to an ansible-galaxy dependency file. Typically this file lives alongside your playbook file and by convention is named `requirements.yml`.

Add the following section to `requirements.yml`:

```
roles:
  - name: creator-ubuntu-common-ansible
    src: git+git@github.com:creatoreng/creator-ubuntu-common-ansible.git
    version: main
```

If there is already a `roles` section, simply append this role to
add it as a dependency.

Then, install the role using ansible-galaxy:

`ansible-galaxy install -r requirements.yml -f -v`

### Method 2: Clone this repository into a `roles` directory

Use this method if you plan to modify this role, or if for some
reason the ansible-galaxy method fails.

Starting from your playbook directory, change into the `roles`
directory and clone this repo. *Be sure to add `roles` to your
`.gitignore` so you don't duplicate this role in your repository.*

```
cd roles/
git clone git@github.com:creatoreng/creator-ubuntu-common-ansible.git
```
