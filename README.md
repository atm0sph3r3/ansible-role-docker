Role Name
=========
This role is designed to configure a new environment to use Docker on Fedora. It includes installing Docker, Docker Compose, and provisions device mapper storage. See [Docker](https://docs.docker.com/engine/userguide/storagedriver/device-mapper-driver/) for more information about device mapper-based storage. 

Requirements
------------
NA

Role Variables
--------------
* docker_vg: the volume group that will be created for device mapper storage (default: docker)
* docker_pv: the physical volume from which the volume group above will be created 
docker_compose_version: the version of Docker Compose to retrieve (default: 1.9.0)
* docker_os: the version of the operating system (default: Linux)
* docker_machine_architecture: (default: x84_64)
* docker_docker_users: an array of users to add to the docker group in order to allow Docker use without sudo

Dependencies
------------
NA

Example Playbook
----------------
    - hosts: docker
      become: yes
      become_method: sudo
      roles:
        - docker

License
-------
MIT

Author Information
------------------
GitHub: tb120
