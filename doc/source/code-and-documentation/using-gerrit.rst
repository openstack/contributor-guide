############
Using Gerrit
############

.. note::

  This section assumes you have completed :doc:`../common/setup-gerrit` guide.

Pushing A Change
================

.. note::
   This is a quick start version. For a more in depth description of how to
   clone, create a patch and push the change, directions can be `found here <https://docs.openstack.org/infra/manual/developers.html#starting-work-on-a-new-project>`_

Following is a list of the commands that you need to know for your first
contribution:

To clone a copy of some repository::

    git clone https://git.openstack.org/openstack/<PROJECT_NAME>

.. note::
   You can find the same respositories using the search function here:
   http://git.openstack.org/cgit

After you've completed the Setup and Learn GIT section, the following command
configures the repository to know about Gerrit and installs the ``Change-Id``
commit hook. You only need to do this once per repository you clone::

    git review -s

To create your development branch (substitute branch_name for a name
of your choice). Its better to create a new branch for each patch than
working from master::

    git checkout -b <branch_name>

To check the files that have been updated in your branch::

    git status

To check the differences between your branch and the repository::

    git diff master

Assuming you have not added new files, you commit all your changes using::

    git commit -a

Read the `Summary of Git commit message structure <https://wiki.openstack.org/wiki/GitCommitMessages?%22Summary%20of%20Git%20commit%20message%20structure%22#Summary_of_Git_commit_message_structure>`_
for best practices on writing the commit message. When you are ready to send
your changes for review use::

    git review

If successful, Git response message will contain a URL you can use to
track your changes.

If you need to make further changes to the same review, you can commit them
using::

    git commit -a --amend

This will commit the changes under the same set of changes you issued earlier.
Notice that in order to send your latest version for review, you will still
need to call::

    git review

Tracking your Changes
=====================

After proposing changes, you can track them at
https://review.openstack.org. After logging in, you will see a
dashboard of "Outgoing reviews" for changes you have proposed,
"Incoming reviews" for changes you are reviewing, and "Recently
closed" changes for which you were either a reviewer or owner.
