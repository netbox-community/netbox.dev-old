---
title: "Error Logging with Sentry"
date: 2022-05-13
author: Jeremy Stretch
categories:
  - Tips and Tricks
tags:
  - features
---
One of the challenges that comes with developing open source software is getting reliable and detailed bug reports from users in the wild. Because NetBox is generally self-hosted and has no phone-home function, we don't have any direct access to deployments other than what we (the maintainers) deploy ourselves. But there's a new feature in [NetBox v3.2.3](https://github.com/netbox-community/netbox/releases/tag/v3.2.3) that I think can really help us out: [Sentry](https://sentry.io/) intgeration.

Enabling error reporting via Sentry allows us to collect and analyze exceptions and other errors as they happen, rather than having to wait for bug reports submitted by end users. It won't capture _all_ bugs, of course, but it will alert us to the more severe issues. Sentry reports include a full stack trace, which is often needed to determine just where a bug exists, but no end user-identifiable information or confidential data.

To enable Sentry integration, simply turn on the `SENTRY_ENABLED` configuration parameter and restart NetBox:

```python
SENTRY_ENABLED = True
```

NetBox will begin generating error reports and sending them to our centralized ingestor. One of the biggest benefits of this community-powered arrangement is that we'll be able to correlate bugs by software release, operating system, and other deployment attributes.

![An example Sentry error report](/assets/images/posts/sentry-error-report.png)

Of course, it's possible to use your own Sentry ingestor too: You'll just need to define your custom DSN:

```python
SENTRY_ENABLED = True
SENTRY_DSN = "https://examplePublicKey@o0.ingest.sentry.io/0"
```

You can find more detail on Sentry configuration in the [NetBox documentation](https://docs.netbox.dev/en/stable/administration/error-reporting/#sentry).

