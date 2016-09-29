# bp-test

vagrant and ansible test

To clone this repository:

$ git clone git@github.com:mccaffrs/bp-test.git

$ cd bp-test/

$ vagrant up

URL: http://localhost:8080

Also need to look at this as a possible better option:

https://github.com/ansible/ansible-container


Ongoing problem trying to use vagrant with ansible provisioner from a windows machine:

$ vagrant provision
==> default: Running provisioner: ansible...
Windows is not officially supported for the Ansible Control Machine.
Please check https://docs.ansible.com/intro_installation.html#control-machine-requirements
    default: Running ansible-playbook...
PYTHONUNBUFFERED=1 ANSIBLE_FORCE_COLOR=true ANSIBLE_HOST_KEY_CHECKING=false ANSIBLE_SSH_ARGS='-o UserKnownHostsFile=/dev/null -o IdentitiesOnly=yes -o ControlMaster=auto -o ControlPersist=60s' ansible-playbook --connection=ssh --timeout=30 --limit="default" --inventory-file=C:/cygwin/home/Steve/bp-test/.vagrant/provisioners/ansible/inventory -v install-docker.yml
The Ansible software could not be found! Please verify
that Ansible is correctly installed on your host system.

If you haven't installed Ansible yet, please install Ansible
on your host system. Vagrant can't do this for you in a safe and
automated way.
Please check https://docs.ansible.com for more information.

