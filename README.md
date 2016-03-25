Ansible role: attic
===================

Install Attic and performs backups (local or remote).

The repositories are encrypted with the passphrase specified in the ATTIC_PASSPHRASE env variable.

Variables
---------

attic_version: 0.16

attic_repository_type: remote          # local, remote
attic_repository_path: /backup/attic   # base path for remote repo, full path for local repo
attic_repository_overwrite: no         # recreates repo
attic_repository_passphrase            # used to encrypt repo, derived from ATTIC_PASSPHRASE env var

# For remote repositories only (over SSH)
attic_repository_server
attic_repository_user: attic
attic_repository_port: 22
attic_repository_key: /root/.ssh/attic # it will be generated if missing, do not reuse other keys for Attic
attic_repository_key_overwrite: no     # recreates SSH key

# Prune options
attic_keep_daily: 7
attic_keep_weekly: 4
attic_keep_monthly: 3

attic_include_list: []                 # List of directories to be included (mandatory)
attic_exclude_list: []                 # List of directories to be excluded (optional)
