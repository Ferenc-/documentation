================
Service networks
================

Active service networks
=======================

=================== ============================== =====================
**Service**         **Ansible role**               **Network**
------------------- ------------------------------ ---------------------
Ceph client         osism.cephclient               ``172.31.100.0/28``
OpenStack client    osism.openstackclient          ``172.31.100.16/28``
phpMyAdmin          osism.helper                   ``172.31.100.32/28``
Rally               osism.helper                   ``172.31.100.48/28``
Adminer             osism.helper                   ``172.31.100.64/28``
Patchman            osism.patchman                 ``172.31.100.80/28``
Pulp                osism.pulp                     ``172.31.100.96/28``
Zabbix              osism.zabbix                   ``172.31.100.112/28``
UCS                 osism.ucs                      ``172.31.100.128/28``
Keycloak            osism.keycloak                 ``172.31.100.144/28``
Health Monitor      osism.openstack_health_monitor ``172.31.100.160/28``
Netbox              osism.netbox                   ``172.31.100.176/28``
Rundeck             osism.rundeck                  ``172.31.100.192/28``
Heimdall            osism.heimdall                 ``172.31.100.208/28``
Jenkins             osism.jenkins                  ``172.31.100.224/28``
OpenLDAP            osism.openldap                 ``172.31.100.240/28``
Manager             osism.manager                  ``172.31.101.0/28``
=================== ============================== =====================

Deprecated service networks
===========================

=================== ========================= ====================
**Service**         **Ansible role**          **Network**
------------------- ------------------------- --------------------
Prometheus          osism.prometheus          ``172.31.102.0/28``
Prometheus exporter osism.prometheus-exporter ``172.31.102.16/28``
=================== ========================= ====================
