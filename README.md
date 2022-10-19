ansible-role-prometheus-node-exporter
=====================================

![](https://github.com/kevincoakley/ansible-role-prometheus-node-exporter/workflows/Molecule%20Test/badge.svg)


Install Prometheus Node Exporter - https://github.com/prometheus/node_exporter . Tested with EL 7, EL 8, EL 9, Ubuntu 18.04, Ubuntu 20.04, and Ubuntu 22.04.

Requirements
------------

None

Role Variables
--------------

See defaults/main.yml. This role supports all collectors, just list the collectors using the prometheus_node_exporter_enabled_collectors variable.

Dependencies
------------

None

Example Playbook
----------------

    - name: The Prometheus Node Exporter role
      hosts: node-exporter
      become: yes
      become_method: sudo

      vars:
        prometheus_node_exporter_enabled_collectors:
          - logind
        prometheus_node_exporter_disabled_collectors:
          - netstat

      roles:
        - ansible-role-prometheus-node-exporter

      tags:
        - node-exporter


License
-------

BSD

Author Information
------------------

Kevin Coakley (https://github.com/kevincoakley)
