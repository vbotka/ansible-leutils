leutils
=========

Install le-utils from github.com/vbotka/le-utils and configure cron to
email a list of certificates that will expire in specified number of
days. Optionaly dry-run renewals.


Requirements.
------------

None.


Role Variables.
--------------

TBD (Check defaults).


Dependencies.
------------

None.


Renewal.
-------

TBD. (cron entry to renew certificates 30 days before expiration).


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


License.
-------

BSD


Author Information.
------------------

[Vladimir Botka](https://botka.link)
