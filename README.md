# Ansible-Docker-Host
===================
Ansible Role for Docker Host setup

## Description
This is a simple role playbook creating a docker-host 

## Dependencies
This role has been tested in an environment with the following components
 * Ubuntu v12.04 or above
 * Ansisble v1.7
 * Docker v1.1.1
 * Python v2.7

## Note
This role introduces `/etc/default.docker.ext` as an extension to provide custom docker options during the startup of docker service.

## Quick start
As this is a completely self contained playbook delivering a working private docker host using the default configurations. Follow the steps below get running:
*  run the playbook: ` ansible-playbook -i hosts site.yml`
  
That will use the
[official image from the Docker index](https://index.docker.io/_/registry/).

## Known Issues
No known issues

## Under the bonnet
### Key components
#### Docker Registry Upstart Configuration
[docker.ext.j2](roles/docker-host/templates/docker.ext.j2) is an extended templated Upstart default configuration and referred in standard `/etc/default/docker` by sourcing as below
`. /etc/default/docker.ext`

#### Tasks
Ansible tasks configuration are written in [main.yml](roles/docker-host/tasks/main.yml)


## Ideas/Features in development
Following are few ideas/features that will be developed in due-course of time
 * Adding support for RHEL/CentOS
