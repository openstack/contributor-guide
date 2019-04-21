##############################
Setting Up Your Gerrit Account
##############################

.. note::

   This section assumes you have completed :doc:`git` guide.

.. _what_is_gerrit:

What is Gerrit?
===============

This is the review system the OpenStack community uses.

Gerrit allows you to review:

* `Code, docs, infrastructure changes, and CI configurations <https://opendev.org/explore/repos>`_
* `Specifications <https://specs.openstack.org>`_
* `Translations <https://opendev.org/openstack/i18n/>`_
* `Use cases for features <https://specs.openstack.org/openstack/openstack-user-stories/>`_

Sign Up
=======

#. Visit `OpenStack's Gerrit page <https://review.opendev.org>`_ and click
   the **sign in** link.
#. You will be prompted to select a username. You can enter the same one you
   did for Launchpad, or something else.

.. note::

   Choose and type your username carefully.
   Once it is set, you cannot change the username.

.. note::

   From here on out when you sign into Gerrit, you'll be prompted to enter
   your Launchpad login info. This is because Gerrit uses it as an OpenID
   single sign on.


Individual Contributor License Agreement
========================================

What is it?
-----------

An agreement to clarify intellectual property rights granted with
contributions from a person or entity. `Preview the full agreement
<https://review.opendev.org/static/cla.html>`_.

Signing it
----------

Individual Contributors
^^^^^^^^^^^^^^^^^^^^^^^

#. In Gerrit's `settings <https://review.opendev.org/#/settings/agreements>`_
   click the **New Contributor Agreement** link and sign the
   agreement. You need this to contribute code & documentation. You
   will not be able to push patches to Gerrit without this.

.. image:: /_assets/account-setup/3.png
   :scale: 70%
   :align: center

Contributors From a Company or Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you are contributing on behalf of a company or organization.

#. In Gerrit's `settings <https://review.opendev.org/#/settings/agreements>`_
   click the **New Contributor Agreement** link and sign the agreement.

   .. image:: /_assets/account-setup/3.png
     :scale: 70%
     :align: center

#. An employer with the appropriate signing rights of the company or
   organization needs to sign the `Corporate Contributor License Agreement
   <https://secure.echosign.com/public/hostedForm?formid=56JUVGT95E78X5>`_.
#. If the CCLA only needs to be extended follow `this
   <https://wiki.openstack.org/wiki/HowToUpdateCorporateCLA>`_ procedure.

.. note::

   Employers can update the list of authorized employees by filling out and
   signing an `Updated Schedule
   A Form
   <https://openstack.echosign.com/public/hostedForm?formid=56JUVP6K4Z6P4C>`_.

Contributors From the U.S. Government
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#. Someone of authority needs to sign the `U.S. Government Contributor License
   Agreement <https://wiki.openstack.org/wiki/GovernmentCLA>`_. Contact the
   `OpenStack Foundation <mailto:communitymngr@openstack.org>`_ to initiate
   this process.

Setup SSH Keys
==============

What are they?
--------------

In order to push things to `Gerrit <https://review.opendev.org>`_ we need to
have a way to identify ourselves. We will do this using SSH keys which allows
us to have our machine we're pushing a change from to perform
a `challenge-response authentication
<https://en.wikipedia.org/wiki/Challenge-response_authentication>`_ with the
Gerrit server.

SSH keys are always generated in pairs:

* **Private key** - Only known to you and it should be safely guarded.
* **Public key** - Can be shared freely with any SSH server you wish to connect
  to.

In summary, you will be generating a SSH key pair, and providing the Gerrit
server with your public key. With your system holding the private key, it
will have no problem replying to Gerrit during the challenge-response
authentication.

Some people choose to use one SSH key pair to access many systems while
others prefer to use separate key pairs. Both options are covered in the
following sections.

Check For Existing Keys
-----------------------

Open your terminal program and type::

  ls -la ~/.ssh

Typically public key filenames will look like:

* id_dsa.pub
* id_ecdsa.pub
* id_ed25519.pub
* id_rsa.pub

If you don't see .pub extension file or want to generate a specific set
for OpenStack Gerrit, you need to generate keys.


Generate SSH Key Pairs
----------------------

Generating The Default Or Initial SSH Key Pair
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can generate a new SSH key pair using the provided email as a label by
going into your terminal program and typing::

  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

When you're prompted to "Enter a file in which to save the key" press Enter.
This accepts the default location::

  Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]

At the prompt, type a secure passphrase, you may enter one or press Enter to
have no passphrase::

  Enter passphrase (empty for no passphrase): [Type a passphrase]
  Enter same passphrase again: [Type passphrase again]

Generating A Separate Key Pair For OpenStack Gerrit (optional)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can generate a new SSH key using the provided email as a label by going
into your terminal program and typing::

  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

When you're prompted to "Enter a file in which to save the key" you must
specify the name of the new key pair and then press Enter::

  Enter a file in which to save the key (/Users/you/.ssh/id_rsa): /Users/you/.ssh/id_openstack_rsa

At the prompt, type a secure passphrase, you may enter one or press Enter to
have no passphrase::

  Enter passphrase (empty for no passphrase): [Type a passphrase]
  Enter same passphrase again: [Type passphrase again]

Finally you need to tell ssh what host(s) to associate SSH keys with. To do
this open "~/.ssh/config" in an editor, create the file if it doesn't exist
and add something like::

  Host review.opendev.org review
    Hostname review.opendev.org
    Port 29418
    User <your_gerrit_username>
    IdentityFile ~/.ssh/id_openstack_rsa

Copy Public Key
---------------

Mac OS & Linux
^^^^^^^^^^^^^^

From your terminal type::

  cat ~/.ssh/id_rsa.pub

Or if you created a separate key pair, assuming the example
name above::

  cat ~/.ssh/id_openstack_rsa.pub

Highlight and copy the output.

Import Public Key Into Gerrit
-----------------------------

#. Go to `Gerrit's SSH Public Keys settings
   <https://review.opendev.org/#/settings/ssh-keys>`_.
#. Click the 'Add Key' button.
#. Paste the public key into the **Add SSH Public Key** text box and click
   **Add**.

Git Review
==========

What is it?
-----------

Git review is a tool maintained by the OpenStack community. It adds an
additional sub-command to 'git' like so::

  git review

When you have changes in an OpenStack project repository, you can use this
sub-command to have the changes posted to
`Gerrit <https://review.opendev.org/>`__ so that they can be reviewed.

Installation
------------

Mac OS
^^^^^^

In a terminal type::

  pip install git-review

If you don't have pip installed already, follow the `installation documentation
<https://pip.pypa.io/en/stable/installing/#installing-with-get-pip-py>`_ for
pip.

.. note::

   Mac OS X El Capitan and Mac OS Sierra users might see an error
   message like "Operation not permitted" when installing with the command.
   In this case, there are two options to successfully install git-review.

   Option 1: install using pip with more options::

     pip install --install-option '--install-data=/usr/local' git-review

   Option 2: Use the package manager `Homebrew <https://brew.sh>`_,
   and type in a terminal::

     brew install git-review

Linux
^^^^^^

For distributions like Debian, Ubuntu, or Mint open a terminal and type::

  sudo apt install git-review

For distributions like RedHat, Fedora 21 or earlier, or CentOS open a terminal
and type::

  sudo yum install git-review

For Fedora 22 or later open a terminal and type::

  sudo dnf install git-review

For SUSE distributions open a terminal and type::

  sudo zypper in python-git-review

Configuration
-------------

Git review assumes the user you're running it as is the same as your Gerrit
username. If it's not, you can tell it by setting this git config setting::

  git config --global gitreview.username <username>

If you don't know what your Gerrit username is, you can check the `Gerrit
settings <https://review.opendev.org/#/settings/>`_.

Preparing to Send a Review
--------------------------

Before doing **git commit** on your patch it is important to initialize
git review. Use the following command to do the initial git review
configuration in your repository::

  git review -s

The command sets up the necessary remote hosts and commit hooks
to enable pushing changes to Gerrit.

.. note::

  Git reviews only needs to be initialized once in a repository.
