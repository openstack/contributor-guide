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
