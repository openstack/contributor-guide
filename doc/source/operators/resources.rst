##########
Resources
##########

There are many resources available to operators. Some are maintained by the
operator community while others are maintained by the upstream developers.
Below are brief descriptions of guides to hopefully help you get to the
information you need quicker!

.. note::
   If you find any issues with the guides, please file a bug! Better yet, fix the bug!
   On each page of the documentation there is a link in the top right corner to
   the place bugs are filed (could be Launchpad or StoryBoard depending on the
   repository).

The order the guides are presented in is the typical order they are needed in,
but of course you should feel free to explore them in any order you like.

Architecture Guides
=====================
`The Architecture Guide <https://docs.openstack.org/arch-design/>`_ provides
basic information about designing an OpenStack cloud. This guide discusses the
basics, common use cases, and architecture design requirements.

Virtual Machine Image Guides
=================================
`The VM Image Guide <https://docs.openstack.org/image-guide/>`_ explains how
to 'obtain, create and modify VM images that are compatible with OpenStack.'

Operations Guide
================
`The Operations Guide <https://docs.openstack.org/operations-guide>`_  is
generally focused on what happens after day 1 of spinning up an
OpenStack Cloud. It offers some basic setup information, but the
majority of the content is about maintenance, troubleshooting, user
facing capabilities, and scaling.

Security Guide
===============
`The Security Guide <https://docs.openstack.org/security-guide/>`_ provides information about ways
to keep your cloud secure. It covers everything from identity and secrets
management to per service security options (compute, networking, storage,
messaging, etc.)

Share and Learn From Real Configurations
========================================
Example configurations for various OpenStack services are provided in the
`openstack/osops-example-configs repository
<https://git.openstack.org/cgit/openstack/osops-example-configs/tree/README.md>`_.
Operators can share their configuration files to help others, and review
how others setup and tune their configurations.
