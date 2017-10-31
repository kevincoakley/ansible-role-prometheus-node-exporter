ansible-role-prometheus-node-exporter
=====================================

[![Build Status](https://travis-ci.org/kevincoakley/ansible-role-prometheus-node-exporter.svg?branch=master)](https://travis-ci.org/kevincoakley/ansible-role-prometheus-node-exporter)

Install Prometheus Node Exporter - https://github.com/prometheus/node_exporter . Tested with CentOS 7 and Ubuntu 16.04

Requirements
------------

None

Role Variables
--------------

See defaults/main.yml. This role supports all collectors, just list the collectors using the prometheus_node_exporter_enabled_collectors variable.

Dependencies
------------

Node

Example Playbook
----------------

    - name: The Prometheus Node Exporter role
      hosts: node-exporter
      become: yes
      become_method: sudo

      vars:
        prometheus_node_exporter_enabled_collectors:
          - gmond
          - loadavg

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
