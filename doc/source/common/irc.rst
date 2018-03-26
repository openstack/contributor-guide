.. _setup-irc:

#########
Setup IRC
#########

IRC
===

What is IRC?
------------

The OpenStack community uses IRC as its primary chat service.

IRC allows you to:

* Communicate with project teams, technical committee, SIGs,
  and other Working Groups.
* Participate in regular meetings with the above groups.

Linux & Windows
===============

Install an IRC Program
----------------------
We will install an IRC program called Hexchat.

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
#. From the list of **Networks** you should see Freenode. Select that and click
   'edit'.

.. image:: /_assets/irc/linux/1.png


Edit Server Settings
--------------------
#. Click the **edit** button and
#. Make sure that **Use SSL for all the servers on this network** is
   checked.

.. image:: /_assets/irc/linux/2.png

Troubleshooting
^^^^^^^^^^^^^^^
* If you get a notice that the nick name is already taken, quit and go back to
  the first set of steps to pick a different nickname.


Register Your Nick Name
-----------------------
If all goes well we should get a dialog window indicating the connection to
freenode has completed, and what to do next.. For now we'll select "Nothing,
I'll join a channel later."

.. image:: /_assets/irc/linux/3.png

When you login to the server for the first time with your nickname, its being
used by you, but it's still not registered yet.

In order to register we need to send a message to nickserv on freenode, which
is a bot that allows us to register and identify ourselves as the owner of
a nick name.

Type the following to register your nick name with nickserv replacing
**mysecretpassword** and **test@domain.com** with your own password and email
address::

  /msg nickserv register mysecretpassword test@domain.com

.. image:: /_assets/irc/linux/4.png

If all goes well you should receive a message back instantly that the nick name
is registered by you and an activation email will be sent to the email address
you provided.



Auto-Login On Connecting To Freenode
------------------------------------
In order to identify ourselves that we own the nick name upon logging in, we
need to tell Hexchat to communicate our password over upon connecting.

#. Click **Hexchat** from the menu and then click **Network List**. We will see
   a familiar first screen of servers listed. Make sure freenode is highlighted
   and click **edit**.
#. In the **Password** put in the password we picked in the previous
   step and click close.

.. image:: /_assets/irc/linux/5.png


Done
----
Congratulations you're now ready to communicate with the OpenStack community
and have a registered nick name on Freenode! From here on out when you connect
to Freenode with Hexchat you will be identified with your nickname.

A good channel to join right away is the #openstack-dev channel. A lot of
people hang around in that channel so come on in and say hello! If there is
a specific project you are also interested in working on, feel free to join
that one as well and introduce yourself there. Interested in joining more
channels or need to look up what one is called? Look :ref:`irc-channels`.

It's also important to note that given that the majority of contributors
reside in the United States, channels will likely be quieter outside of
United States work hours and it might be a while before they respond.

Mac OS
======

Install an IRC Program
----------------------
We'll install an IRC program called Colloquy.

#. Go to http://colloquy.info and follow the download link.
#. From your downloads folder, drag the Colloquy application icon to your
   applications folder to install.


Add A New Connection
--------------------
#. Lets first fill out the **Nickname** and **User name** field with our
   choice of a nickname:
#. For the **Chat server** type in **irc.freenode.net**.
#. For the **Chat Server Port** type in **6697** and check the **SSL
   Connection** box.

.. image:: /_assets/irc/macos/1.png
    :width: 50%

If all goes well in the second window we should see our our new connection and
our client connected.

.. image:: /_assets/irc/macos/2.png
    :width: 50%

Troubleshooting
^^^^^^^^^^^^^^^
* If you get a notice that the nick name is already taken
    * Click **cancel**.
    * Click the **info** icon.
    * Type in a different user/nick name as shown in the previous step.
    * Click **disconnect** and click **connect** to retry connecting with the
      new nick name.

.. image:: /_assets/irc/macos/3.png
    :width: 50%


Register Your Nick Name
-----------------------
If all goes well we should be connected and no pop ups as indicted in the
previous step's Troubleshooting section.

When you login to the server for the first time with your nickname, its being
used by you, but it's still not registered yet.

In order to register we need to send a message to nickserv on Freenode, which
is a bot that allows us to register and identify ourselves as the owner of
a nick name.

Click the **message user** icon and type::

  nickserv

A message dialog window will come up. Type the following to register your nick
name with nickserv replacing **mysecretpassword** and **test@domain.com** with
your own password and email address::

  register mysecretpassword test@domain.com

.. image:: /_assets/irc/macos/4.png
    :width: 90%

If all goes well you should receive a message back instantly that the nick name
is registered by you and an activation email will be sent to the email address
you provided.


Auto-Login On Connecting To Freenode
------------------------------------
In order to identify ourselves that we own the nick name upon logging in, we
need to tell Colloquy to communicate our password over upon connecting.

#. Going back to your connection window, highlight your freenode connection and
   click the **info** icon.
#. In the **Password** field type your password.

.. image:: /_assets/irc/macos/5.png
    :width: 50%


Done
----
Congratulations you're now ready to communicate with the OpenStack community
and have a registered nick name on Freenode! From here on out when you connect
to Freenode with Colloquy you will be identified with your nickname.

A good channel to join right away is the #openstack-dev channel. A lot of
people hang around in that channel so come on in and say hello! If there is
a specific project you are also interested in working on, feel free to join
that one as well and introduce yourself there. Interested in joining more
channels or need to look up what one is called? Look :ref:`irc-channels`.

It's also important to note that given that the majority of contributors
reside in the United States, channels will likely be quieter outside of
United States work hours and it might be a while before they respond.

.. _irc-channels:

IRC Channels
============

Each project and working group has its own IRC channel. The common syntax for
naming the IRC channels is: #openstack-<name-of-project>.
The list of OpenStack related IRC channels is maintained on a
`wiki page <https://wiki.openstack.org/wiki/IRC>`__.

IRC Meetings
============

In OpenStack all the meetings are happening on a variety of IRC
channels (e.g. #openstack-meeting, #openstack-meeting-cp, etc.). Check the
`list of meetings <http://eavesdrop.openstack.org/>`__ for meetings times, IRC
channels, and archives of meetings.

.. note::
   There are a finite number of meeting channels so that meetings are
   spread around. This is enforced by infra. The #openstack-meeting-cp
   channel is special in that it is dedicated to cross project efforts.

IRC Archives
============

Most IRC channels are archived, you can read the logs on the
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
----------

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
