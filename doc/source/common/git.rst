.. _git:

###################
Setup and Learn GIT
###################

.. note::

   This section assumes you have completed :doc:`accounts` guide.

GIT
===

What is Git?
------------

Git is a free and open source distributed version control system that the
OpenStack community uses to manage changes to source code and documentation.

Git allows you to:

* Push and test `code, docs, infrastructure changes, and CI configurations <https://opendev.org/explore/repos>`_
* Push `Specifications <https://specs.openstack.org>`_
* Push `Use cases for features <https://specs.openstack.org/openstack/openstack-user-stories/>`_


Installation
------------

Mac OS
^^^^^^

#. Go to the Git `download page <https://git-scm.com/downloads>`_ and click
   **Mac OS X**.

#. The downloaded file should be a dmg in your downloads folder. Open that dmg
   file and follow the instructions on screen.

If you use the package manager `Homebrew <http://brew.sh>`_, open a terminal
and type::

    brew install git

Linux
^^^^^

For distributions like Debian, Ubuntu, or Mint open a terminal and type::

  sudo apt install git

For distributions like RedHat, Fedora 21 or earlier, or CentOS open a terminal
and type::

  sudo yum install git

For Fedora 22 or later open a terminal and type::

  sudo dnf install git

For SUSE distributions open a terminal and type::

  sudo zypper in git

Windows
^^^^^^^

`Windows Subsystem for Linux (WSL) <https://docs.microsoft.com/en-us/windows/wsl/about>`_
is available in Windows 10 Anniversary Update or later (build 1607+).
There is the possibility to install and run modern Linux Operating Systems:

* `Ubuntu 16.04 <https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6>`_
* `openSUSE Leap 42 <https://www.microsoft.com/en-us/store/p/opensuse-leap-42/9njvjts82tjx>`_
* `SLES 12 <https://www.microsoft.com/en-us/store/p/suse-linux-enterprise-server-12/9p32mwbh6cns>`_

All common tools like bash, git, and SSH will work out of the box.

Although Git `download page <https://git-scm.com/downloads>`_ provides Windows
installation binary, most OpenStack development tools (e.g., git-review)
unfortunately will not work well on Windows environment.

Configure Git
-------------

Once you have Git installed you need to configure it. Open your terminal
application and issue the following commands putting in your first/last name
and email address. This is how your contributions will be identified::

  git config --global user.name "Firstname Lastname"
  git config --global user.email "your_email@youremail.com"

.. note::

   Use the same email address that was used during the account setup.

Learning Git
------------

You can use `Git Immersion <http://gitimmersion.com/lab_02.html>`_ to work
through tutorials for learning git.

For reference, use the `Git Reference and Cheat Sheet <https://git-scm.com/doc>`_.

Commit Messages
===============

Commit messsages are the first things a reviewer sees and are used as
descriptions in the git log. They provide a description of the history of
changes in a repository. Commit messages cannot be modified once the patch is
merged.

Format:

- Summary Line
- Empty line
- Body
- Empty line
- Tags

.. note::

  Tags should be entered one per line.

Summary Line
------------

The summary line briefly describes the patch content. The character limit is 50
characters. The summary line should not end with a period. If the change is
not finished at the time of the commit, start the commit message with WIP.

Body
----

The body contains the explanation of the issue being solved and why it should
be fixed, the description of the solution, and additional optional information
on how it improves the code structure, or references to other relevant patches,
for example. The lines are limited to 72 characters. The body should contain
all the important information related to the problem, without assuming that the
reader understands the source of the problem or has access to external sites.

Tags
----

Tags are references used to link the change to other tools.

The following tags are required:

- The ``Change-id`` line is a unique hash describing the change,
  which is generated automatically by a Git commit hook. This should not be
  changed when rebasing a commit following review feedback, since it is used
  by Gerrit, to track versions of a patch.

StoryBoard specific tags:

- ``Task``: 1234: the number of the task in Storyboard implemented by the
  change. This will auto update the task to 'Review' status and assign it
  to you when you push the patch.
- ``Story``: 1234567: the number of the story in Storyboard to which the task
  being implemented belongs. This will post a comment on the story with a
  link to your patch.

Launchpad specific tags:

- ``Closes-Bug``: #123456789: use ``Closes-Bug`` if the commit is intended to
  fully fix and close the bug being referenced. Use the Launchpad ID of the bug
  for the number; Gerrit automatically creates a link to the bug.
- ``Partial-Bug``: #123456789: use ``Partial-Bug`` if the commit is only a
  partial fix and more work is needed. Use the Launchpad ID of the bug
  for the number; Gerrit automatically creates a link to the bug.
- ``Related-Bug``: #12456789: use 'Related-Bug' if the commit is merely
  related to the referenced bug. Use the Launchpad ID of the bug
  for the number; Gerrit automatically creates a link to the bug.
- ``Partial-Implements``: Use this tag if the change partially implements
  a Launchpad blueprint. Use the name of the blueprint as an ID.
- ``Implements``: Use this tag if the change fully implements
  a Launchpad blueprint. Use the name of the blueprint as an ID.


The following tags are optional; however, their use is recommended if they are
applicable to the patch:

- The ``DocImpact`` tag contains a comment about why
  the change impacts documentation. Put DocImpact on a line by itself.
  Use this tag to indicate that documentation is either contained in the
  patch or has documentation impact.
  When this tag is included in a commit
  message, Gerrit creates a bug for the project affected by the change for task
  tracking, or move to the openstack-api-site as needed.
- The ``APIImpact`` tag contains a comment about why
  the change impacts a public HTTP API. Put APIImpact on a line by itself.
  Use this tag to indicate that the patch impacts a public
  HTTP API. When this tag is included in a commit message,
  the API_Working_Group can use it to help find relevant reviews.
- The ``SecurityImpact`` tag is used to indicate that a change has
  security implications and should be reviewed by the OpenStack Security Group.
- The ``UpgradeImpact`` tag contains a comment
  about why the change impacts upgrades. It is used to indicate that a change
  has upgrade implications for those doing continuous deployment or N to N+1
  upgrades. Also consider updating the 'Upgrade Notes' section in the release
  notes for the affected project.
- The ``Depends-On``: <gerrit-change-url> tag is used to refer to a change
  the current one depends on. Use the permalink of the change.

