# apk-tools module for Ansible

A simple module to make use of apk-tools under Ansible. It's very possible it can be written cleaner — patches welcome (also on [Github](https://github.com/Barthalion/ansible-apk).

## Installation
Copy `apk` to `$ANSIBLE_LIBRARY` on the management host.
    install -m444 library/apk $ANSIBLE_LIBRARY/apk

## Examples
    - name: Install package foo
      action: apk pkg=foo state=present
Note that default value of `state` is `present`, therefore it doesn't have to be explicitly defined.

    - name: Update the package database and upgrade package bar
      action: apk pkg=bar update=yes state=latest

    - name: Remove package foo and purge its configuration files
      action: apk pkg=foo state=purge

    - name: Force removal of package bar
      action: apk pkg=bar force=yes

## To-do
* return more verbose messages
* add support for `upgrade`, `verify` and `fix`
