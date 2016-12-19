leutils
=======

[![Build Status](https://travis-ci.org/vbotka/ansible-leutils.svg?branch=master)](https://travis-ci.org/vbotka/ansible-leutils)

[Ansible role.](https://galaxy.ansible.com/vbotka/leutils/) Install le-utils from https://github.com/vbotka/le-utils and configure cron to:

- email a list of certificates that will expire in specified number of days.
- optionaly dry-run renewal of the certificates.
- optionaly renew if there are certificates due for renewal.

Requirements.
------------

None.


Role Variables.
--------------

TBD (Check defaults).


Dependencies.
------------

None.


Dry-run renewal.
---------------

Daily dry-run renewal is recommended. "This verifies whether you're
apparently able to get a certificate, in your current configuration
... You can use this to simulate what would apparently happen if you
ran the command without --dry-run."
[Q. What's the new --dry-run flag?]
(https://community.letsencrypt.org/t/help-us-test-renewal-with-letsencrypt-renew/10562)

Set
```
leutils_dryrun: "yes"
```
to enable dry-run renewal.

Command
```
/root/bin/lectl -n -c -a
```
will stop apache during renewal.


Renewal.
--------

Set
```
leutils_renew: "yes"
```
to enable renewal and review the template renew-certificates.j2



License.
-------

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


Author Information.
------------------

[Vladimir Botka](https://botka.link)

