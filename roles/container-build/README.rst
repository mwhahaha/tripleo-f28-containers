container-build
===============

A role to build fedora28 containers using kolla/tripleo

Requirements
------------

N/A

Role Variables
--------------

.. list-table:: Variables used for container registry
   :widths: auto
   :header-rows: 1

   * - Name
     - Default Value
     - Description
   * - `build_python_version`
     - `python3`
     - python version that should be used (python2|python3)
   * - `build_work_dir`
     - `{{ ansible_user_dir }}/containers`
     - work dir for container build (logs end up here)
   * - `kolla_work_dir`
     - `{{ ansible_user_dir }}/kolla`
     - work dir to checkout kolla from source
   * - `kolla_f28_ref`
     - `refs/changes/38/624838/21`
     - gerrit ref to checkout with required changes
   * - `tripleo_common_work_dir`
     - `"{{ ansible_user_dir }}/tripleo-common`
     - work dir to checkout tripleo-common from source
   * - `virtenv_work_dir`
     - `{{ ansible_user_dir }}/containers-venv`
     - virtualenv dir where we install kolla
   * - `container_tag`
     - `latest`
     - container tag to use when building
   * - `container_registry`
     - `127.0.0.1:8787`
     - container registry to push containers to
   * - `container_push`
     - `True`
     - push built containers to a registry
   * - `kolla_rpm_repos`
     - `['http://trunk.rdoproject.org/fedora/current/delorean.repo','http://trunk.rdoproject.org/fedora/delorean-deps.repo']`
     - rpm repos to use in the containers when building

Dependencies
------------

virtualenv, pip, git, tripleoclient

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: container-build }

License
-------

Apache

Author Information
------------------


