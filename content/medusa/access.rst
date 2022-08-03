---
title: Accessing
weight: 230
---

Command Line
************
The easiest and most reliable way of connecting to Medusa is via
`SSH </docs/tools/ssh/>`_.

Connecting is as simple as running the following in your terminal:

.. code::

  ssh username@medusa.ovgu.de

.. class:: note

  **NOTE:** Users with unstable internet connections will likely find
  `tmux </docs/tools/tmux/>`_ to be a helpful tool.

VPN
*********
You need a VPN connection to be able to log in to medusa. A description how
to configure a VPN client can be found on the
`OVGU URZ page <https://www.urz.ovgu.de/urz/en/vpn.html>`_

Graphical
*********
There are multiple methods of connecting to Medusa graphically.

**X Forwarding**
  Graphical programs run on the remote server can be displayed locally using
  `SSH's X Forwarding </docs/tools/ssh/#x%20forwarding>`_. Do note that X Forwarding
  is very sensitive to latency, so it is only practical to use when on the OvGU
  campus.

  .. code::

    ssh -X username@medusa.ovgu.de

**Sixel**
  `Sixel </docs/tools/sixel/>`_ is mostly a toy right now. But it is quite convenient
  in the few situations where there is support (image and NIfTI previews).

**VNC**
  VNC is for users who prefer a more familiar desktop experience or need to use
  graphical programs while off-campus. VNC is a multi-step process and not as
  easy as straight SSH.

  First, SSH into Medusa (explained above). Then setup your VNC password. You
  only need to do this once. The password is stored **unencrypted** in a text
  file, so do not use a valuable password (such as for Medusa, email, etc).

  .. code::

    me@medusa:~$ vncpasswd
    Password:
    Verify:

  Next, start the VNC server.

  .. code::

    me@medusa:~$ vncserver

    New 'medusa:9 (me)' desktop is medusa:9

    Starting applications specified in /home/me/.vnc/xstartup
    Log file is /home/me/.vnc/medusa:9.log

  Note the number ``9`` in ``medusa:9``. Yours will likely be different. Take
  note of your number, as it references *your* VNC session and will be used
  later.

  The VNC server runs until it is terminated by you (or a reboot of Medusa). If
  you close your client/disconnect, it will continue to run. If you "log out" in
  the session, it will terminate the server.

  **Linux**
    Open a terminal and run the following:

    .. code::

      vncviewer -via medusa.ovgu.de :9

    Note the ``:9``. Make sure that this is *your* number from above.  This
    command will first ask that you authenticate to Medusa, and then it will ask
    for the VNC password you set before.

  **macOS**
    macOS has a VNC client built-in, but it isn't SSH aware. So a SSH tunnel
    needs to be setup first.

    .. code::

      ssh -f -L 5909:127.0.0.1:5909 username@medusa.ovgu.de sleep 60

    Then you can use VNC.

    .. code::

      open vnc://127.0.0.1:5909

    Note the number "5909" in both commands. It should be 5900 + the ``number``
    noted above. Make sure that it is *your* number.

    .. class:: todo

      **TODO**: write a simple shell script that can be ``curl``-ed into the user's path.

  **Windows**
    Windows lacks a built-in VNC viewer, so you will need to download and
    install one of your choice, here
    `VNC viewer <https://www.realvnc.com/en/connect/download/viewer/>`_
    is used. To be able to establish a ssh tunnel
    `PuTTY <https://www.putty.org/>`_ is used in addition.

    0. Connect to medusa and start the VNC Server (after setting up your password) to get your session number.
    1. Open putty and specify ``Host Name`` as your medusa login (name@medusa.ovgu.de) and ``Port`` 22
    2. On the right hand side, click on the + next to ``SSH`` and then click ``Tunnels``.
    3. Type 59(session number) for ``Source port`` (e.g. if your session number is 11 type 5911).
    4. Type localhost:5900 + your unique session number (here 11) as ``Destination`` then click ``Add``. (e.g. localhost:5911)
    5. Go back to ``Session``. If you don't want to repeat this steps each time you connect to medusa, save this session.
    6. Load and open the session to connect to medusa.
    7. Open a VNC Viewer, type localhost:59(session number) and connect.
    8. You will be required to enter your VNC password. Afterwards you will have access to the GUI.

    Note the port number: "5911". It should be 5900 + the ``number`` we
    noted above. Make sure that it is *your* number.

    Putty:

    |pic1| |pic2|

    .. |pic1| image:: /docs/medusa/images/finaltwo.png
       :width: 45%

    .. |pic2| image:: /docs/medusa/images/finalone.png
       :width: 45%

    VNC Viewer:

    .. image:: /docs/medusa/images/vnc_connection.png
         :align: center
         :width: 80%

After successfully establishing a VNC connection the desktop will look like this:

.. image:: /docs/medusa/images/youmadeit.png
     :align: center
     :width: 90%

**Helpful Commands**

How to show the List of started VNC Server.

.. code::

    vncserver -list

How to kill the process from to many started vnc server (11 is the sessionnumber).

.. code::

    vncserver -kill :11
