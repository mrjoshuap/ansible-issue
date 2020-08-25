Role Name
=========

This role allows you to manage `/etc/issue` `/etc/issue.net` and can configure sshd to use
`/etc/issue.net` as a banner.

Requirements
------------

There are no special requirements for this role, it should work on Ansible 2.8 and newer.

Role Variables
--------------

The following variables are defined in `defaults/main.yml` and are the ones generally used to customize
this role's behavior:

`issue_deploy` | bool
Default: `yes`
Should this role manage and deploy issue?

`issue_template_src` | string
Default: `issue.j2`
This is the path to the template used to generate the issue file.

`issue_net_deploy` | bool
Default: `yes`
Should this role manage and deploy issue.net?

`issue_net_template_src` | string
Default: `issue.net.j2`
This is the path to the template used to generate the issue.net file.

`issue_net_sshd_banner` | bool
Default: `yes`
Should this role configure sshd to use issue.net as the banner?

`issue_net_sshd_restart` | bool
Default: `yes`
Should this role restart sshd if the banner is changed?

The following variables are defined in vars/main.yml and are used to customize things you should probably not change unless you need to customize or add a newly supported operating system.

`issue_location` | sting / path
Default: `/etc/issue`

`issue_net_location` | string / path
Default: `/etc/issue.net`

`issue_sshd_config_location` | string / path
Default: `/etc/ssh/sshd_config`

`issue_sshd_service_name` | string
Default: `sshd`

Dependencies
------------

There are no dependencies for this role.

Example Playbook
----------------

The simplest form for an example playbook is:

    - hosts: servers
      roles:
         - { role: mrjoshuap.issue }

The fullest form looks like:

    - hosts: servers
      roles:
         - { role: mrjoshuap.issue, issue_deploy: yes, issue_net_deploy: yes, issue_net_sshd_banner: no }

License
-------

GPL 2.0 or later

Author Information
------------------

Joshua Preston
mrjoshuap@redhat.com
