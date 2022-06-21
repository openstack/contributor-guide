#####################
Using Elastic Recheck
#####################

.. note:: This section assumes you have completed :doc:`/common/zuul-status`

Allows you to:

* Enhance the automatic testing the community does on every patch submitted
  to gerrit
* Report recurring bugs so that you don't need to manually 'recheck'

What to do if a test job fails
==============================

When you submit a patch to gerrit and zuul returns the test results for the
jobs it ran, sometimes one of those tests fails. Most of the time this
indicates there is an issue with your proposed change and the tests are
catching it. Sometimes the test run might have tripped over an underlying
pre-existing bug in OpenStack. Additionally, some times the infrastructure for
running the tests might have had a failure. To figure this out you'll always
need to look at the logs from the failed job to understand what's happening.

OpenSearch
==========

For deeper investigation of related log messages across multiple builds of
jobs, a community-run `OpenSearch cluster
<https://governance.openstack.org/sigs/tact-sig.html#opensearch>`_ is
available, with both a WebUI for producing real-time graphs as well as a REST
API for more programmatic analysis.

Past and Future of Elastic Recheck
==================================

At one time, there existed a service to automatically analyze indexed job logs
in order to match them against curated queries for known bug signatures, and
leave helpful review comments on changes when those same failures were
identified in a new build. That service relied on an old suite of systems
fronted by logstash.openstack.org, which ceased operation in April 2022. A
recreation of that solution is in progress based on the community's new
OpenSearch backend, but is not available for general use yet.
