Ansible role testing example with Molecule
=========
[![Build status](https://travis-ci.org/silazare/ansible-role-test.svg?branch=master)](https://travis-ci.org/silazare)

## Molecule initialize examples:

- Docker with default Testinfra
```sh
molecule init role -r ansible-role-test -d docker
```

- Docker with Goss (switch to branch Goss_testing for example)
```sh
molecule init role -r ansible-role-test -d docker --verifier-name goss
```
