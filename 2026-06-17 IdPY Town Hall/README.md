# IdPY Town Hall Discussion
_17 June 2026_

There have recently been several meetings to re-engage the community on IdPY work. We invite you to attend an IdPY Town Hall where we will share what has been discussed.

Meeting was attended by 20+ members of the IdPY community.

## MEETING RESOURCES
* [Recording](https://vimeo.com/1204357582?share=copy&fl=sv&fe=ci)
* Transcript - Available with the recording
* [Slides](https://github.com/IdentityPython/Meetings/blob/master/2026-06-17%20IdPY%20Town%20Hall/IdPY%20Town%20Hall%20SLIDES-%2017%20Jun%202026.pdf)

_Meeting was structured as an interactive discussion using Mentimeter._

---

### Meeting Chat Notes 
_(reactions to comments have been removed)_

* 00:24:53	Matthew E:	Here's the direct link if you want.  https://github.com/IdentityPython/Meetings/blob/master/2026%20DRAFT%20IdPY%20Technical%20Transition%20Charter.pdf

* 00:34:44	David:	Hi, I run SATOSA as an IdP at the University of Graz behind a Keycloak IdP to join it to the eduGAIN identity federation.
For this I made a fork: https://github.com/BotoX/SATOSA
and would be willing to contribute pull requests
  * 00:38:07	Ivan K:	Replying to "Hi, I run SATOSA as ..."
    That would be great! With the technical chapter we'll be setting for coding guidelines to ease reviews and align on the coding standards. Contributions are welcome in any case!

    The main problem is to have enough people that can dedicate time on the projects, do the reviews, and make progress.

* 00:37:31	David:	Also where did c00kiemon5ter go? They seemed like the only active maintainer.
    * 00:38:45	Ivan K:	Replying to "Also where did c00ki..." hi David, that'd be me ;)

  I agree about the lack of good documentation but there are just too many use-cases to be honest, reading the code was not too hard for me since it's python.

  Here's our config: https://git.botox.bz/BotoX/satosa-idp-proxy

* 00:41:21	Max M:	we're also running instances of SATOSA at TU Wien (vienna, austria) to connect some of our services to the eduGAIN interfederation; one of our setups is available here: https://gitlab.tuwien.ac.at/crdm/crdm-satosa-setup

  this setup was aligned with peter brand from ACOnet (austrian SAML federation) to at least pass some sanity checks :)

  i've opened a PR about adding our config as sample to the SATOSA github repo a while back but never got around to polish it up some
* 00:47:16	David:	we had no performance issues at all with satosa and python in general.
load average 0.00 but only around 30k requests per day.
but there's a memory leak in pyff with lxml yes.
i could probably look into fixing this, for now i just restart the pyff service every night.

  * 00:53:24	Ivan K:	Replying to "we had no performanc..."

    having said this, libxml2 is the most advanced xml library right now. The buildin python library is not geting everything right (esp, prefixes in qualified attributes).

* 00:52:17	Ivan K:	Unfortunately, lxml and specifically the C-libraries behind it (libxml2) are notorious for leaks.

* 00:57:48	Matthew E:	Regarding CI, I have created a Cookiecutter template for my Python projects that automates linting, testing, releases, and documentation. https://github.com/ResearchDataCom/templates

  The curated GitHub Actions workflows are here: https://github.com/ResearchDataCom/actions

  I'd love to see something similar in place with the IdPy projects.
* 01:00:43	Matthew E:	I feel the same way as Guisseppe, which is why I'm here and speaking as loudly as I am.  It's also why I'm willing to put time and effort into the project, even if just on my own outside of anything billable.

* 01:05:11	Laura P:	We are at the top of the hour. Thank you so much for coming. Contact information is on the screen. I hope you will join the mailing list, or contact me if you’d like to be involved in the upcoming technical meeting.
* 01:06:19	Ivan K:	Thank you everyone!
* 01:06:38	Charles:	Thank you very much Laura and team!
* 01:06:52	Matthew E:	Thanks all!  Nice to see you!
