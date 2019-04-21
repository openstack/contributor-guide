###############################
Contributing Organization Guide
###############################

What is the Contributing Organization Guide?
============================================

A guide outlining the base requirements and recommendations for employees
looking to contribute to OpenStack.

Recommendations
===============

Developer Involvement
---------------------

Why we need to send technical people into the community?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

With technical people in the community, you will find it's easier to trigger
development tasks or discussions in the community to get the best chance of
integrating with your business/product plan.

You need people to maintain your product, just as the community needs people
to maintain projects in each release cycle to keep development going.

There are multiple chances in each release cycle to trigger development tasks
in the community. Bringing more technical decision to the community will help
you get more feedback and guidelines from developers and operators globally.
Also, help them to make better cycle goals which also be a benefit for you.

How many people you should send?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Depends on your own plan, but try to cover the range of project services that
you're using or plan to use for your services.

Getting involved in these projects means you can:

* Monitor the health of the project.
* Be involved in design and direction of the project.
* Being involved in and shape implementation discussions.
* Avoid carrying downstream patches.

The more people you have working upstream, the better attention your feature
will get. Providing more reviewers will definitely help merge your
implementation to projects. Code review is a bottleneck for landing patches,
more good reviews the faster code can land.

How long they should be there?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The ideal answer is to give the technical people as much percentage of their
time as you can give, and for as long as possible.

If your company is large enough to have the choice, giving engineers more time
to specialise and concentrate on specific areas tend to be more efficient than
having engineers continually context switching as they have to
wear multiple hats.

Having engineers spending more time upstream helps everyone by providing
continuous input and feedback to tasks that you set as high priority.
But it's more then that, OpenStack relies on `peer review
<https://governance.openstack.org/tc/reference/principles.html#we-value-constructive-peer-review>`_.
From landing code to its governance, to function the project needs
people in the community reviewing.

Further, having engineers in the community long term will also keep the
company ahead of the curve as they are embedded and engaged in the community
rather then popping in and out.

To put more simply, the more invested a company is in the community, the more
likely they are to earn a place of influence.

Why you need to sync with the technical community?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The community upstream is filled with passionate and intelligent people who
all want what's best for the project. Being involved means you can help shape
and improve the project.

Better yet, instead of forking or adding downstream
patches in your own products that you'd then need to carry, support and
maintain, which can be very costly.
You could push it upstream and get benefit from an entire community of
developers improving and maintaining it with you. Effectively removing most, if
not all of the additional cost and risk of maintaining it downstream.

It will also be better tested than anything developed internally because it
will be tested by the community and used more widely than just your customers.

All these extra developers means more eyes on code finding, fixing, and
improving the code. This means having a community of developers helping in the
development and improvement of your own infrastructure.

Remember many hands make light work.

Technical
---------

Code
^^^^

* Access to review.opendev.org for code review and code submission.

  * Port 29428/tcp is the Gerrit SSH API.
  * Port 443/tcp is also available to access gerrit but only recommended if
    opening port 29428 is not possible, as it requires generating a password in
    the gerrit interface rather than using ssh certificates, so is inherently
    less secure.

    * https://docs.openstack.org/infra/manual/developers.html#accessing-gerrit-over-https

  * For more information on how we use gerrit see:

    * :ref:`what_is_gerrit`
    * :doc:`../code-and-documentation/using-gerrit`

Internet Relay Chat (IRC)
^^^^^^^^^^^^^^^^^^^^^^^^^

* Access to chat.freenode.net port 6697/tcp (IRC communication)

  * If utilizing an IRC bouncer port 443, to the bouncer, may be used.
  * See :ref:`setup-irc`.

Suggestions
~~~~~~~~~~~

There are browser based IRC services, like irccloud, that will keep users
connected and use the standard HTTPS (443/tcp).

If connectivity to certain ports are locked down or are a problem,
a SOCKS server can be used to provide access.

Email Consideration
^^^^^^^^^^^^^^^^^^^

* Ability to receive E-mail from and send E-mail to addresses at
  lists.openstack.org (mailing lists)

  * Mailing list can be high traffic, consider permitting use of external mail
    services to handle the intake from community mailing lists.

* Consider an exception for standard email footers on emails being sent to the
  community mailing lists
* See :ref:`communication-mailing-lists`.

Operating System (OS) Considerations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

There are many components and projects related to running and developing
OpenStack all of which run on top of Linux. So a developer will need:

* Permission to run Linux and install other open source software on
  employer-supplied hardware.

Technical Events
^^^^^^^^^^^^^^^^

There are a number of technical events that are held where community,
project, and cross-project planning and networking happen in person. Although
this planning and networking does happen online outside these events you
should consider sending developers along to be involved.

Some technical events include:

* Project Technical Gatherings (PTGs)
* Summits and Forums
* Operator meetups

For more information on such events see: https://www.openstack.org/community/events/

Non-Technical
-------------

OpenStack is a global community. Interaction with the community means working
and interacting with people from different timezones and cultures, as such
there are other non-technical recommendations that help
facilitate engagement in the OpenStack community, these can be broken down into
three areas: communication, culture and expectations.

Communication
^^^^^^^^^^^^^

Being a global community, with members from across the globe being available
to occasionally work, talk or meet outside of typical office hours is
paramount.

Some asynchronous communication mediums, such as email and gerrit, are
heavily used, but at times these discussions can to be sped up by using more
synchronous mediums such as:

* IRC conversations

  * Working if developers from a different part of the globe
    may mean finding a time to chat on IRC when all parties are available.
  * Likewise, when reviewing patches, talking with a patch author in channel
    can greatly speed up reviews especially for more complicated patches.

* IRC meetings

  * All projects have regular meetings on IRC. Most these meetings alternate
    between two different timezones. Sometimes however, it is advantageous to
    get all developers working on a certain feature or project to be in one
    place at the same time.

* Other

  * Other projects may choose other ways of communicating depending on the
    developers in question. But transparency is important. Anything discussed
    should be logged or minuted for the rest of the OpenStack project and world
    to see.


Community Culture
^^^^^^^^^^^^^^^^^

* Timezones

  * The OpenStack community is spread across the different timezones, so always
    try be transparent to the greater community and if using a synchronous
    communication system to make feature/project decisions, make sure you make
    it possible for asynchronous input from members in other timezones.
  * Different timezones means different cultures, so be sensitive to
    these cultural differences. One example is to give non-native English
    speakers a chance to think and speak and if using a voice medium, please
    slow down.

* Titles held by community members are temporary and activities are not really
  linked to titles.

  * Everyone is in this together and are working for a better OpenStack.
  * Everyone who holds a title, such as PTL or a part of the technical
    committee are elected in. So titles are temporary.

* Forks are bad, contributing upstream is much better.

  * citing articles about how maintaining forks is generally an expensive and
    painful process (via links to further reading on effective open source
    community involvement)

* The community does not officially endorse Stackalytics, a contribution
  statistics gathering service hosted by Mirantis. The community does not
  encourage attempting to boost one's contribution statistics by
  proposing large quantities of low-value commits or voting on large
  numbers of change proposals without providing thoughtful reviews.
  Activities like this appear to other members of the community as an
  attempt to game the system and contributors who engage in this will
  often lose credibility for themselves and their employers in the community.
  Instead, contributors should try to engage deeply with a single project or a
  small number of projects to gain understanding of the software component and
  build relationships with the other contributors for that project.

* Focusing staff on particular project areas, or towards particular goals is
  more effective than asking them to track activity over many projects.

Expectations
^^^^^^^^^^^^

* Permission to agree to the OpenStack ICLA (required)
* Permission to occasionally work outside typical office hours
* A process to clear contributions from IP point of view
* Permission and budget to send contributors to events
* Expectation of travel to at least some events - does not need to be all

  * Should be prepared to write permission letter/visa letters/necessary
    letters for getting visas
  * The letters/decisions made on travel should be given out, ideally weeks
    or more, in advance
  * Permission to agree with terms of becoming an OpenStack Foundation
    Individual Member

* Consider signing up as a contributing organization member
