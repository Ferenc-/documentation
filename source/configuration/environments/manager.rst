.. _configuration-environment-manager:

=======
Manager
=======

Base directory: ``environments/manager``

Ansible configuration
=====================

.. note::

   Do not customize the ``ansible.cfg`` configuration file. The file will be updated
   from time to time.

Playbooks
=========

In the manager environment some playbooks are included. These are needed to perform the initial
bootstrap of the manager independently of Docker.

.. note::

   These playbooks are updated from time to time. Therefore do not make any changes to them.
   Custom playbooks can be placed in the custom environment.

Inventory
=========

The manager environment has its own inventory file as the only environment. Only one host group
``manager`` is stored in this inventory. All other environments use the global inventory.

Script
======

The manager environment includes a ``run.sh`` script. This script is used for the execution of the
included playbooks.

.. note::

   Do not customize the ``run.sh`` script. The file will be updated from time to time.

Caching
=======

Redis
-----

.. code-block:: ini
   :caption: environments/ansible.cfg

   # Fact caching
   gathering = smart
   fact_caching = redis
   fact_caching_timeout = 86400
   fact_caching_connection = cache:6379:0

JSON file
---------

.. code-block:: ini
   :caption: environments/manager/configuration.yml

   redis_enable: false

.. code-block:: ini
   :caption: environments/ansible.cfg

   # Fact caching
   gathering = smart
   fact_caching = jsonfile
   fact_caching_timeout = 86400
   fact_caching_connection = /share/facts
