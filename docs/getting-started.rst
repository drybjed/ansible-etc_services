Getting started
===============

.. include:: includes/all.rst

.. contents::
   :local:

Useful variables
----------------

This is a list of role variables which your might want to define to create local services:

:envvar:`etc_services__host_list`
  Local services on a per host basis. :ref:`Local services <etc_services__ref_local_services>`.

Using debops.etc_services from other roles
------------------------------------------

One common use case for ``debops.etc_services`` is to use it form other roles
to configure :file:`/etc/services`.

To do this, you can define the services in your :file:`defaults/main.yml` file.
Example::

   # Configuration for ``debops.etc_services`` role which registers port numbers
   # for Apt-Cacher NG.
   apt_cacher_ng__etc_services__dependent_list:

     - name: 'acng'
       port: '3142'
       comment: 'Apt-Cacher NG caching proxy server'

And then in the playbook for this role, hand the
:command:`apt_cacher_ng__etc_services__dependent_list` variable over to the
``debops.etc_services`` role::

   ---

   - name: Configure package proxy server apt-cacher-ng
     hosts: [ 'debops_service_apt_cacher_ng' ]
     become: True

     roles:

       - role: debops.etc_services
         tags: [ 'role::etc_services' ]
         etc_services__dependent_list:
           - '{{ apt_cacher_ng__etc_services__dependent_list }}'

Example inventory
-----------------

To configure ``debops.etc_services`` on a given remote host, it needs to be added to
``[debops_all_hosts]`` or ``debops_service_etc_services`` Ansible inventory group::

    [debops_all_hosts]
    hostname

Example playbook
----------------

Here's a minimal example playbook that can be used to manage the
:file:`/etc/services` file:

.. literalinclude:: playbooks/etc_services.yml
   :language: yaml

This playbooks is shipped with this role under
:file:`docs/playbooks/etc_services.yml` from which you can symlink it to your
playbook directory.
