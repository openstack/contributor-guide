###########################
How to Become a Patch Guru?
###########################

When you are working on implementing a new feature or adding documentation to
an already existing one it is easy to get carried away by the work itself and
forget about the unwritten rules of constructing your changes.

This section will guide you through how to create patches that people will want
to review.

Allows you to:

* Know how to structure a patch that makes it easier to maintain throughout
  the review process
* Know how to structure a patch that is easier for community members to review

The Right Size
==============

Reviewing large patches is very inconvenient and time consuming therefore we
always suggest to break down your changes into smaller blocks.

While there is no magic number try to **keep the size of your changes as small
as possible**, but under a few hundreds of lines changed total. Patches that
are test heavy with little code change require as much effort as code heavy
changes.

In rare occasions when there is no good logical breakdown for a change and your
patch can grow to a thousand lines or more. In some cases it is acceptable as
you cannot extract the related test changes to another patch for instance, but
it's not highly recommended.

Always try to extract as much as you can into other patches, like documentation
or logical parts of the functionality that do not depend on common functions
in a lower layer.

Longer patches require more time to review; wherever you can, keep the length
reasonable. And where you can't, you can help the reviewers by adding code
comments and writing a detailed commit message to describe the changes you
introduced in your patch.

Patch Chains, Depends-On Tag and Gerrit Topics
==============================================

In the case of complex feature implementation work when you need to introduce
changes to multiple modules of the same project or multiple projects you need
to be very careful with managing the dependencies.

There are multiple options to choose from depending on the structure of your
design. You can either organize the changes in patch chains or you can use the
'Depends-On' tag.

Depends-On Tag
--------------

When you have changes in multiple project repositories you can mark dependent
patches with the 'Depends-On' tag. The tag will appear as a link in the
commit message which helps you and also the reviewers to track and navigate
between the dependencies of your changes.

The 'Depends-On' tag is a marker on your changes and when used
a patch cannot be merged until all its dependencies are landed.

The tag can be applied to patches proposed for the same repository as well. In
that case the changes are separate enough to be kept independent which means
that if you need to fix changes from review comments you can do it on a per
patch basis. It is also true for rebasing each patch.

.. note::

   In case you use the 'Depends-On' tag you need to download all the changes
   for a feature implementation or documentation change to test the feature or
   build the documentation with all the changes applied. Git will not take care
   of handling the dependencies automatically in this case.

Patch Chains
------------

In some cases when you break down the required changes to smaller blocks you
cannot avoid having direct dependencies between them that prevents you from
having independent changes. You need to organize your changes in a chain to
maintain the dependencies which requires some additional care when you work
with these changes.

Even if you have a chain of patches you still need to keep code changes and
related tests in one patch as you cannot guarantee that both land in time for a
release.

When you have a chain Gerrit helps you by listing all the commit titles in the
'Related Changes' column on the top right corner of the Gerrit UI. The titles
are also links which help you navigate between the changes to review them when
you upload a new version.

How to Handle Chains?
---------------------

A patch chain is easy to handle if you keep in mind a few recommendations:

* Always have a local branch for these changes to ensure that you don't mix it
  together with changes related to another feature or bug fix.

* Always handle a chain as one block of changes by rebasing the whole chain and
  keep it up to date when you modify a patch to fix review comments or add
  changes to it.

* To modify a patch within a chain you will need to use interactive rebase:

.. code-block:: console

   git rebase -i HEAD^

You need as many '^' as the number of the patch you want to edit first from the
top of the chain. Alternatively you may wish to use `git-restack
<https://docs.openstack.org/infra/git-restack/>`_, which figures out the
appropriate ``git rebase`` command for you.

Gerrit also provides you options to edit the patch itself or only the
commit message and a few more for more advanced changes, like modifying
the author.

* To download the full chain you need to download the top patch and Git will
  automatically download all the dependent patches in the chain.

* If you only need to modify the top patch in the chain that can be done the
  same way as you update individual patches.

* When you upload changes in a chain only the patches that got updated will be
  uploaded. This also means that the review scores on lower patches in the
  chain will be untouched.

* Always check the changes you made to each patch and be careful that you
  applied the changes in the right one as patches still get merged individually
  and there is no guarantee that the whole chain gets landed at the same time.

For a more in-depth look at managing patch chains, see
:doc:`/code-and-documentation/patch-series-tutorial`.

Gerrit Topics
-------------

You have the option to specify a topic for your changes when you upload them
for review. While Gerrit topics will not add dependency to your patches you can
apply a search based on the topic that will show you all the relevant changes
in all the projects where there are patches with the same topic. Gerrit will
also show them to you in the 'Same Topic' column on the top right corner of
the page of a review.

This is a good way to help tracking related changes, let that be a feature
implementation, bugfix or documentation work.

How to Structure Your Changes?
==============================

When your work item grows above a particular size and you need to upload
multiple patches it is crucial to structure it well in case of both patch
chains and independent changes.

It is a good practice to group changes by modules in a project, for instance
virt driver changes, compute manager and api changes in case of OpenStack
Compute.

By grouping the changes per module you can also construct the chain or
dependencies by the hierarchy of the components and always keep the API changes
last as that will enable the new functionality and that change will depend on
everything else you needed to touch for your design.

Beyond this you can also look into the functionality to find smaller building
blocks and make your changes smaller. For instance changes to an object can be
implemented first that you will use later when you implement new API
functionality.

The Right Content
=================

Changes that are not related to any feature implementation or bug report can be
uploaded but are less welcomed by reviewers.

Improvement to either the code or documentation should be part of a larger
effort, like if you would like to fix typos in documentation then you should
do it for a larger block, like a whole guide. It is also preferred to report a
story with tasks for a work item like this that can be tracked later.

It is similar for code improvements. As the community is large and world-wide
we have coding guidelines, but the style of each individual can still be very
different. We don't enforce a particular coding style, therefore changes
related to fix that are less welcomed and are sources of very opinionated
arguments that should be avoided.

In case of code refactoring work which makes the code more readable and easier
to maintain by restructuring methods and deleting unused code snippets it is
highly encouraged to consult with the project team and report a story in
StoryBoard first and then upload the relevant changes to Gerrit for review.
