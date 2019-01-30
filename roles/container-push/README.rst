container push
==============

A concurrent container tag/push role

Requirements
------------

docker

Role Variables
--------------

.. list-table:: Variables used for container registry
   :widths: auto
   :header-rows: 1

   * - Name
     - Default Value
     - Description
   * - `push_src_registry`
     - `127.0.0.1:8787`
     - container registry source to tag from
   * - `push_src_namespace`
     - `master`
     - container source namespace
   * - `push_src_tag`
     - `latest`
     - container source tag
   * - `push_dest_registry`
     - `docker.io`
     - destination containter registry to push to
   * - `push_dest_namespace`
     - `mwhahaha`
     - destination container namespace
   * - `push_desg_tag`
     - `latest`
     - destination container tag

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: container-push }

License
-------

Apache

Author Information
------------------

