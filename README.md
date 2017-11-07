Acme-Tiny Install
=================

This is an ansible role for installing acme-tiny, first by trying the distro way but, if this is not working, by directly getting the source from 'diafygi' on github - this can be overridden if an URL/Checksum is specified.

The role is meant to be run on the host that will later also play the inofix.ansible-acme-tiny-setup and the inofix.ansible-acme-tiny-sign role.

Why we do not use one of the existing roles?

* For the first reason read the section "Promise" below. We need something reliable.
* This role will be used by [maestro](https://github.com/inofix/maestro) and must follow the logic used there. (Of course, the role can be used without maestro..)

State
-----

UNSTABLE! We are just migrating from zwischenloesung.acme-tiny-install.

Promise
-------

Sure, this role may change in the future, but we will only expand features to not break backwards compatibility.

If radical changes should become necessary, a new role will be created, probably with an 'ng' or version suffix...

Installation
------------

 # ansible-galaxy install inofix.ansible-acme-tiny-install

Requirements
------------

* Ansible >2.0
* Galaxy-Role: inofix.yapkg
* Python2/3 on target host
* Generic UNIX with FHS

Role Variables
--------------

* http\_proxy (optional, string)
* app\_\_acme\_\_tiny\_\_checksum (optional, string: default="sha256:bcd7cb56c280543c929cb4b7b2d1ed2d7ebabdae74fedc96b6a63f218c0b8ace")
* app\_\_acme\_\_tiny\_\_download\_upstream (optional, string: default="https://raw.githubusercontent.com/diafygi/acme-tiny/master/acme\_tiny.py")

Dependencies
------------

* Galaxy-Role: inofix.yapkg
* The Download-Source: default URL/checksum might change..

Example Playbook
----------------

    - hosts: servers
      roles:
         - inofix.ansible-acme-tiny-install

License
-------

GPLv3

Author Information
------------------

* Michael Lustenberger at [inofix.ch](http://www.inofix.ch)
