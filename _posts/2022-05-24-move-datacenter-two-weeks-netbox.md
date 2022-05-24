---
title: "How to Move a Datacenter in Two Weeks with NetBox"
subtitle: "How I found NetBox and learned to love documentation"
date: 2022-05-24
author: Sofia Eroshevich
categories:
  - War Stories
tags:
  - datacenter
  - migration
---
_Please note that all players have been anonymized to protect the guilty. Please also note that I have jumped ship several times during my formal IT education. You might see why._

I had just started my apprenticeship at this company—hardly past the three-month mark—when BigBoss told me I was to assist with the move of the company's servers. About nine racks' worth of equipment across the city, minimum downtime… you know the drill. _I_ don't at this point, but I think figuring out what equipment goes where and how it is connected is a good first step.

My direct superior helpfully points me to a folder on our network labeled “Server Documentation”. I see the file ending. These are Excel files. Uh oh.

A quick check reveals that not even half of our switches are in here. Somebody has attempted to visualise the whole deal by drawing rack outlines with the columns. It's colourful and pretty, yet not a single cable is part of the documentation. It is a complete and utter mess.

I get back to my superior and he agrees that the situation is hardly ideal. I'm just getting known in the company for my research skills, so I'm tasked to find us software that will allow proper documentation of all racks and interfaces.

An hour later, I have identified the two best candidates. First I present my favourite: NetBox, which I knew from an earlier internship, has all the features we need, is self-hosted, and it's open source!

"Open source?!" BigBoss laughs at that, "Open source software isn't suitable for enterprise applications!"

"Okay, then we probably need to go with $EnterpriseSoftware, which is hard to administer and doesn't have all the features we need, but at least it's way over budget." 

He looks at the costs.  
He looks at the capabilities.  
He looks at the costs again.

"Do a presentation for the C-Suite. If you can convince them, I'm fine with it."

Sure, apprentice, new software, C-Suite, software options that cost more than my salary in a year… no pressure!

In the end, the C-Suite wasn't hard to convince; also, I love convincing people. They liked that NetBox is an off-the-shelf solution for our exact problem and didn't seem too bothered by the fact that it was open source.

I would have loved to introduce them to the wonders of automation, in the form of the NetBox API, that would have done a lot of the heavy lifting in documenting the datacenter. But this is an old school kind of company, so the very Idea of automating something you could make apprentices do was frowned upon. Not like we had an approaching deadline or anything.

Next came a roll out in our testing environment, a couple "oohs" and "aahs" from my superiors, and a couple “I told you so”s I kept quietly in my head. They loved the multi-tenant option, allowing us to not only document our own racks, but also the customers' racks, without any possibility of a mix-up.

I think the documentation is solid enough to be able to direct a helper on location (even if that helper is non-technical staff), enabling shorter turn-arounds for any disruptions occurring at remote sites, in turn saving money, time, and sanity of the employee who doesn't have to drive out to some village.

Then we had to check every single connection by tugging a bit on the cables, taking care not to disconnect the productive environment, screaming over the racket of racks, and slowly untangling the organically grown infrastructure our predecessors had left us with. All told, we spend about 130 manhours just documenting the racks. Additionally, I spent twenty hours with a label printer, putting the UIDs NetBox had generated on the corresponding cables.

Being able to distinguish the kind, colour, length, transmission rate, and interfaces of every cable inside NetBox saved my life, or at the very least our deadline. If a future version could automate sitting on a server room floor and attaching tiny labels to hundreds of cables, I might just marry that version.

Armed with this shiny new documentation—our first single-point-of-truth—we even managed to plan ahead where to put equipment that was yet to be purchased. If the cabling was any indication, planning ahead was a first.

The fact that NetBox allows us to label devices throughout their lifecycle from “staging” to “decommissioning” brought another round of impressed "oohs" and "aahs" from my superior.

For the outsourced moving company, I printed A3 size posters with front and rear views of the racks they had to assemble. They also got binders with plans where each device had to go. I brought enough for everybody, and a couple more for us, documenting the cabling. NetBox even allows exporting everything to CSV files, which was amazing for setting up these binders.

Otherwise the move went almost flawlessly, and the included stress testing of NetBox was so convincing it's now part of the portfolio at that company.

Seems like NetBox is indeed suited for enterprise applications.

In summary: NetBox did everything we wanted it to, passed our security audit, and has the potential to do so much more, with options to document IPs, VMs, and entire networks down to the providers.

By the end, my superior acknowledged that the move was pretty much my project more than his, so if a tool can do that for an apprentice three months in, imagine what it can do for you.
