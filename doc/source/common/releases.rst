########
Releases
########

OpenStack has a 6-month long release cadence with different release models that
projects can choose to follow.

This section allows you to:

* Understand the different release models that OpenStack components follow
* Know the structure of the different release models and how to work
  effectively in those to influence the future of OpenStack

Release Models
--------------

OpenStack consists of a large number of projects that form the main components
of an OpenStack cloud, from client libraries to lifecycle management
services. The different projects are different in nature which implies
different `release models
<https://releases.openstack.org/reference/release_models.html>`_ to follow.

The currently available options are the following:

* `cycle-with-rc
  <https://releases.openstack.org/reference/release_models.html#cycle-with-rc>`_
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
testing of new functionality added during the release. You need to ensure to
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

Stable Branches
---------------

Once a 6-month development cycle is completed the code for that release
is branched, in git, to a stable branch. For instance, when the Stein
release was completed a new branch in git, ``stable/stein`` was created.

Stable branches are kept as a safe source of fixes for high impact
bugs and security issues which have been fixed, on master, since the
release occurred. Given the stable nature of these branches, backports
to stable branches undergo additional scrutiny when they are proposed.
Proposed changes should:

* Have a low risk of introducing a regression
* Have a user visible benefit
* Be self contained
* Be included in master and backported to all releases between master
  and the stable branch in question

Project teams do point releases off stable branches when enough
changes accumulate in the stable branch to justify creating another release for
their project.

Stable branches proceed through different levels of maintenance as they
age.

+--------------+--------------------+--------------------------------------+
| State        | Time frame         | Summary                              |
+==============+====================+======================================+
| Maintained   | Approximately 18   | All appropriate bug fixes accepted   |
|              | months             | and releases are produced.           |
+--------------+--------------------+--------------------------------------+
| Extended     | While there are    | All appropriate bug fixes accepted.  |
| Maintenance  | community members  | No releases are produced and there   |
|              | maintaining it.    | is reduced CI commitment.            |
+--------------+--------------------+--------------------------------------+
| Unmaintained | 6 months from the  | The branch is under Extended         |
|              | time the branch is | Maintenance rules, but there are no  |
|              | made unmaintained. | maintainers.                         |
+--------------+--------------------+--------------------------------------+
| End of Life  | N/A                | Branch is no longer accepting        |
| (EOL)        |                    | Changes.                             |
+--------------+--------------------+--------------------------------------+

Before the Ocata release the Maintained and Extended Maintenance phases were
only 6 months long. This meant that each release went End of Life after
18 months. It was determined that this practice was not beneficial for
distributors or users of OpenStack. As a result the Maintained state
was updated to last 18 months and the Extended Maitenance time frame
was made flexible increasing the number of stable branches still accepting
fixes.

The state of all OpenStack releases may be seen on the
`OpenStack Releases <https://releases.openstack.org>`_ web page.

For more detailed information on Stable Branches and their
maintenance phases see the `Stable Branches
<https://docs.openstack.org/project-team-guide/stable-branches.html>`_
page.
