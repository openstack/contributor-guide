####################
OpenStack Governance
####################

The OpenStack community has a few different groups and roles for `governance
<https://governance.openstack.org/>`_, leadership, and community participation.
Each operates in a different sector of the community but being aware of each of
them is useful.

This section allows you to:

* Understand the governance model of OpenStack
* Know how to participate in groups that interest you and influence the future
  of OpenStack

Committees
==========

Foundation Board of Directors
-----------------------------

The OpenStack Foundation is a non-profit "whose purpose is to develop, support,
protect, and promote" OpenStack. It has a set of `bylaws
<https://www.openstack.org/legal/bylaws-of-the-openstack-foundation/>`_ and a
board of directors. The Foundation has three types of members, defined by the
bylaws. Each of the types—Platinum, Gold and Individual—are represented on a
Board of Directors. Currently there are 24 directors, eight of each type.

Individual members of the foundation vote once a year (usually near the start
of the calendar year) for the individual directors. Individuals who wish to
join the Foundation can learn more at :ref:`foundation account`.

Technical Committee
-------------------

The `OpenStack Technical Committee <https://governance.openstack.org/tc/>`_
(TC) provides governance and technical oversight of the open development of
OpenStack. They validate projects applying to be part of the official
OpenStack project and provide an ultimate appeals board for technical
decisions. The `Technical Committee Charter
<https://governance.openstack.org/tc/reference/charter.html>`_ describes the TC
in more detail.

The 13 Members of the TC are elected for one year terms, six at one election,
seven at another election six months later. They are elected by
:ref:`Active Technical Contributors <atc>`.

User Committee
--------------

The `OpenStack User Committee <https://governance.openstack.org/uc/>`_ (UC)
serves the users of OpenStack, representing them to the rest of the OpenStack
community. The `User Committee Charter
<https://governance.openstack.org/uc/reference/charter.html>`_ describes the UC
in more detail.

The 5 members of the UC are elected to one year terms, three at one election,
two at another election six months later. They are elected by
:ref:`Active User Contributors <auc>`.

Official OpenStack projects
===========================

Official OpenStack projects are the projects under the governance of the
Technical Commitee. Official OpenStack projects are listed in the
`OpenStack Project Teams page
<https://governance.openstack.org/tc/reference/projects/index.html>`_.
Most well-known official OpenStack projects are listed in the `project
navigator <https://www.openstack.org/software/project-navigator>`_. It
is not mandatory for a project to become an official OpenStack project.

Requirements for the official OpenStack projects are listed
`in the wiki of the Technical Commitee
<https://governance.openstack.org/tc/reference/new-projects-requirements.html>`_.

Benefits for official OpenStack projects:

* Contributors get to vote in the Technical Committee election
* Can publish to `docs.openstack.org <https://docs.openstack.org/>`_ and
  `developer.openstack.org <https://developer.openstack.org/>`_
* The teams get space at `OpenStack Summits
  <https://www.openstack.org/summit/>`_ and `Project Team Gatherings (PTG)
  <https://www.openstack.org/ptg/>`_
* Get marketing from the OpenStack Foundation
* Can participate in common programs, like `mentoring
  <https://wiki.openstack.org/wiki/Mentors>`_ and `internship
  <https://wiki.openstack.org/wiki/Outreachy>`_ to help with on boarding
* Get guidance from community members and leaders
* Its activities are under the oversight of the Technical Committee

To propose a project to be an official OpenStack project the project's
information should be added to the *reference/projects.yaml* file of the
*openstack/governance* repository. Anyone can propose changes to the file.

Groups
======

.. _special-interest-groups:

Special Interest Groups
-----------------------

OpenStack `Special Interest Groups <https://governance.openstack.org/sigs/>`_
are working groups that operate within the entire OpenStack community to
address interests and concerns of all participants with a shared interest.

Roles
=====

.. _atc:

Active Technical Contributor (ATC)
----------------------------------

Individual Members of the Foundation who have contributed to any of the
official OpenStack project repositories over the last two 6-month release
cycles are automatically considered as ATCs.

In specific cases you can apply for an exception to become an ATC, for further
information please see the `relevant section of the Technical Committee Charter
<https://governance.openstack.org/tc/reference/charter.html#voters-for-tc-seats-atc>`_.

Active Project Contributor (APC)
--------------------------------

If you have the ATC status, in the official OpenStack project where you
contributed over the last two 6-month release cycles you are considered to be
an Active Project Contributor.

Only APCs can participate in the election process to vote for the next PTL of
the team.

Project Team Lead (PTL)
-----------------------

Official project teams within OpenStack have a `Project Team Lead
<https://governance.openstack.org/tc/reference/charter.html#project-team-leads>`_.
These individuals coordinate the day to day operation of the project, resolve
technical disputes within the project, and operate as the spokesperson and
ambassador for the project.

Project Team Leads are `elected
<https://governance.openstack.org/tc/reference/charter.html#election-for-ptl-seats>`_
for each release cycle by Active Project Contributors: individuals who have
contributed to the project in the last two release cycles.

Core Reviewer
-------------

Official OpenStack projects have a project team consisting of core reviewers
and contributors.

Core reviewers are responsible for:

* Defining and maintaining the project mission
* Reviewing bug reports and deciding about their priority
* Reviewing changes and approving them when it meets the design and coding or
  documentation standards of the project

Core reviewers have '+/-2' and 'W+1' rights in Gerrit that is required for
blocking or approving a patch.

New core reviewers are nominated by someone from the existing team on the
Developer Mailing List and/or in Gerrit and elected by voting from the members
of the core team of the project.

.. _auc:

Active User Contributor (AUC)
-----------------------------

The user community is crucial for OpenStack and their participation is highly
encouraged.


Community members who have engaged in community functions listed in the
`related section of the User Committee Charter
<https://governance.openstack.org/uc/reference/charter.html#active-user-contributors-auc>`_
are considered to be Active User Contributors.

The User Committee chairs are elected from and by the group of AUCs.

Releases
========

OpenStack has a 6-month long release cadence with different release models that
projects can choose to follow.

Release Models
--------------

OpenStack consists of a large number of projects that form the main components
of an OpenStack cloud, from client libraries to lifecycle management
services. The different projects are different in nature which implies
different `release models
<https://releases.openstack.org/reference/release_models.html>`_ to follow.

The currently available options are the following:

* `cycle-with-milestones
  <https://releases.openstack.org/reference/release_models.html#cycle-with-milestones>`_
* `cycle-with-intermediary
  <https://releases.openstack.org/reference/release_models.html#cycle-with-intermediary>`_
* `cycle-trailing
  <https://releases.openstack.org/reference/release_models.html#cycle-trailing>`_
* `independent
  <https://releases.openstack.org/reference/release_models.html#independent>`_
* `untagged
  <https://releases.openstack.org/reference/release_models.html#untagged>`_

Release Schedule and Planning
-----------------------------

The majority of the official OpenStack projects follow the release schedule
set by the Release Management Team.

The 6-month cycle is divided into three milestones and a usually one-month long
stabilization period with release candidates.

The first period of a cycle includes more focus on planning, which is why the
PTGs are scheduled right after the releases. This is the phase when you should
upload your specs for review and use the mailing list, project channels and
meetings on IRC to discuss any parts of your design that might be in question.

After the first milestone, some projects focus more on the development and bug
fixing activities, while other projects might still accept new ideas to
implement in that cycle.

The third period of a release is focusing on finishing the implementation and
testing of new functionality added during the release. You need to esnure to
add new tests in Tempest and have documentation covered as well before the
third milestone. During this phase the core review team can choose to focus on
higher priority features only. They make their decision about priorities either
at the PTG or soon after, some time before the first milestone of a release.

Some projects also have different dates through a release cycles as internal,
project-specific deadlines, like spec-freeze or code-freeze. You need to make
sure you are aware of the freeze dates which you can find on the `release
schedule page <https://releases.openstack.org>`_.

After the third milestone the community is focusing on stabilizing the release
by putting more emphasis on testing and fixing bugs. The projects following
the release cycle have their release candidates tagged after the third
milestone. There are no limits to release candidates, but the goal is to keep
the number low and fix all the critical issues that got identified by
milestone-3.

Having the main projects following the release cycle ensures that all these
projects release at the same time so these can be picked up by downstream
teams to package and further distribute.
