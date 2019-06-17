============
Cookiecutter
============

.. note::

   To gain access to the cookiecutter repository, please send a request to info@betacloud-solutions.de.

You need a Git repository to store the configuration of the environment. It has to be accessible
from the manager node. A SSH deploy key for read-only access is sufficient.

Before you create the configuration, you need some basic information:

* NTP servers
* DNS servers
* FQDNs and IP addresses for the API endpoints
* desired versions of OSISM, OpenStack, Ceph and Docker
* CIDRs of networks for Ceph
* SSL certificate, if one is used

.. note::

   After the deployment of the manager, it is possible to generate a self-signed SSL certificate
   using an included Ansible playbook. See :ref:`generation-of-self-signed-certificate` for more information.

To prepare the configuration repository, you need cookiecutter. Usually you prepare and edit the
repository on your workstation. It is pushed to a central server and pulled from the manager node
later.

It is recommended to always use a virtual environment when you install packages from PyPI.

.. code-block:: console

   $ virtualenv -p python3 .venv
   $ source .venv/bin/activate

.. code-block:: console

   $ pip3 install \
       cookiecutter \
       cryptography \
       oslo.utils \
       paramiko \
       passlib \
       pycrypto \
       python-gilt \
       pyyaml \
       ruamel.yaml

When you run cookiecutter, you are asked for the information you collected before.
A list with all queries can be found in the ``cookiecutter.json`` configuration file.
A description of the individual parameters can be found in the README file of the repository.

.. code-block:: console

   $ cookiecutter ssh://git@git.betacloud-solutions.de:10022/generic/cookiecutter.git

Push the contents of the newly created ``cfg-customer`` directory to your Git repository. Be careful
not to forget dotfiles like ``.gitignore``. The directory itself is not stored in the repository.

.. figure:: /images/gitlab-initial-commit.png

   Directory structure after the initial commit in the Git repository. The ``secrets`` directory
   is only stored in the repository for test environments.

.. warning::

   In a productive environment use Ansible Vault to encrypt the newly created ``secrets.yml`` files,
   before committing it to the Git repository. Never commit any plaintext passwords or secrets to the
   configuration repository.
