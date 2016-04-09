---
layout: page
title: Connect
permalink: /connect/
---
## via ssh

Connect with ssh: `ssh user@bongo.zone`. The `.ssh/known_hosts` should look like.

```
# bongo.zone:22 SSH-2.0-OpenSSH_7.2
bongo.zone ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC+JwIDbYFvyS5xKAMs83LCqk/Ld1DwdfKcFck7AkKOfrcZxHUlXrqC0g8tPS9dD0naksRXsCDeEuwjZJGjzvOLxIyPHFGUrjiuUgLRpjF7lW0pEPyR0s7F7pno6eLPSABaNGFwMIJK6hqZXwrr0DwGTdYUrQ6BN/hHYilzOpKPkf29XRckTBKPUWP2VCzl3voB/o8fhEagQr7OCwOaLrZEAyzYp8YiQUXCIru3n9nWcLynEtZJWIe8SyTNAaTTiiVVffCLQbykI7FS/O5uyyS07nu5WkcTerf0Te3z1AlVC9TAG7SRXZlL7fum6KYKlImvESGMZjzusaKtpVaStof/
bongo.zone ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBLXucRj+5hh1f1YylWwKQCRz9Q2w7IJgph3VJG2hZrw0y1k5KsmQYzd0c3sFRC34VPBlo0pA8m7hfF17eyDOvgM=
bongo.zone ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIP6YYx6ASdFZ937jDldBEA7KXGKEbLqfhO4ALq1YSO00
cqxpkm2q2avequbp.onion ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC+JwIDbYFvyS5xKAMs83LCqk/Ld1DwdfKcFck7AkKOfrcZxHUlXrqC0g8tPS9dD0naksRXsCDeEuwjZJGjzvOLxIyPHFGUrjiuUgLRpjF7lW0pEPyR0s7F7pno6eLPSABaNGFwMIJK6hqZXwrr0DwGTdYUrQ6BN/hHYilzOpKPkf29XRckTBKPUWP2VCzl3voB/o8fhEagQr7OCwOaLrZEAyzYp8YiQUXCIru3n9nWcLynEtZJWIe8SyTNAaTTiiVVffCLQbykI7FS/O5uyyS07nu5WkcTerf0Te3z1AlVC9TAG7SRXZlL7fum6KYKlImvESGMZjzusaKtpVaStof/
cqxpkm2q2avequbp.onion ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBLXucRj+5hh1f1YylWwKQCRz9Q2w7IJgph3VJG2hZrw0y1k5KsmQYzd0c3sFRC34VPBlo0pA8m7hfF17eyDOvgM=
cqxpkm2q2avequbp.onion ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIP6YYx6ASdFZ937jDldBEA7KXGKEbLqfhO4ALq1YSO00
```

## via tor

[http://cqxpkm2q2avequbp.onion](http://cqxpkm2q2avequbp.onion)

## via ssh over tor

Setup [socat](http://www.dest-unreach.org/socat/) to use tor for onion urls. Add this to your `.ssh/config` and **add the above `.ssh/known_hosts` entry so you don't get MITM'd.**

```
Host *.onion
  ProxyCommand socat STDIO SOCKS4A:localhost:%h:%p,socksport=9150
  StrictHostKeyChecking yes
```
*Change the port number to 9150 if you're using regular tor i.e. not the browser bundle.*

Connect `ssh user@cqxpkm2q2avequbp.onion`
