docker_install
=========

Installs Docker on a RHEL host for use as Jenkins worker node within the BEaaS environment.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------
In the vars/main.yml file you may set the version of Docker to install and define the packages that should be removed prior. 
- This includes items like podman, which is a conflict with docker. 

In the defaults/main.yml file you may set or remove the proxy settings that may be required to reach the necessary repository sources
- The standard Lab proxy is defined by default, but **should** be removed if not required.


