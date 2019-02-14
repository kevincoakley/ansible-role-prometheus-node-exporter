ansible-role-prometheus-node-exporter
=====================================

[![Build Status](https://travis-ci.org/kevincoakley/ansible-role-prometheus-node-exporter.svg?branch=master)](https://travis-ci.org/kevincoakley/ansible-role-prometheus-node-exporter)

Install Prometheus Node Exporter - https://github.com/prometheus/node_exporter . Tested with CentOS 7 and Ubuntu 18.04

Use role release >= 0.15.0 on node_exporter versions >= 0.15.0. Use role release <= 0.14.0 on node_exporter versions <= 0.14.0

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
