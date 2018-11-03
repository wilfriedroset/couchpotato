CouchPotato
===========
[![Build Status](https://travis-ci.org/wilfriedroset/couchpotato.svg?branch=master)](https://travis-ci.org/wilfriedroset/couchpotato)

Install [CouchPotato](https://github.com/CouchPotato/CouchPotatoServer)

Requirements
------------

This role do not have requirements other than to be used on tested platforms.

Platforms
---------

This role has been tested on:

* Debian stretch (9)
* Ubuntu xenial (16.04)
* Ubuntu bionic (18.04)
* Centos 7

Role Variables
--------------

This role supports the following variables:
* couchpotato_user: name of the user responsible for running couchpotato daemon
* couchpotato_group: name of the group of the user responsible for running couchpotato daemon
* couchpotato_data: path where to store couchpotato data
* couchpotato_repo: git repository of couchpotato
* couchpotato_src: path where to store couchpotato source
* couchpotato_version: couchpotato version to provision

Dependencies
------------

This role is standalone and do not depends on any other role.

Example Playbook
----------------

Use the role with all default variables:

```yaml
    - hosts: servers
      roles:
         - wilfriedroset.couchpotato
```

Change the user:

```yaml
    - hosts: servers
      roles:
         - {role: 'wilfriedroset.couchpotato', couchpotato_user: 'pi', couchpotato_group: 'pi'}
```

Install a specific version:

```yaml
    - hosts: servers
      roles:
         - {role: 'wilfriedroset.couchpotato', couchpotato_version: 'V3.0.1'}
```

License
-------

GPLv3
