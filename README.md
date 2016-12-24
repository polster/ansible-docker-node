Ansible Docker Node Role
========================

This [Ansible](http://www.ansible.com/home) role supports the installation and configuration of the [Docker](https://www.docker.com/) Server on a Docker host.

## Supported Platforms

See [meta info](meta/main.yml).

## User Manual

### Basic usage

* Configure this role as ansible-galaxy dependency (e.g. requirements.yml)
* Add the following line to your Ansible playbook's role section (sample):
```
roles:
  - role: "ansible-docker-node"
```

### Install specific docker version

* Install a specific Docker version:
```
roles:
  - role: "ansible-docker-node"
    ansible_docker_node_docker_version: "1.12.5"
```

## Configuration

### Configurable variables

See [defaults](defaults/main.yml).
