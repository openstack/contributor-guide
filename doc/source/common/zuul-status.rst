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
