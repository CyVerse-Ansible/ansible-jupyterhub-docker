ansible jupyterhub
==================

This role will install jupyterhub with github authentication and dockerspawner for jupyter notebooks.

Currently, Ubuntu 20 is supported.

Requirements
------------

This requires docker

This role also assumes the community.docker collection is installed i.e. ansible-galaxy collection install community.docker

If using swarmspawner, then docker and docker swarm should be setup beforehand

Role Variables
--------------

* jupyterhub_system_config, the directory containing the jupyter configuration (default: /etc/jupyterhub)
* jupyterhub_log, the path to the jupyterhub log file (default: /var/log/jupyterhub.log)
* jupyterhub_dockerhost_ip, the default internal ip of the docker host (default: 172.17.0.1)
* jupyterhub_docker_image, the default docker image to use for jupyter notebooks (default: jupyter/datascience-notebook)
* jupyterhub_config_allowed_users, the set of users who are allowed to login
* jupyterhub_config_admin_users, the set of users with admin rights (default: "set()" or empty)
* jupyterhub_systemd_after, setting used for the systemd config file. Note, this is distro specific.
* jupyterhub_mod_auth_cas_config_path, location of the apache module configuration path
* jupyterhub_oauth2_callback_url, callback url for this jupyterhub
* jupyterhub_oauth2_client_id, oauth2 client id
* jupyterhub_oauth2_client_secret, oauth2 client secret
* jupyterhub_enable_swarmspawner, default is false

Dependencies
------------

* Any role that installed docker ce

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- name: This playbook will install jupyterhub
  hosts: jupyterhub
  roles:
  - ansible-docker
  - ansible-jupyterhub-docker

License
-------

BSD

Author Information
------------------

For more information, please contact Edwin Skidmore (edwin@cyverse.org)
