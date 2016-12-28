Ansible Docker Node Role
========================

This [Ansible](http://www.ansible.com/home) role supports the installation and configuration of the [Docker](https://www.docker.com/) Server on a Docker host.

## Table of Contents

* [Supported Platforms](#supported-platforms)
* [User Manual](#user-manual)
  * [Basic usage](#basic-usage)
  * [Install specific docker version](#install-specific-docker-version)
  * [Enable Remote Management](#enable-remote-management)
  * [Enable Remote Management with TLS](#enable-remote-management-with-tls)
* [Configuration](#configuration)
  * [Configurable variables](#configurable-variables)

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

### Enable Remote Management

* Add the following lines (adjust as needed):
```
roles:
  - role: "ansible-docker-node"
    ansible_docker_node_docker_opts: "-H tcp://srv-docker-node01:2376"
```

### Enable Remote Management with TLS

* Ensure the required server and client certificates are present (see [Docker Host - Secured remote management](http://polster.github.io/2016/12/25/Docker-Host-Secure-remote-management.html))
* Add the following lines (adjust as needed):
```
roles:
  - role: "ansible-docker-node"
    ansible_docker_node_docker_opts: "--tls=true --tlscert=/root/.docker/server-cert.pem --tlskey=/root/.docker/server-key.pem --tlscacert=/root/.docker/ca.pem -H tcp://srv-docker-node01:2376"
```

## Configuration

### Configurable variables

See [defaults](defaults/main.yml).
