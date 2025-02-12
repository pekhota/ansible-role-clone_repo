# Ansible Role: Clone Repository

## Overview
This role clones a Git repository and installs dependencies (e.g., Composer).

## Requirements
- Ansible 2.9+
- Git installed on the target machine
- Composer (if using PHP projects)

## Variables

| Variable           | Default                                        | Description             |
|--------------------|------------------------------------------------|-------------------------|
| `repo_url`         | `"https://github.com/username/repository.git"` | Repository URL          |
| `repo_destination` | `"/var/www/site"`                              | Directory to clone into |
| `repo_branch`      | `"main"`                                       | Branch to checkout      |
| `repo_owner`       | `"www-data"`                                   | User owning the repo    |
| `repo_group`       | `"www-data"`                                   | Group owning the repo   |
| `composer_install` | `true`                                         | Run `composer install`? |

## Usage
```yaml
- hosts: servers
  roles:
    - role: clone_repo
      vars:
        repo_url: "git@github.com:yourorg/project.git"
        repo_branch: "develop"
        repo_owner: "ubuntu"
        repo_group: "ubuntu"
        composer_install: true
```