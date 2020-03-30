Ansible MongoDB role testing example with Molecule
=========
[![Build status](https://travis-ci.org/silazare/ansible-role-test.svg?branch=master)](https://travis-ci.org/silazare)

## Supported OS:

- Ubuntu 18.04

## Requirements:

- Ansible =>2.9
- Molecule =>=3.0.2

## Molecule initialize example:

- Docker with Ansible verifier
```sh
molecule init role -r ansible-role-test -d docker
```
