---
layout: single
published: true
toc: false
title: "It's Time to Retire Your @cpan.org Email Address"
date: 2026-10-05 09:00:00 +0000
tags: pause email cpan.org guides cpan modules security metacpan authors cve
author: oalders
author_profile: true
excerpt: "Please remove uses of the @cpan.org email forwarding service where you can conveniently do so, as this makes it easier to contact you about security issues in your code. If you've updated your contact info on MetaCPAN, please check it again to ensure your update has not been clobbered."
header:
  overlay_image: /assets/images/header/eguidry-macbook-pro-keyboard.jpg
  teaser: assets/images/teaser/eguidry-macbook-pro-keyboard.jpg
  overlay_filter: 0.6
  caption: "Photo credit: [Macbook Pro Keyboard](https://www.flickr.com/photos/40082898@N00/4010965162) by [eGuidry](https://www.flickr.com/photos/eguidry/), [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/), cropped"
---

# It's Time to Retire Your @cpan.org Email Address

TL;DR: Please remove uses of the @cpan.org email forwarding service where you
can conveniently do so, as this makes it easier to contact you about security
issues in your code. If you've updated your contact info on MetaCPAN, please
check it again to ensure your update has not been clobbered.

On April 25, 2026, the Perl Network Operations Center (NOC) announced that
[the forwarding service for @cpan.org had been shut
down](https://log.perl.org/2026/04/cpanorg-email-forwarding-has-been-shut.html).
In the intervening months, we've been left in kind of a weird state, with some
people holding out hope that the forwarding service would resume, some folks
making an effort to stop using this forwarding address and others who were
blissfully unaware that the service had even been shut down.

This was not helped by the fact that a couple of different bugs in MetaCPAN
prevented profile updates from persisting. If you updated your
MetaCPAN profile over the summer, you may not have noticed that your profile was
quietly reset by a cron job while you were going about your day.

All of this has meant that email is going undelivered and also that it's that
much harder to contact authors whose primary email address is listed on
MetaCPAN as YOURPAUSEID@cpan.org. This comes into play more often than you may
think. The CPAN Security Group issues a lot of CVEs, and part of that process is
contacting the responsible authors. If the only public contact info you have
ends in @cpan.org, then we have to do more digging. We can often still find
the author, but it's time that could have been spent on other security-related
issues.

So today I'm taking this opportunity to remind PAUSE users that a) this email
service is gone permanently and b) it would be very helpful if you updated your
YOURPAUSEID@cpan.org address to be something else in the important places. You
won't be able to do it everywhere (like in tarballs you uploaded to CPAN over
the years), but please update your
[MetaCPAN profile](https://metacpan.org/account/profile) and consider not using this
address for your git commits or your GitHub profile. There is even more excellent
advice in [our June post](/2026/06/14/cpan.org-email-forwarding-shutdown.html).
I highly encourage you to take 2 or 3 minutes to absorb that information.

If you have not yet linked your PAUSE account to your MetaCPAN account, you
will not be able to do that for the foreseeable future. The existing linking
method sends a confirmation email to (you guessed it) your @cpan.org
address. The MetaCPAN team has not had the resources to come up with a new
solution to this yet, so please sit tight while we find a volunteer to do it.
