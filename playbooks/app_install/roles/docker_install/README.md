docker_install
=========

Installs Docker on a RHEL host for use as Jenkins worker node within the BEaaS environment.

Requirements
------------

- Ansible >=2.15.4
- Python >=3.9

Role Variables
--------------
In the vars/main.yml file you may set the version of Docker to install and define the packages that should be removed prior. 
- This includes items like podman, which is a conflict with docker. 

#### In the defaults/main.yml file an archive with rpms will be pulled from artifactory.

This archive needs to be defined in the vars/main.yml along with the following:
_All items have default values which are current as of 10-01-23_
---
##### _docker_version_ - The major.minor.patch version of Docker to install and contained in the artifact archive
##### _docker_rpm_src_ - either 'local' or 'artifactory'
##### _artifact_path_ - 'full url to artifact' used in combination with the prior var
##### _package_removals_ - List of all packages needing to be(possibly) removed before installing the docker packages we want to use to build images with.
##### _package_installs_ - List of the rpm files contained in the artifact archive.
- They will be prepended with the /tmp/ dir on install

