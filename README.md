# leutils

[![Build Status](https://travis-ci.org/vbotka/ansible-leutils.svg?branch=master)](https://travis-ci.org/vbotka/ansible-leutils)

[Ansible role.](https://galaxy.ansible.com/vbotka/leutils/) Install le-utils from https://github.com/vbotka/le-utils and configure cron to:

- email a list of certificates that will expire in specified number of days.
- dry-run renewal of the certificates.
- renew certificates.


## Requirements

None.


## Role Variables

Review defaults and examples in vars.


## Dependencies

None.


## Installation

1) Create directory for the source code and download the tarball first. Without the tarball the --check will crash with error `No such file or directory`.

```
shell> ansible-playbook leutils.yml -t leutils_download
```

2) Perform a syntax check on the playbook, but do not execute it.

```
shell> ansible-playbook leutils.yml --check
```

3) Run the playbook.

```
shell> ansible-playbook leutils.yml
```


## Dry-run renewal

Daily dry-run renewal is recommended. "This verifies whether you're
apparently able to get a certificate, in your current configuration
... You can use this to simulate what would apparently happen if you
ran the command without --dry-run."

[Q. What's the new --dry-run flag?](https://community.letsencrypt.org/t/help-us-test-renewal-with-letsencrypt-renew/10562)

To enable dry-run renewal set

```
leutils_dryrun: True
```

and configure variable *leutils_dryrun_command*. Command:

```
shell> /root/bin/lectl -n -c -a
```

will stop the webserver during dry-run renewal.


## Renewal

To enable renewal set

```
leutils_renew: True
```

and configure variable *leutils_renew_command*. Review the template
renew-certificates.j2 and optionally use the script
renew-certificates.sh


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.link)
