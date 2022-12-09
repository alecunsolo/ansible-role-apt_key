Ansible Role: apt_key
=========

A simple role to download apt keys, since `apt_key` is deprecated.

Requirements
------------

None.

Role Variables
--------------

```yaml
key_url: < the URL to use to download the key i.e. https://download.docker.com/linux/debian/gpg >
key_name: < the name of the downloaded key i.e. docker-archive-keyring.gpg >
key_armored: < boolean. whether the key is ASCII armored or not >

```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- name: Apt key
  hosts: all
  vars:
    key_url: https://download.docker.com/linux/debian/gpg
    key_name: docker-archive-keyring.gpg
    key_armored: true
  tasks:
    - name: Include apt_key.
      ansible.builtin.include_role:
        name: alecunsolo.apt_key
```

License
-------

MIT

Notes
-----

Testing with molecule (including the docker images used) is ~~stolen from~~ heavily inspired by [Jeff Geerling](https://www.jeffgeerling.com/). Watch [his video](https://youtu.be/FaXVZ60o8L8) (and the other ones as well).
