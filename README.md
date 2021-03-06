[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/grycap/ansible-role-clues.svg?branch=master)](https://travis-ci.org/grycap/ansible-role-clues)

CLUES cluster Role
=======================

Install [CLUES](http://www.grycap.upv.es/clues/eng/index.php).  
Recipe for [EC3](http://servproject.i3m.upv.es/ec3/).

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows.
```
clues_secret_token: not_very_secret_token
# Select between the following: torque, slurm, sge, condor, mesos
clues_queue_system: slurm
# Number of max worker nodes to deploy in the cluster
ec3_max_instances: 5
# Prefix applied to the elastic cluster worker nodes
vnode_prefix: wn
# Path for the authorization file used
auth: auth.dat
# Path for extra configuration files needed
extract_proxy_file: extract_proxy.py
```

Example Playbook
----------------

This an example of how to install a SLURM cluster with three nodes:
```
- hosts: server
  roles:
  - { role: 'grycap.clues', clues_queue_system: 'slurm', ec3_max_instances: '3' }
```
Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks
