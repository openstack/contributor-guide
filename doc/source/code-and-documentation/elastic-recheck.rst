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

What is elastic-recheck
=======================

elastic-recheck is a tool used to track failures in test jobs. It keeps a
repository of fingerprints for known bugs that are affecting jobs in the gate.
It is then used to both track the rates those bugs are being found and also to
leave comments in gerrit and in IRC when it has found a known bug fingerprint
in a failure.

elastic-recheck is built on top of an ELK (`Elastic Search
<https://github.com/elastic/elasticsearch>`_, `Logstash <https://github.com/elastic/logstash>`_,
`Kibana <https://github.com/elastic/kibana>`_) stack where we use Logstash to store all logs from CI jobs in an
Elastic Search cluster. We also host a `Kibana dashboard <http://logstash.openstack.org/>`_ which can be used
to run queries on the cluster and interacts with the data. elastic-recheck
queries the elastic-search cluster for the fingerprints.

You can see the current status of the bugs being tracked by elastic recheck at:
`Elastic Recheck <http://status.openstack.org/elastic-recheck/index.html>`_

.. image:: /_assets/elastic_recheck/er_status.png
   :scale: 65

Each graph shows how many matches were found for that fingerprint over the past
10 days. It also provides a link to both the launchpad page for the bug, and
the kibana dashboard for the underlying elastic-search query used for the
fingerprint.

elastic-recheck also has a page to show how many failures were encountered that
do not have a matching fingerprint. Typically the more failures that go
uncategorized the more unstable the gate is (and OpenStack as a whole).

You can find these pages at:

`Unclassified failed integrated gate jobs
<http://status.openstack.org/elastic-recheck/data/integrated_gate.html>`_
and
`Unclassified failed jobs
<http://status.openstack.org/elastic-recheck/data/others.html>`_

depending on which jobs you're interested in.

.. image:: /_assets/elastic_recheck/er_uncategorized.png
   :scale: 65

If you're interested in more of the theory and history behind the project, this
talk from the Juno OpenStack Summit provides a good overview:
`Elastic Recheck - Tools for Finding Race Conditions in OpenStack
<https://www.youtube.com/watch?v=Byo26Pioq1Y>`_

Tracking a new bug in elastic-recheck
=====================================

When you encounter a failure that's not being tracked by elastic-recheck
and you've looked through the logs to determine that it's not being caused
by the proposed change and is affecting other changes you can propose a new
elastic-recheck fingerprint.

This guide won't go into the details of tracing through the logs of a run
and finding a good fingerprint, since that's quite involved, dependent on the
job you're looking at, and already documented in a few places including:

 * `Tales From the Gate: How Debugging the Gate Helps Your Enterprise
   <https://www.openstack.org/videos/vancouver-2015/tales-from-the-gate-how-debugging-the-gate-helps-your-enterprise>`_
 * `elastic-recheck queries <https://docs.openstack.org/infra/elastic-recheck/readme.html#queries>`_

Once you've identified a message in the logs that can be used for
fingerprinting you need to turn that into an elastic-search query. You can
use any of the existing fingerprints as an example:
`opendev/elastic-recheck <https://opendev.org/opendev/elastic-recheck/src/queries>`_

You should also check any elastic search queries using kibana at:
`Logstash Search <http://logstash.openstack.org/>`_

Once you've constructed a query and checked in on elastic-search you should
create a yaml file in the queries directory of the elastic-recheck git repo.
The file name is the launchpad bug number for the bug and the contents are
the elastic-search query.
