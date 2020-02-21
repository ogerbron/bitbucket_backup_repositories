Bitbucket - Backup Repositories
=========

[ ![Image](https://cloud.githubusercontent.com/assets/5514990/24834935/e0d1db04-1d1c-11e7-8ad0-53fd45ff13c3.png "Ansible") ](https://www.ansible.com/ "Ansible")

[![Build Status](https://travis-ci.org/ogerbron/bitbucket_backup_repositories.svg?branch=master)](https://travis-ci.org/ogerbron/bitbucket_backup_repositories/)
<!-- [![Ansible Role](https://img.shields.io/ansible/role/21653.svg)](https://galaxy.ansible.com/ogerbron/bitbucket_backup_repositories/) -->

Backup all repositories of a given team/user using Bitbucket API.

Requirements
------------

None

Role Variables
--------------

| Variable name                  | Required | Default                   | Choices                                         | Comments |
|--------------------------------|:--------:|:-------------------------:|:------------------------------------------------|:---------|
| `bitbucket_api_url`            | no       | https://api.bitbucket.org | HTTP URL                                        |  |
| `bitbucket_exclude_repos_list` | no       | []                        | A list of repositories                          | Some repositories you would like to exclude from the backup |
| `bitbucket_git_version`        | no       | HEAD                      | A git version, branch, commit, etc.             | See [Ansible git module](https://docs.ansible.com/ansible/latest/modules/git_module.html#parameter-version) |
| `bitbucket_password`           | yes      | None                      | The user's password |  |
| `bitbucket_user`               | yes      | None                      | The user to connect to bitbucket                |  |
| `bitbucket_workspace`          | yes      | None                      | The workspace you want to backup                | The bitbucket team or username in which the repositories are located |

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: backup_server
  roles:
  - role: bitbucket_backup_repositories
    vars:
      bitbucket_password: "test"
      bitbucket_user: "test"
      bitbucket_workspace: "test"
```

License
-------

GNU GENERAL PUBLIC LICENSE
