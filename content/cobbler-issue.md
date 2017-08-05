---
title: "Second Post"
date: 2017-08-04
tags: []
categories:
  - Linux
draft: false
---

Where I work we use Cobbler to help provision our servers. It has been a while since I had to provision a server. We generate an iso that is used to boostrap and provide the kickstart for the server. As I was watching the initial boot sequence I noticed dracut has issues with the networking. As a result dracut would error to an emergency shell.

I did some Googling and decided to do a dump of the kickstart for the server. I noticed near the top of the generated kickstart was a little warning about using the old way to setup the network, and to add the mac address for the new way.

I edited the server definition with the mac address and made progress. But now name resolution wasn't working. I looked at the kickstart again and noticed the entry name server definition had both DNS servers in the same declaration. I edited the server definition again to only include one DNS entry. After that it worked like a charm.
