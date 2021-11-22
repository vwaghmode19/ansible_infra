# Ansible Roles:

1. java: Install java based upon ansible_os_family viz Debian, Windows
2. jenkins-master: Set up jenkins master environment on Unix server. Here its for Debian system
3. jenkins-slave: Set up jenkins slave based upon ansible_os_family viz Debian, Windows

# Prerequisites:

1. Password less ssh from Ansible controller to remote machine is required.
2. WinRM set up on windows hosts 

# Role Variables:

All are defined under defaults/ and vars/ of each role.

# Dependencies:

1. For java Role: NA
2. For jenkins-master Role: java role
3. For jenkins-slave Role: 
		- java role
		- Jenkins Master should be running on Unix Box.

# Example Playbook:

Please check jenkins_site.yml

`- \n
  Host: 10.110.10.110 \n
  Deployments: \n
    - Name: ms_sql \n
    - Name: keycloak \n
    - Name: nice_extractor \n
`

# References:

1. geerlingguy/ansible-role-jenkins -- > https://github.com/geerlingguy/ansible-role-jenkins
2. johnbuhay/setup-users.groovy -- > https://gist.github.com/johnbuhay/c6213d3d12c8f848a385
3. winsw/winsw -- > https://github.com/winsw/winsw


# License:

BSD

# Author Information:

Name: V Waghmode
Email: vwaghmode19@gmail.com


