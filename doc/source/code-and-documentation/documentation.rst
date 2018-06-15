#############
Documentation
#############

This section contains information necessary to contributing to OpenStack
documentation.

Documents in project repositories
=================================

All project documentation must follow the same directory structure, which is
described on the `Project Guide Setup page`_.

The documentation directory structure is the following::

  └── source
      ├── admin
      ├── cli
      ├── configuration
      ├── contributor
      ├── install
      ├── reference
      └── user

Installation guide
------------------

The installation guide can be found in the ``install`` directory. It contains
information on anything to do with installing a project from packages, for
instance, software necessary for installing the project, like database
installation and configuration, or what parameters should be set in the
project's config file. If everything is configured properly (described below),
the project's installation guide is included in the `OpenStack Installation
Guides`_. The installation guide is not intended to be used for production
system installations.

Contributor guide
-----------------

The contributor guide can be found in the ``contributor`` directory. It
contains project-specific information on contributing to the project and on
team management. This guide appears only in the project's documentation.

Configuration reference
-----------------------

The ``configuration`` directory contains configuration reference information
that is either automatically generated (if the project uses ``oslo.config``) or
manually written (if ``oslo.config`` is not used). For more information, see
`Sphinx Integration`_.

CLI reference
-------------

The ``cli`` directory contains command line tool reference documentation which
can be automatically generated with cliff’s sphinx integration, or manually
written when auto-generation is not possible. For more information, see
`cliff Sphinx Integration`_.

Administrator guide
-------------------

The admin guide can be found in the ``admin`` directory. It contains
information on the configuration and operation of the software. The project's
administrator guide is included in the `OpenStack Administrator Guides`_.

User guide
----------

The ``user`` directory contains information targeted at end-users, for
instance, concept guides, tutorials, step-by-step instructions for using the
CLI or the project's API, and such.

Reference documents
-------------------

The ``reference`` directory contains reference information not included in the
other directories, for instance, automatically generated class documentation in
library projects.

Publishing documents in project repositories
============================================

For the project documents to be linked to on the `OpenStack documentation
portal`_, the ``www/project-data/latest.yaml`` file in the
``openstack-manuals`` repository has to be updated, following the rules of the
`template generator`_.

#. Find your project in the file.

#. Set to 'true' all document options that apply. For example::

       has_install_guide: true
       has_api_ref: true
       has_admin_guide: true
       has_config_ref: true
       has_user_guide: true

If the above structure exists in the project repository and the ``latest.yaml``
file is updated, the ``publish-openstack-sphinx-docs`` job in the
``project-config`` repo automatically includes the document in the published
documentation. For detailed instructions, see the `Project guide setup`_.

.. _`Project guide setup`: https://docs.openstack.org/doc-contrib-guide/project-guides.html
.. _`Project Guide Setup page`: https://docs.openstack.org/doc-contrib-guide/project-guides.html
.. _`template generator`: https://docs.openstack.org/doc-contrib-guide/doc-tools/template-generator.html
.. _`OpenStack documentation portal`: https://docs.openstack.org
.. _`OpenStack Administrator Guides`: https://docs.openstack.org/admin/
.. _`Sphinx Integration`: https://docs.openstack.org/oslo.config/latest/reference/sphinxext.html
.. _`cliff Sphinx Integration`: https://docs.openstack.org/cliff/latest/user/sphinxext.html
.. _`OpenStack Installation Guides`: https://docs.openstack.org/install/
