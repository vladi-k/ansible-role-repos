ansible-role-repos
====

Manage DNF repos.

Requirements
------------

* RHEL8+

Role Variables
--------------

* `repos_gpg_keys` - list of gpg keys to import, example:

```yaml
repos_gpg_keys:
  - key: https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-8
```

* `repos_from_rpm` - list of repos to add from RPM, exmaple:

```yaml
repos_from_rpm:
  - https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
```

* `repos_add` - list of repos to add, example:

```yaml
repos_add:
  - name: myrepo
    description: My Repo
    baseurl: https://my.repo.com/el8
```

* `repos_remove` - list of repos to remove, example:

```yaml
repos_remove:
  - myrepo
```

Dependencies
------------

Collections:

* `ansible.builtin`

Example Playbook
----------------

```
- hosts: my_servers
  vars:
    repos_gpg_keys:
      - key: https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-8
    repos_from_rpm:
      - https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
  roles:
    - ansible-role-repos
```

License
-------

GPLv3

Author Information
------------------

Vladimir Vasilev (@vladi-k)
