Ansible MongoDB role testing example with Molecule
=========
[![Build status](https://travis-ci.org/silazare/ansible-role-test.svg?branch=master)](https://travis-ci.org/silazare)

## Supported OS:

- Ubuntu 18.04

## Requirements:

- Ansible =>2.8
- Molecule =>2.22rc6
- Goss =>3.6.7

## Molecule initialize examples:

- Docker with Ansible verifier (master branch)
```sh
molecule init role -r ansible-role-test -d docker --verifier-name ansible
```

- Docker with default Testinfra (testinfra branch)
```sh
molecule init role -r ansible-role-test -d docker --verifier-name testinfra
```

- Docker with Goss (goss branch)
```sh
molecule init role -r ansible-role-test -d docker --verifier-name goss
```