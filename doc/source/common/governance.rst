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
bylaws. Each of the types -- Platinum, Gold and Individual -- are represented
on a Board of Directors. The maximum numbers of members of each type are
eight, twenty four, and unlimited, respectively.

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
Discuss Mailing List and/or in Gerrit and elected by voting from the members
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
