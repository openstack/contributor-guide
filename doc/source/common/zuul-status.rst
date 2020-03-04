#######################
Checking Status in Zuul
#######################

.. note::

   This section assumes you have completed :doc:`/code-and-documentation/using-gerrit`.

This section allows you to:

* Monitor your patches as they get tested by Zuul
* Understand the underlying infrastructure and gating processes that
  OpenStack uses

What is Zuul
============

Zuul is a tool written and run by the OpenStack Infrastructure team that is
used to manage running continuous infrastructure jobs. It provides projects
with a way to define test jobs that will run on each proposed commit. These
tests are required to pass in order for any proposed patch to merge.

When you push a patch to gerrit zuul will automatically trigger jobs to verify
the patch functions properly.


Tracking Changes in Zuul status page
====================================

You can check the status of those jobs at any time by navigating to:
https://zuul.openstack.org/

.. image:: /_assets/zuul_status/zuul_status.png
   :scale: 65

This will show you the status on all jobs running in zuul currently. You can
expand jobs running on any patch by clicking on the box for a patch.

.. image:: /_assets/zuul_status/zuul_patch.png
   :scale: 65


To find your specific patch in zuul you can use the search bar and search
for the patch number. This will then filter what is displayed to just that
patch:

.. image:: /_assets/zuul_status/zuul_status_searchbar.png
   :scale: 65

Why do changes go first in the check queue?
-------------------------------------------

The OpenStack project uses what's called a `clean check` approach. This
is designed to keep flaky changes out of the gate. A change always needs
to pass the check before it enters the gate. If it fails in the gate, it
re-enters the check pipeline.


* If your change fails in the gate, then there is an increased chance
  it is introducing non-deterministic failure behavior. Forcing it
  to go through check again helps make that more apparent.
* This avoids approving changes that have no hope of ever passing
  due to pep8 or other trivial errors.
* It also helps with approving changes that had been sitting around
  with a 6-month-old passing check.

Changes in the gate pipeline are prioritized but also serialized.
If a change fails, all tests for changes behind that failing change
have to be restarted. If restarts after restarts happen, then
resources are never freed up for the check pipeline.

Therefore, having a stable gate pipeline is crucial and the clean
check requirement will help with the stable jobs.
