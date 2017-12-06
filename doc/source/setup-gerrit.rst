##############################
Setting Up Your Gerrit Account
##############################

.. note::

  This section assumes you have completed :doc:`git` guide.

What is Gerrit?
===============

This is the review system the OpenStack community uses. Here are just some of
the things we use Gerrit for reviewing:

* `Code <http://git.openstack.org/cgit>`_
* `Specifications <http://specs.openstack.org>`_
* `Translations <http://git.openstack.org/cgit/openstack/i18n/tree/>`_
* `Use cases for features
  <http://specs.openstack.org/openstack/openstack-user-stories/>`_

Sign Up
=======
#. Visit `OpenStack's Gerrit page <https://review.openstack.org>`_ and click
   the **sign in** link.
#. You will be prompted to select a username. You can enter the same one you
   did for Launchpad, or something else.

.. note::

   Choose and type your username carefully.
   Once it is set, you cannot change the username.

.. note::

  From here on out when you sign into Gerrit, you'll be prompted to enter your
  your Launchpad login info. This is because Gerrit uses it as an OpenID single
  sign on.


Individual Contributor License Agreement
----------------------------------------

What is it?
^^^^^^^^^^^
An agreement to clarify intellectual property rights granted with
contributions from a person or entity. `Preview the full agreement
<https://review.openstack.org/static/cla.html>`_.

Signing it
----------

Individual Contributors
^^^^^^^^^^^^^^^^^^^^^^^

#. In Gerrit's `settings <https://review.openstack.org/#/settings/agreements>`_
   click the **New Contributor Agreement** link and sign the agreement. You need
   this to contribute code & documentation. You will not be able to push patches
   to Gerrit without this.

.. image:: _assets/account-setup/3.png
   :scale: 70%
   :align: center

Contributors From a Company or Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
If you are contributing on behalf of a company or organization.

#. In Gerrit's `settings <https://review.openstack.org/#/settings/agreements>`_
   click the **New Contributor Agreement** link and sign the agreement.

.. image:: _assets/account-setup/3.png
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

In order to push things to `Gerrit <https://review.openstack.org>`_ we need to
have a way to identify ourselves. We will do this using SSH keys which allows
us to have our machine we're pushing a change from to perform
a `challenge-response authentication
<https://en.wikipedia.org/wiki/Challenge-response_authentication>`_ with the
Gerrit server.

SSH keys are always generated in pairs:

* **Private key** - Only known to you and it should be safely guarded.
* **Public key** - Can be shared freely with any SSH server you wish to connect
  to.

In summary, we will be generating these keys, and providing the Gerrit server
with your public key. With your system holding the private key, it will have no
problem replying to Gerrit during the challenge-response authentication.


Check For Existing Keys
-----------------------

Open your terminal program and type::

  ls -la ~/.ssh

Typically public key filenames will look like:

* id_dsa.pub
* id_ecdsa.pub
* id_ed25519.pub
* id_rsa.pub

If you don't see .pub extension file, you need to generate keys.


Generate SSH Keys
-----------------

Assuming you weren't able to find keys in your ~/.ssh directory, you can
generate a new SSH key using the provided email as a label by going into
your terminal program and typing::

  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

When you're prompted to "Enter a file in which to save the key" press Enter.
This accepts the default location::

  Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]

At the prompt, type a secure a passphrase, you may enter one or press Enter to
have no passphrase::

  Enter passphrase (empty for no passphrase): [Type a passphrase]
  Enter same passphrase again: [Type passphrase again]


Copy Public Key
---------------

Mac OS & Linux
^^^^^^^^^^^^^^

From your terminal type::

  cat ~/.ssh/id_rsa.pub

Highlight and copy the output.

Import Public Key Into Gerrit
-----------------------------

#. Go to `Gerrit's SSH Public Keys settings
   <https://review.openstack.org/#/settings/ssh-keys>`_.
#. Click the 'Add Key' button.
#. Paste the public key into the **Add SSH Public Key** text box and click
   **Add**.

Git Review
==========

What is it?
-----------

Git review is tool maintained by the OpenStack community. It adds an additional
sub-command to 'git' like so::

  git review

When you have changes in an OpenStack project repository, you can use this
sub-command to have the changes posted to
`Gerrit <https://review.openstack.org/>`__ so that they can be reviewed.

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

  Option 2: Use the package manager `Homebrew <http://brew.sh>`_,
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
settings <https://review.openstack.org/#/settings/>`_.

