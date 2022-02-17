---
title: "Okta Authentication with NetBox"
date: 2022-02-04
author: Jeremy Stretch
categories:
  - Tips and Tricks
tags:
  - authentication
---

NetBox v3.1 introduced [support for single-sign on (SSO) authentication](https://github.com/netbox-community/netbox/issues/7649) when it was released back in December, using the popular [`python-social-auth`](https://python-social-auth.readthedocs.io/en/latest/) library. This has been in high demand for quite some time as it enables NetBox administrators to offload authentication to an external service.

[Jason Lavoie](https://twitter.com/ratvarre) has just written an excellent tutorial on [enabling Okta authentication for NetBox](https://www.oasys.net/posts/okta-sso-with-netbox/). He walks through the entire process from start to finish, covering configuration of both Okta and NetBox, even going so far as to include a Terraform configuration for Okta! It's well worth a read if you're looking to enable Okta authentication for NetBox.

