---
layout: post
title:  "Welcome to bongo.zone"
date:   2016-04-08 20:21:41 -0400
---
* setup this website
* installed a tor node and polipo HTTP proxy; SOCKS proxy is 9050, HTTP is 8123. **Don't connect to these using a generic desktop browser!**

Testing:

```sh
curl --socks5-hostname localhost:9050 https://ifconfig.co/all.json
curl --proxy http://localhost:8123  https://ifconfig.co/all.json
```

