=============
Configuration
=============

.. list-table::
   :widths: 10 90
   :align: left

   * - **Name**
     - ``osism.configuration``
   * - **Repository**
     - https://github.com/osism/ansible-configuration
   * - **Documentation**
     - ---

Git
===

.. code-block:: yaml
   :caption: environments/configuration.yml

   ##########################
   # configuration

   configuration_directory: /opt/configuration
   configuration_type: git

   configuration_git_host: git.betacloud-solutions.de
   configuration_git_port: 10022

   configuration_git_private_key_file: ~/.ssh/id_rsa.configuration
   configuration_git_protocol: ssh
   configuration_git_repository: customers/CUSTOMER/cfg-NAME.git
   configuration_git_username: git
   configuration_git_version: master

Deploy key
----------

* https://developer.github.com/v3/guides/managing-deploy-keys/#deploy-keys
* https://docs.gitlab.com/ee/ssh/#per-repository-deploy-keys

.. code-block:: yaml
   :caption: environments/secrets.yml

   ##########################
   # private ssh keys

   configuration_git_private_key: |
     -----BEGIN RSA PRIVATE KEY-----
     [...]
     -----END RSA PRIVATE KEY-----
