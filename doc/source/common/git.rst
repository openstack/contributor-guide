###################
Setup and Learn GIT
###################

.. note::

   This section assumes you have completed :doc:`accounts` guide.

Git
===

What is it?
-----------

Git is a free and open source distributed version control system that the
OpenStack community uses to manage changes to source code.

Installation
------------

Mac OS
^^^^^^

#. Go to the Git `download page <https://git-scm.com/downloads>`_ and click
   **Mac OS X**.

#. The downloaded file should be a dmg in your downloads folder. Open that dmg
   file and follow the instructions on screen.

If you use the package manager `Homebrew <http://brew.sh>`_, open a terminal
and type::

    brew install git

Linux
^^^^^

For distributions like Debian, Ubuntu, or Mint open a terminal and type::

  sudo apt install git

For distributions like RedHat, Fedora 21 or earlier, or CentOS open a terminal
and type::

  sudo yum install git

For Fedora 22 or later open a terminal and type::

  sudo dnf install git

For SUSE distributions open a terminal and type::

  sudo zypper in git

Windows
^^^^^^^

`Windows Subsystem for Linux (WSL) <https://msdn.microsoft.com/en-us/commandline/wsl/about>`_
is available in Windows 10 Anniversary Update or later (build 1607+).
There is the possibility to install and run modern Linux Operating Systems:

* `Ubuntu 16.04 <https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6>`_
* `openSUSE Leap 42 <https://www.microsoft.com/en-us/store/p/opensuse-leap-42/9njvjts82tjx>`_
* `SLES 12 <https://www.microsoft.com/en-us/store/p/suse-linux-enterprise-server-12/9p32mwbh6cns>`_

All common tools like bash, git, and SSH will work out of the box.

Although Git `download page <https://git-scm.com/downloads>`_ provides Windows
installation binary, most OpenStack development tools (e.g., git-review)
unfortunately will not work well on Windows environment.

Configure Git
-------------

Once you have Git installed you need to configure it. Open your terminal
application and issue the following commands putting in your first/last name
and email address. This is how your contributions will be identified::

  git config --global user.name "Firstname Lastname"
  git config --global user.email "your_email@youremail.com"

.. note::

   Use the same email address that was used during the account setup.

Learning Git
============

You can use `Git Immersion <http://gitimmersion.com/lab_02.html>`_ to work
through tutorials for learning git.

For reference, use the `Git Reference and Cheat Sheet <https://git-scm.com/doc>`_.
