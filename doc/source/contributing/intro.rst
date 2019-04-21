######################
Introduction and Goals
######################

What is the Contributor Guide?
==============================
First it's important to note that we're not just talking about code projects.
OpenStack contributions come in different forms such as running meet ups,
identifying use cases (Product Working Group), documentation, testing, etc. Our
goal is to have these contributions valued equally.

The Contributor Guide aims to provide common documentation for all OpenStack
Contributors and help with on-boarding efforts.

Having the common documentation worked on by various projects will better help
prevent duplicated efforts, inconsistent documentation, and will also provide
more accurate information. Projects that have zero/outdated documentation can
also just use the Contributor Guide.

Where the Guide Is Used
=======================
At various OpenStack events, the Contributor Guide is used to help various
on-boarding programs:

* `The OpenStack Upstream Institute <https://docs.openstack.org/upstream-training/>`_
* `The Certified OpenStack Administrator Exam <https://www.openstack.org/coa>`_
* Project team on-boarding sessions

Project Specific Contributor Guides
===================================
Project teams should still have their own contributor documentation to cover
things listed under `Examples of Documentation that's NOT Common`_. A couple
examples of project team specific contributor guides are the `Nova team's
<https://docs.openstack.org/nova/latest/contributor/index.html>`_ and the
`Documentation team's <https://docs.openstack.org/doc-contrib-guide/>`_.


Adding/Updating Content
=======================
Before you modify or add new content first get familiar with OpenStack's
code/documentation practices. You can read the
:doc:`/code-and-documentation/index`
for getting started.

Once you've read through the guide, use git to clone the Contributor Guide
repository::

  git clone https://opendev.org/openstack/contributor-guide


Content Guidelines
==================
* No wall of text. The reader should feel like they can finish things on the
  page in five minutes, instead of having yet another forgotten tab that
  they'll never get back to.
* Use screen shots.
* Avoid covering every issue that can be hit along the way. Case by case basis
  will be accepted depending on how common it is.
* No videos please. They're way too complicated to keep updated.

Common Content Only
-------------------
As the Contributor Guide is meant to be general so everyone can use it, here
are some helpful examples of what should be contributed. Examples of things
that are **not** common should be in your project team's specific documentation
which will be listed in the Contributor Portal.

Examples of Common Documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
* Setting up Git.
* Setting up IRC to communicate.
* Setting up Mailing Lists to communicate.
* Setting up appropriate accounts to contribute like Gerrit, Storyboard and
  Launchpad.
* How to vote in elections.

Examples of Documentation that's NOT Common
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
* Some specific software tool only your project team uses.
* Specific procedures for doing things like bug triage.

Examples of Good Documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Use chapters that have already been accepted to get a feel of what we're
looking for.

* :doc:`/common/irc`
* :doc:`/common/git`
* :doc:`/common/setup-gerrit`

How Can I Start Helping?
========================
Bug reports and tasks are all recorded in `Storyboard
<https://storyboard.openstack.org/#!/project/913>`_. If something isn't
assigned, it's available for you to take.

Get Help Contributing
=====================
We want you to succeed! You can ask for help on `IRC Freenode
<https://webchat.freenode.net/>`_ in channel #openstack-doc. You can also ask
for help on the `OpenStack Discuss Mailing list
<http://lists.openstack.org/cgi-bin/mailman/listinfo/openstack-discuss>`_ prefixing
your email subject with '[contributor-guide]'. If you're not familiar with
these ways of communicating, read the :doc:`/code-and-documentation/index`.
