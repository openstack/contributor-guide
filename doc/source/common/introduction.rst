############
Introduction
############

What is OpenStack?
==================

Software
--------

OpenStack is a software package that provides a cloud platform for Public and
Private cloud covering various use cases including Enterprise and Telecom.
The main focus is on Infrastructure as a Service (IaaS) cloud and additional
services built upon IaaS.
The Technical Committee maintains an evolving `vision for OpenStack
clouds
<https://governance.openstack.org/tc/reference/technical-vision.html>`_
describing the overall design scope for an OpenStack cloud and the
principles of cloud platforms in general, and OpenStack in particular,
that each service within OpenStack is expected to follow.

As a software, OpenStack is built from a set of microservices which can be
combined into different setups based on the actual need.
The services provide REST APIs for their users. These can be the cloud
operators or other services. To make the usage of the APIs easier it is
possible to use Software Development Kits (SDKs) which are also developed
as projects inside the OpenStack community.

Documentation is very important for the community so you can find guidelines
about how to install and use the services developed by the project teams on
the `documentation website for OpenStack <https://docs.openstack.org>`_.

The services developed by the community are available as tarballs to install
them from source and are also picked up and packaged to make it available for
different Linux distributions or as part of OpenStack distributions.

Map of OpenStack projects
^^^^^^^^^^^^^^^^^^^^^^^^^

.. image:: /_assets/introduction/map-of-OpenStack-projects.png
    :scale: 80 %

Community
---------

OpenStack is a community working towards one mission:

To produce a ubiquitous Open Source Cloud Computing platform that **is** easy
to use, simple to implement, interoperable between deployments, works well at
**all** scales, **and** meets the needs of users and operators of both public
**and** private clouds.

OpenStack provides an ecosystem for collaboration. It has infrastructure for

* Code review
* Testing
* CI
* Version control
* Documentation
* a set of collaboration tools, like a wiki, IRC chanels, Etherpad
  and Ethercalc.

The four opens
^^^^^^^^^^^^^^

The basic princinples of the OpenStack community are the four opens.

* `Open source <https://governance.openstack.org/tc/reference/opens.html#open-source>`_
* `Open design <https://governance.openstack.org/tc/reference/opens.html#open-design>`_
* `Open development <https://governance.openstack.org/tc/reference/opens.html#open-development>`_
* `Open Community <https://governance.openstack.org/tc/reference/opens.html#open-community>`_

Groups
------

There are lots of people working on OpenStack organized into different groups.
These are described in the :ref:`special-interest-groups` section of
the Governance chapter.

What is a contribution?
=======================

In open source projects a contribution can be anything which helps the project
to accomplish its mission. In addition to code contribution it can be testing,
documentation, requirements gathering, bug reporting and so forth.
