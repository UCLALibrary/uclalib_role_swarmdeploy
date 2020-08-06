uclalib_role_swarmdeploy
=========

Ansible role to deploy a Docker Compose service into a Docker Swarm cluster

Requirements
------------

A Docker Swarm cluster must be available.

Role Variables
--------------

* `project_name` - defines the name of the Docker service to be deployed into the Swarm cluster.
* `dockeradmin_home` - defines the path to the Docker admin user's home directory. (default: `/home/dockeradmin`)
* `use_docker_env_file` - defines whether the Docker compose service requires an external environment vars file. (default: `no`)
* `docker_compose_file_content` - defines the content of the Docker service's compose file.
    * This variable is intended to be a YAML scalar (|) that holds what you'd actually put into a docker compose file
* `docker_env_file_content` - defines the content of the Docker compose environment variables file
    * This is only needed if you set `use_docker_env_file` to `yes`.


Dependencies
------------

None

Example Playbook
----------------

```
- name: uclalib_swarmstackdeploy.yml
  become: yes
  become_method: sudo
  hosts: swarm_host

  roles:
    - { role: uclalib_role_swarmdeploy }
```
