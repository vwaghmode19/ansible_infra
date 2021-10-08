# Ansible Roles:
=========

1. java: Install java based upon ansible_os_family viz Debian, Windows
2. jenkins-master: Set up jenkins master environment on Unix server. Here its for Debian system
3. jenkins-slave: Set up jenkins slave based upon ansible_os_family viz Debian, Windows

Prerequisites:
------------

1. Password less ssh from Ansible controller to remote machine is required.
2. WinRM set up on windows hosts 

Role Variables:
--------------

All are defined under defaults/ and vars/ of each role.

Dependencies:
------------

1. For java Role: NA
2. For jenkins-master Role: java role
3. For jenkins-slave Role: 
		- java role
		- Jenkins Master should be running on Unix Box.

Example Playbook:
----------------

---
- name: Jenkins Master
  hosts: jenkins-master
  gather_facts: yes
  roles:
    - java
    - jenkins-master

- name: Jenkins Slave
  hosts: jenkins-slave
  vars_files:
    - vault/dev.yml
  gather_facts: yes
  roles:
    - java
    - jenkins-slave
...

References:
----------------

geerlingguy/ansible-role-jenkins -- > https://github.com/geerlingguy/ansible-role-jenkins
johnbuhay/setup-users.groovy -- > https://gist.github.com/johnbuhay/c6213d3d12c8f848a385
winsw/winsw -- > https://github.com/winsw/winsw


License:
-------

BSD

Author Information:
------------------

Name: V Waghmode
Email: vwaghmode19@gmail.com


