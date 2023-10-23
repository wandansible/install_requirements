Ansible role: install\_requirements
===================================

Install ansible role and collection requirements from requirements.yml
with ansible-galaxy on the host running ansible playbooks.

Role Variables
--------------

```
ENTRY POINT: main - Install ansible requirements with ansible-galaxy.

        Install ansible role and collection requirements from
        requirements.yml with ansible-galaxy.

OPTIONS (= is mandatory):

- install_requirements_ansible_playbook_dir
        Path to ansible playbook directory
        default: '{{ ansible_config_file | dirname }}'
        type: str
```

Installation
------------

This role can either be installed manually with the ansible-galaxy CLI tool:

    ansible-galaxy install git+https://github.com/wandansible/install_requirements,main,wandansible.install_requirements

Or, by adding the following to `requirements.yml`:

    - name: wandansible.install_requirements
      src: https://github.com/wandansible/install_requirements

Roles listed in `requirements.yml` can be installed with the following ansible-galaxy command:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

    - hosts: all
      roles:
        - role: wandansible.install_requirements
      gather_facts: false
      run_once: true
      become: false
