tripleo-f28-containers
======================

The roles and playbooks in this repository can be used to build the TripleO
containers using a Fedora 28 base image and python 3 packages.

Usage
-----

Building Containers
~~~~~~~~~~~~~~~~~~~

NOTE: When you checkout the code, you currently need to patch the
container-registry role that is pulled down and apply `this patch
to fix permission issues <https://review.openstack.org/#/c/633812/>`_.

.. code-block::

    git clone https://github.com/mwhahaha/tripleo-f28-containers
    cd tripleo-f28-containers
    cat > inventory.yml <<EOF
    all:
      hosts:
        node:
          ansible_ssh_host: 192.168.122.30
          ansible_ssh_user: fedora
          ansible_python_interpreter: /usr/bin/python3
    EOF
    export TAG=$(date +"%Y-%m-%d")
    ansible-playbook -i inventory.yml build-containers.yaml --extra-vars "container_tag=$TAG" 


Pushing Containers
~~~~~~~~~~~~~~~~~~

.. code-block::

    ansible-playbook -i inventory.yml push-container.yaml


Purging Containers
~~~~~~~~~~~~~~~~~~

.. code-block::

    ansible-playbook -i inventory.yml purge-containers.yaml

NOTE: This will remove *all* containers from the system.

