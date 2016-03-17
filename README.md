# percona_apt

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/saucelabs-ansible/percona_apt/master/LICENSE)
[![Build Status](https://travis-ci.org/saucelabs-ansible/percona_apt.svg?branch=master)](https://travis-ci.org/saucelabs-ansible/percona_apt)

[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/saucelabs-ansible-percona_apt/widgets/project_thin_badge.gif)](https://www.openhub.net/p/saucelabs-ansible-percona_apt/)

Ansible role to install the Percona APT repository.


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Ubuntu  | Trusty  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |


## Requirements

- ansible >= 1.9.4
- vagrant (testing)


## Dependencies

None.


## Role Variables

- **debug**: verbosity (default=false)
- **percona_apt_deb_file**: filename for the percona_apt Linux installer.
- **percona_apt_dir_source**: directory where to download the percona_apt Linux installer.
- **percona_apt_download_url**: URL to download percona_apt.
- **percona_apt_version**: version of percona_apt.


## Tags

* **debug**: debug statements
* **setup**: download APT repository installer and configure preferences
* **validation**: input parameter validation


## Playbooks

```
- hosts: all
  gather_facts: yes

  vars:
    debug: yes

  roles:

    - role: percona_apt
      tags: [ percona, percona_apt ]

```


## Test

To manually run a playbook:
```
$ cd tests

$ vagrant up

# run this command as many times as you need
$ vagrant provision

# run this to destroy the Vagrant box
$ vagrant destroy
```

To run the full integration suite:
```
$ tox
```

To run the integration suite manually:
```
$ cd tests

$ bash vagrant.sh --box trusty64.vagrant.dev
```

## References

* [Percona 5.6 server > Installing Percona Server on Debian and Ubuntu](https://www.percona.com/doc/percona-server/5.6/installation/apt_repo.html)
