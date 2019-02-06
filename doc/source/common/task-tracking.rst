#############
Task Tracking
#############

This section provides information on Storyboard and Launchpad task trackers.
You can learn about Storyboard stories and tasks, boards and worklists, and
Launchpad blueprints and bugs.


.. note::

   This section assumes you have completed :doc:`accounts` guide.

This section allows you to:

* Understand the different tools OpenStack uses for task management
* Know how to report bugs and propose features

What Task Trackers does OpenStack use?
======================================

Each project is different in the process of reporting bugs and planning new
features. There are however two main tools that projects use: Launchpad and
Storyboard.

.. note::

   Before raising a bug, story or feature request it's important to note that not
   all projects do the same thing. It's best to go check with the project to see
   how they handle these requests. For details on how to contact
   a project check the `project list
   <https://governance.openstack.org/tc/reference/projects/index.html>`_.

.. _storyboard:

Storyboard
==========

Storyboard is a kanban style task tracking system created and maintained by
the community. It was designed API-first and was engineered to support the
coordination of cross project work. Items tracked are stories and tasks.
A story can be a bug or a new feature, while tasks are the smaller todo's
required to complete the story.

For information on how to use storyboard, please see `the user interface manual <https://docs.openstack.org/infra/storyboard/gui/tasks_stories_tags.html>`_.

For other information about the project itself, please check out `their documentation <https://docs.openstack.org/infra/storyboard/>`_.

.. image:: /_assets/task_tracking/Storyboard.png
   :scale: 40

Stories & Tasks
---------------

A story is a desired change. Whether it is a bug or a new feature, both are
essentially a code change. Tasks are sub items of the story; they are tied
to specific projects. As an example, a story could be to invent some new
feature A, and tasks would be change in project X, change in project Y, and
change in project Z. Those changes need to merge in order to complete feature
A.

Boards & Worklists
------------------

Worklists and boards are different ways of organizing work. It is up
to the project team how stories are organized. They could be sorted by
milestone. A lane could have all the bugs or all the new features. It
depends on the teams way of organizing and coordinating work. Order of
stories in a worklist could convey priority as well.

.. _launchpad:

Launchpad
=========

Launchpad is the original task tracker used by OpenStack projects to organize
and target work to milestones and releases. It uses UbuntuOne for
authentication as it is managed by Canonical. Items tracked are either bugs
or blueprints.

.. image:: /_assets/task_tracking/Launchpad.png
   :scale: 40


Blueprints
----------

In Launchpad, a new feature is called a blueprint. To file a new
blueprint, click the 'Register a blueprint' button on the right.

On the next screen you are prompted to add details including its name
and title.

.. image:: /_assets/task_tracking/LP-overview.png
   :scale: 30

These are different in that the name is what is used in the generated
url and the title is what displays when blueprints are listed out
(name: new_ibm_driver title: New IBM ISCSI Driver). The next most
important part is the summary- a description of the code change, where
most of the details about the implementation are. After that, there
are several optional fields you may wish to fill in- a specification
url, assignee, drafter, and approver. The last two fields before
registering have default values- status and propose for a sprint. For
most teams, it is typical to leave the default values.

It is possible to update all of this information except the name and
title after the blueprint is registered. When you have finished
filling out all of the information you care to include, it is good to
communicate with the project team lead that you have filed a
blueprint.

.. image:: /_assets/task_tracking/LP-bp.png
   :scale: 40

.. note::

   Not all projects use the blueprints feature of Launchpad, you should contact the
   project to see how they handle feature requests. For details on how to contact
   a project check the `project list
   <https://governance.openstack.org/tc/reference/projects/index.html>`_.

Bugs
----

Bugs are pretty self explanitory- some unexpected or unintended behavior of the
software. To report a bug you have found in Launchpad, click the 'Report a bug'
button from the project's overview page.

To get to the details of reporting the bug you fill in the summary
line and click 'next'.

.. image:: /_assets/task_tracking/LP-bug.png
   :scale: 40

Based on the summary line, Launchpad will do a quick query to see if
there has been anything reported already that might be the same issue
you are trying to report. It is important to look through these to
avoid filing duplicate bugs and creating redundancies in the bug
index. If you do not see a bug that sounds like the issue you are
reporting, you can click the 'No, I need to report a new bug' button.

.. image:: /_assets/task_tracking/LP-bug-2.png
   :scale: 40

After clicking that button, the further information field will appear
along with the 'This bug is a security vulnerability' radio box. You
can edit the summary line to differentiate it from the other bugs
Launchpad thought it was similar to, add details like the setup you
were using, what you were doing when you hit the unexpected behavior,
the error codes you encountered, etc.

If the bug is related to a security vulnerability it is important to
click the box to alert the Vulnerability Management Team to the issue.
When you feel you have added all of the information needed, go ahead
and submit the bug report. For more information about the full process
for reporting security vulnerabilties, please continue reading `this
page <https://security.openstack.org/vmt-process.html>`_.

.. image:: /_assets/task_tracking/LP-bug-3.png
   :scale: 30

It is a good idea to check back on the bug routinely if you aren't
actively working on solving it to make sure people haven't asked for
more information about the issue. If someone has commented on the bug,
try to respond with the details they need.

**Bug Status**
All bugs have a status lifecycle. They start as 'New' and move to
other statuses from there depending on what all is included in the
description and if others can duplicate the issue. Resolved statuses,
meaning there is no more work to be done on the bug are: 'Fix
Released', 'Invalid', or 'Won't Fix'.

.. list-table::
   :widths: 20 100

   - * `New`
     * The bug was just created
   - * `Incomplete`
     * The bug is waiting on input from the reporter
   - * `Confirmed`
     * The bug was reproduced or confirmed as a genuine bug
   - * `Triaged`
     * The bug comments contain a full analysis on how to properly fix the
       issue
   - * `In Progress`
     * Work on the fix is in progress, bug has an assignee
   - * `Fix Committed`
     * Not used
   - * `Fix Released`
     * The fix has been merged into an official branch
   - * `Invalid`
     * This is not a bug
   - * `Opinion`
     * This is a valid issue, but it is the way it should be
   - * `Won't Fix`
     * This is a valid issue, but we don't intend to fix that
