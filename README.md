## [![DebOps project](http://debops.org/images/debops-small.png)](http://debops.org) etc_services

<!-- This file was generated by Ansigenome. Do not edit this file directly but
     instead have a look at the files in the ./meta/ directory. -->

[![Travis CI](http://img.shields.io/travis/debops/ansible-etc_services.svg?style=flat)](http://travis-ci.org/debops/ansible-etc_services)
[![test-suite](http://img.shields.io/badge/test--suite-ansible--etc__services-blue.svg?style=flat)](https://github.com/debops/test-suite/tree/master/ansible-etc_services/)
[![Ansible Galaxy](http://img.shields.io/badge/galaxy-debops.etc_services-660198.svg?style=flat)](https://galaxy.ansible.com/detail#/role/1563)


The `debops.etc_services` role can be used to "reserve" or "register" a
service port in the `/etc/services` file. Service ports configured this way can
appear as named entries in many command outputs, such as `iptables --list`
or `netstat --listening --program`. You can also have convenient database
of reserved and free ports on a particular host, and reference ports by
their names in firewall configuration files.

### Installation

This role requires at least Ansible `v1.7.0`. To install it, run:

```Shell
ansible-galaxy install debops.etc_services
```

### Documentation

More information about `debops.etc_services` can be found in the
[official debops.etc_services documentation](http://docs.debops.org/en/latest/ansible/roles/ansible-etc_services/docs/).



### Are you using this as a standalone role without DebOps?

You may need to include missing roles from the [DebOps common
playbook](https://github.com/debops/debops-playbooks/blob/master/playbooks/common.yml)
into your playbook.

[Try DebOps now](https://github.com/debops/debops) for a complete solution to run your Debian-based infrastructure.





### Authors and license

`etc_services` role was written by:

- Maciej Delmanowski | [e-mail](mailto:drybjed@gmail.com) | [Twitter](https://twitter.com/drybjed) | [GitHub](https://github.com/drybjed)
- [Robin Schneider](http://ypid.de/) | [e-mail](mailto:ypid@riseup.net) | [Twitter](https://twitter.com/ypid) | [GitHub](https://github.com/ypid)

License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

***

This role is part of the [DebOps](http://debops.org/) project. README generated by [ansigenome](https://github.com/nickjj/ansigenome/).
