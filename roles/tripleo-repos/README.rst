tripleo-repos
=============

basic role to install tripleo-repos and configure a set of repos

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
   * - `tripleo_repos_python`
     - `python3`
     - python version to use (python2|python3)
   * - `tripleo_repos_branch`
     - `master`
     - tripleo branch to use
   * - `tripleo_repos_version`
     - `current`
     - specific repo to use (current|current-tripleo-dev)
   * - `tripleo_repos_distro`
     - `fedora`
     - distro being used (fedora|centos)


Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

.. code-block::

    - hosts: servers
      roles:
         - { role: tripleo-repos }

License
-------

Apache

Author Information
------------------

