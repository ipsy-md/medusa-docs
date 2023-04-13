---
title: Data
weight: 240
---

Folder Hierarchy
****************
All data in the ``/home`` directory is available across the entire cluster.

``/home/<user_name>``
  This directory is for all of your personal files.

``/home/data/<project_name>``
  This directory is for data shared across the group/project.

``/home/<user_name>/scratch`` or ``/home/data/<project_name>/scratch``
  This directory is not backed-up and should be used to store interim results which can be easily regenerated.
  Storing data here helps relieve the burden on backups.

``/home/data/archive/<project_name>``
  Read-only and heavily compressed (via cool transparent compression mojo), this directory stores data for projects which are completed.

DataLad
*******
When starting new projects, it is highly recommended to use DataLad to ease remote data acquisition and provenance tracking.

Backups
*******
All data located under the ``/home`` directory are snapshot at 05:00 every day — *except* for any data located in the ``/home/<user_name>/scratch`` or ``/home/data/<project_name>/scratch`` folders.
Snapshots are then transferred to a dedicated backup server.

The backup retention policy is:

- daily backups

  * executed daily at 05:00
  * kept for 2 weeks

- weekly backups

  * executed on Mondays at 05:10
  * kept for 6 weeks

- monthly backups

  * executed on the 1st of every month at 05:20
  * kept for 1 year


If you need to have data recovered from a backup, contact the system administration to help recover your data.

To/From Medusa
**************
``rsync``
  This is *the* tool for efficient and reliable transfer.

  .. code::

    rsync -rltoDvh --progress dir_here/ user@medusa.ovgu.de:~/dir_there

WinSCP or Cyberduck
  If you prefer using a GUI, `WinSCP`_ (Windows) and `Cyberduck`_ (macOS and Windows) are decent SFTP clients.

  To connect to Medusa: install and launch your client. Enter the information for host (``sftp://medusa.ovgu.de``), user, and password.
  Click connect.
  Once connected, you can drag-and-drop files to transfer.

.. _WinSCP: https://winscp.net/eng/download.php
.. _Cyberduck: https://cyberduck.io

.. class:: todo

   **TODO:** explain SFTP/SSHFS on a per OS basis. Nautilus integration, sshfs
   on Linux and macOS, and SSHFS-Win on Windows.
