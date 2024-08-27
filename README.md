# tolecnal.nvchad

This role helps you to install and configure neovim with the default configuration, as well as all the required Python and APT packages.

## Requirements

Python packages:

- python3-jmespath
- yamllint
- yq

NPM packages:

- tree-sitter-cli

APT packages:

- curl
- software-properties-common
- ca-certificates
- gnupg
- curl
- build-essential
- python3-venv
- jq
- unzip
- git
- libfuse2
- squashfuse
- fuse
- luarocks

All the requirements will be installed by the role.

## Role variables

Available variables are listed below, along with default values (see defaults/main.yml):

    python_packages:
The default Python packages to install: jmespath, yamllint and yq.

    nodejs_deps:
APT packages required to install NodeJS: curl, software-properties-common, ca-certificates and gnupg.

    ripgrep_owner:
The GitHub repository owner for `ripgrep`: BurntSushi

    ripgrep_repo:
The GitHub repository name for `ripgrep`: ripgrep

    ripgrep_install_path:
The ripgrep temporary installation file location: `/tmp/{{ repo }}.deb`

## Example playbook

Below is is a sample playbook to deploy nvchad to your system.

```yaml
---

- name: Setup nvchad
  hosts: all
  become: true
  gather_facts: true

  roles:
    - tolecnal.nvchad
```
