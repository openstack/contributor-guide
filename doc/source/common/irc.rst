.. _setup-irc:

#########
Setup IRC
#########

IRC
===

.. warning::

   The OpenStack Community moved the IRC network from Freenode to OFTC
   on May 31, 2021. All the current IRC channels used by the OpenStack
   community are registered in the OFTC network with the same name.

What is IRC?
------------

The OpenStack community uses Internet Relay Chat (IRC) as its primary chat
service.

IRC allows you to:

* Communicate with project teams, technical committee, SIGs,
  and other Working Groups.
* Participate in regular meetings with the above groups.

What IRC network we use
=======================

As of May 31st, 2021 the OpenStack Community has decided to move its IRC
network from Freenode to OFTC.

Set up IRC on Linux & Windows
=============================

Install an IRC Program
----------------------

This section explains how you can install an IRC program called Hexchat.

For a Linux distributions like Debian, Ubuntu, or Mint open a terminal and
type::

  sudo apt install hexchat

For a Linux distributions like Redhat, Fedora 21 or earlier, or CentOS open
a terminal and type::

  sudo yum install hexchat

For Fedora 22 or later open a terminal and type::

  sudo dnf install hexchat

For Windows environment, download latest Hexchat installation binary from
`Hexchat download <https://hexchat.github.io/downloads.html>`__ and
install it.
You will probably also need extra components shown just under Hexchat.

Now open the hexchat program just like you would for any Linux program.


Edit Nick Name Settings
-----------------------

#. Lets first fill out the **Nick name** and **User name** field with our
   choice of a nickname:
#. From the list of **Networks** you should select OFTC network.

* ircs://irc.oftc.net:6697 for SSL (alternative port: 9999), IPv4 and IPv6.
* irc://irc.oftc.net:6667 for non-SSL (alternative ports: 6668-6670, 7000),
  IPv4 and IPv6.


Edit Server Settings
--------------------

#. Click the **edit** button and
#. Make sure that **Use SSL for all the servers on this network** is
   checked.

Troubleshooting
^^^^^^^^^^^^^^^

* If you get a notice that the nick name is already taken, quit and go back to
  the first set of steps to pick a different nickname.


Register Your Nick Name
-----------------------

If you don’t already have an account, you can register one with
``/msg NickServ REGISTER <password> <e-mail>``. `The OFTC Guide
<https://www.oftc.net/Services/#nickserv>`_ will guide you through
the rest of the registration process.  Make sure to follow the instructions
and complete the verification process.

When you login to the server for the first time with your nickname, it
will be used by you, but it's still not registered yet.

In order to register you need to send a message to nickserv on OFTC, which
is a bot that allows you to register and identify yourselves as the owner of
a nick name.

If all goes well you should receive a message back instantly that the nick name
is registered by you and an activation email will be sent to the email address
you provided.

Auto-Login On Connecting To OFTC
--------------------------------

In order to identify yourselves that you own the nick name upon
logging in, you need to tell Hexchat to communicate your password
upon connecting.

#. Click **Hexchat** from the menu and then click **Network List**.
   You will see a familiar first screen of servers listed. Make sure
   OFTC is highlighted and click **edit**.
#. In the **Password** put in the password you picked in the previous
   step and click close.


In case of more question about OFTC, read `these FAQs
<https://www.oftc.net/FAQ/Services/>`_

Done
----

Congratulations you're now ready to communicate with the OpenStack community
and have a registered nick name on OFTC! From here on out when you connect
to OFTC with Hexchat you will be identified with your nickname.

A good channel to join right away is the #openstack-dev channel. A lot of
people hang around in that channel so come on in and say hello! If there is
a specific project you are also interested in working on, feel free to join
that one as well and introduce yourself there. Interested in joining more
channels or need to look up what one is called? Check out
:ref:`irc-channels` for more information.

It's also important to note that given that the majority of contributors
reside in the United States, channels will likely be quieter outside of
United States work hours and it might be a while before they respond.

Set up IRC on Mac OS
====================

TODO

.. _irc-channels:

IRC Channels
============

Each project and working group has its own IRC channel. The common syntax for
naming the IRC channels is: #openstack-<name-of-project>. See the
`list of OpenStack-related IRC channels <http://eavesdrop.openstack.org/#channels>`__.

IRC Meetings
============

In OpenStack all the meetings are happening either on generic meeting channels
channels like #openstack-meeting, or on specific project channels. Check the
`list of meetings <http://eavesdrop.openstack.org/#meetings>`__ for meetings
times, IRC channels, and archives of meetings.

IRC Archives
============

Most IRC channels are archived, you can read the logs on
`eavesdrop <http://eavesdrop.openstack.org/irclogs/>`__.

IRC bots
========

IRC allows different programs to listen to the IRC channels and do some
actions. These programs are called IRC bots. There are several bots used
in the OpenStack IRC channels, this section contains the ones which are
useful from the first days of OpenStack development. A more
comprehensive list can be found in the `Infrastructure team IRC page
<https://docs.openstack.org/infra/system-config/irc.html>`__.

Thanksbot
---------

This bot allows people to recognize each other and be thankful. Anyone
can post a message in the OpenStack IRC channels to say thanks.
The way to say thanks is:

.. code::

  #thanks <irc_nick> <message>

The irc_nick is the IRC nick of the person who is receiving the thanks.
The message is a short text to explain the reason for the thanks. The bot
collects all thanks to a `wiki page
<https://wiki.openstack.org/wiki/Thanks>`__.

Statusbot
---------

Statusbot is used to distribute urgent information from the Infrastructure team
to OpenStack channels.

Successbot
----------

Succesbot is an IRC bot to express small successes in OpenStack
development.
To celebrate in the OpenStack IRC channel way just type:

.. code::

  #success <message>

to any OpenStack IRC channel where the Statusbot is listening.
The message will be posted to the `Successes wiki page
<https://wiki.openstack.org/wiki/Successes>`__.
