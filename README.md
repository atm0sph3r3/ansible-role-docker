Role Name
=========
This role is designed to configure a new environment to use Docker on Fedora. It includes installing Docker, Docker Compose, and provisions device mapper storage. See [Docker](https://docs.docker.com/engine/userguide/storagedriver/device-mapper-driver/) for more information about device mapper-based storage.

Requirements
------------
A physical volume or volumes must be provided and should be specified in the `docker_pvs` variable, which is described below.

Role Variables
--------------
* docker_pvs: the physical volume from which the volume group above will be created (default: no default provided) *mandatory*
* docker_compose_version: the version of Docker Compose to retrieve (default: 1.9.0) *mandatory*
* docker_machine_architecture: (default: x84_64) *mandatory*
* docker_docker_users: an array of users to add to the docker group in order to allow Docker use without sudo (default: no default provided) *optional*

Dependencies
------------
NA

Example Playbook
----------------
    - hosts: docker
      become: yes
      vars:
        docker_pvs: dev/vda
      roles:
        - docker

License
-------
MIT

Author Information
------------------
GitHub: tb120
