---
title: "cobbler Issue"
date: 2017-08-04
tags: []
categories:
  - Linux
  - Nginx
draft: false
---

Trying out Nginx Plus R13 release in a PoC as a potential replacement for our Cisco ACE's. I been wanting to test out the REST API of Nginx, we were running R12 in the PoC and hadn't had time to test the REST API yet. But, with R13 a new revamped API has been intoduced. The status page has been setup, which uses the now depricated "/status" directive. Checked to see if the documentation for how to setup real time monitoring had been updated and it has.

Looking at the updated documentation seemed like to only change was to swap the "/status" location with a "/api" location. I did this one on of the PoC servers and the status pages was not loading and making a rest call was also not working. The status page stated it could not read the "/status" location. This seemed strange to me since that was supposed to deprecated and the documentaiton made no memtion to it. I decided to restart the services, still same issue.

I decided to add the "/status" location back to the conf file and reloaded the configuration. The status page loaded with the statistics and a rest call also worked. Seems odd to me to need to declare the "/status" location. I have raised this issue with the pre-sales engineer for clarification.