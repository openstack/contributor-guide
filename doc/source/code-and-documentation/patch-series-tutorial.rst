########################################
Tutorial: Developing Changes In A Series
########################################

This tutorial walks through a simple scenario of developing multiple change
sets in a series on the same branch. If you wish, you can follow along, using
the `sandbox repository
<https://opendev.org/openstack-dev/sandbox/>`_, executing the
commands exactly as they're laid out.

If you are a visual learner, you may prefer
`this video <https://www.youtube.com/watch?v=mHyvP7zp4Ko&list=PLR97FKPZ-mD9XJCfwDE5c-td9lZGIPfS5&index=4>`_
which does roughly the same thing (but without ``git-restack``).

Here we go.

Start on a freshly-``pull``\ed master branch:

.. code-block:: console

  efried:~/openstack/sandbox$ git checkout master
  Switched to branch 'master'
  Your branch is up-to-date with 'origin/master'.
  efried:~/openstack/sandbox$ git pull --all
  <snip>

When you're working on a blueprint, you want to name your local branch
after the blueprint. For this example, we'll use
``bp/nova-cyborg-interaction``.

.. code-block:: console

  efried:~/openstack/sandbox$ git checkout -b bp/nova-cyborg-interaction
  Switched to a new branch 'bp/nova-cyborg-interaction'
  efried:~/openstack/sandbox$ git log --oneline -1 --decorate
  3d008a3 (HEAD -> bp/nova-cyborg-interaction, origin/master, origin/HEAD, gerrit/master, master) Merge "suggest change  punctuation to english punctuantion"

When you ``git commit`` (without ``--amend``), you're creating a new commit on
top of whatever commit you started at. If you started with a clean, freshly
``pull``\ed master branch, that'll be whatever the most recently merged commit
in the master branch was. In this example, that's commit ``3d008a3``.

So let's say I make an edit for my first patch and commit it:

.. code-block:: console

  efried:~/openstack/sandbox$ echo 'python-cyborgclient>=1.0' >> requirements.txt
  efried:~/openstack/sandbox$ echo 'python-cyborgclient==1.1' >> lower-constraints.txt
  efried:~/openstack/sandbox$ git add -A
  efried:~/openstack/sandbox$ git commit -m "Add cyborg client to requirements"
  [bp/nova-cyborg-interaction d76195e] Add cyborg client to requirements
   2 files changed, 2 insertions(+)
   create mode 100644 lower-constraints.txt
  efried:~/openstack/sandbox$ git log --oneline -2 --decorate
  d76195e (HEAD -> bp/nova-cyborg-interaction) Add cyborg client to requirements
  3d008a3 (origin/master, origin/HEAD, gerrit/master, master) Merge "suggest change  punctuation to english punctuantion"

I just made commit ``d76195e`` on top of ``3d008a3``. You'll notice my branch
name (``bp/nova-cyborg-interaction``) came along with me.

Now I'm going to make another change, but just part of it, a
work-in-progress commit:

.. code-block:: console

  efried:~/openstack/sandbox$ mkdir -p nova/pci/cyborg
  efried:~/openstack/sandbox$ touch nova/pci/cyborg/__init__.py
  efried:~/openstack/sandbox$ git add nova/pci/cyborg/__init__.py
  efried:~/openstack/sandbox$ git commit -m "WIP: Cyborg PCI handling"
  [bp/nova-cyborg-interaction f17f040] WIP: Cyborg PCI handling
   1 file changed, 0 insertions(+), 0 deletions(-)
   create mode 100644 nova/pci/cyborg/__init__.py
  efried:~/openstack/sandbox$ git log --oneline -3 --decorate
  f17f040 (HEAD -> bp/nova-cyborg-interaction) WIP: Cyborg PCI handling
  d76195e Add cyborg client to requirements
  3d008a3 (origin/master, origin/HEAD, gerrit/master, master) Merge "suggest change  punctuation to english punctuantion"

Now commit ``f17f040`` is on top of ``d76195e``, which is still on top of
``3d008a3`` (aka ``master``). Note that my branch name came with me again.

At this point, I push my series up to gerrit. Note that it makes me
confirm that I really want to push two commits at once.

.. code-block:: console

  efried:~/openstack/sandbox$ git review
  You are about to submit multiple commits. This is expected if you are
  submitting a commit that is dependent on one or more in-review
  commits, or if you are submitting multiple self-contained but
  dependent changes. Otherwise you should consider squashing your
  changes into one commit before submitting (for indivisible changes) or
  submitting from separate branches (for independent changes).

  The outstanding commits are:

  f17f040 (HEAD -> bp/nova-cyborg-interaction) WIP: Cyborg PCI handling
  d76195e Add cyborg client to requirements

  Do you really want to submit the above commits?
  Type 'yes' to confirm, other to cancel: yes
  remote:
  remote: Processing changes: new: 2, refs: 2
  remote: Processing changes: new: 2, refs: 2
  remote: Processing changes: new: 2, refs: 2, done
  remote:
  remote: New Changes:
  remote:   https://review.opendev.org/635341 Add cyborg client to requirements
  remote:   https://review.opendev.org/635342 WIP: Cyborg PCI handling
  remote:
  To ssh://review.opendev.org:29418/openstack-dev/sandbox.git
   * [new branch]      HEAD -> refs/for/master%topic=bp/nova-cyborg-interaction

Now if you go to either of those links - e.g.
https://review.opendev.org/#/c/635342/ - you'll see that the patches
are stacked up in series on the top right.

But oops, I made a mistake in my first commit. My lower constraint can't be
higher than my minimum in ``requirements.txt``. If I still had my branch
locally, I could skip this next step, but as a matter of rigor to avoid some
common pratfalls, I will pull the whole series afresh from gerrit by asking
``git-review`` to grab the *top* change:

.. code-block:: console

  efried:~/openstack/sandbox$ git review -d 635342
  Downloading refs/changes/42/635342/1 from gerrit
  Switched to branch "review/eric_fried/bp/nova-cyborg-interaction"

Now I'm sitting on the top change (which you'll notice happens to be
exactly the same as before I pushed it - again, meaning I could
technically have just worked from where I was, but see above):

.. code-block:: console

  efried:~/openstack/sandbox$ git log --oneline -3 --decorate
  f17f040 (HEAD -> review/eric_fried/bp/nova-cyborg-interaction, bp/nova-cyborg-interaction) WIP: Cyborg PCI handling
  d76195e Add cyborg client to requirements
  3d008a3 (origin/master, origin/HEAD, gerrit/master, master) Merge "suggest change  punctuation to english punctuantion"

But I want to edit ``d76195e``, while leaving ``f17f040`` properly stacked on
top of it. Here I use a tool called `git-restack
<https://docs.openstack.org/infra/git-restack/>`_ (run ``pip install
git-restack`` to install it).

.. code-block:: console

  efried:~/openstack/sandbox$ git restack

This pops me into an editor showing me all the commits between wherever
I am and the main branch (now they're in top-first order):

.. code-block:: console

  pick d76195e Add cyborg client to requirements
  pick f17f040 WIP: Cyborg PCI handling
  <snip>

I want to fix the first one, so I change ``pick`` to ``edit``:

.. code-block:: console

  edit d76195e Add cyborg client to requirements
  pick f17f040 WIP: Cyborg PCI handling
  <snip>

Save and quit the editor, and I see:

.. code-block:: console

  Stopped at d76195e...  Add cyborg client to requirements
  You can amend the commit now, with

    git commit --amend

  Once you are satisfied with your changes, run

    git rebase --continue

I fix ``lower-constraints.txt``:

.. code-block:: console

  efried:~/openstack/sandbox$ sed -i 's/cyborgclient==1.1/cyborgclient==1.0/' lower-constraints.txt

...and *amend* the current commit

.. code-block:: console

  efried:~/openstack/sandbox$ git commit -a --amend --no-edit
  [detached HEAD df226f7] Add cyborg client to requirements
   Date: Wed Feb 6 16:15:30 2019 -0600
   2 files changed, 2 insertions(+)
   create mode 100644 lower-constraints.txt

...and tell ``git-restack`` to proceed

.. code-block:: console

  efried:~/openstack/sandbox$ git rebase --continue
  Successfully rebased and updated refs/heads/review/eric_fried/bp/nova-cyborg-interaction.

If I had a taller series, and I had changed ``pick`` to ``edit`` for more than
one commit, I would now be sitting on the next one I needed to edit. As it is,
that was the only thing I needed to do, so I'm done and sitting on the top of
my series again.

.. code-block:: console

  efried:~/openstack/sandbox$ git log --oneline -3 --decorate
  e937eef (HEAD -> review/eric_fried/bp/nova-cyborg-interaction) WIP: Cyborg PCI handling
  df226f7 Add cyborg client to requirements
  3d008a3 (origin/master, origin/HEAD, gerrit/master, master) Merge "suggest change  punctuation to english punctuantion"

Notice that the commit hashes have changed for *both* commits (but not
for ``master``). The top one changed because it got rebased onto the new
version of the middle one.

Now if I push the series back up to gerrit, I get the same confirmation
prompt, and both changes get a new patch set. If you look at the top
patch in gerrit, you'll see that patch set 2 shows up as just a rebase.

.. :: TODO: Describe gotchas when restacking and the automatic rebase results in
      merge conflicts.
