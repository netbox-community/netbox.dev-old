---
title: "Migration Scripts for NetBox v3.2"
date: 2022-03-30
author: Jeremy Stretch
categories:
  - Tips and Tricks
tags:
  - extensions
---
With NetBox v3.2 due to be released next week, it's worth taking a moment to evaluate your upgrade readiness. While there aren't many major breaking changes in this release, there are two items you'll definitely want to double-check:

* The contact fields (name, phone, and email) are being removed from the site model
* The ASN field is being removed from the site model

You may recall that Netbox v3.1 introduced a dedicated "Contact" model, which enables much more efficient and complex contact assignment, and obviates the need for storing contact information directly on individual sites. Likewise, v3.1 also introduced a designated model for autonomous system number (ASN) tracking, rendering the site model's `asn` field obsolete.

To help expedite the upgrade process for organizations which still rely on data in any of these fields, we've published a set of [migration scripts](https://github.com/netbox-community/migration-scripts). These can be installed and run in your local NetBox instance to automatically replicate data from the legacy fields into the new models.

![Contact migration script in the NetBox UI](/assets/images/posts/netbox32-contact-migration.png)

As with any such process, it is highly recommended to perform a database backup immediately prior to running these, and to perform a "dry run" (without commiting changes to the database) first as a sanity check. While the behavior of the scripts is likely suitable for most cases, users are also encouraged to modify these if necessary to better fit their exact preferences. For example, you might want to limit the sites being migrated by tag or role. (Be sure to check out NetBox's [custom script documentation](https://netbox.readthedocs.io/en/stable/customization/custom-scripts/) too!)

With the relevant data safely migrated to the new models, you'll be ready for NetBox v3.2!

