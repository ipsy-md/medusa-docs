


Putty on Windows
**********

.. figure:: ./images/images_win_putty_vnc/onmedusa_server.png
    :name: onmedusa_server.png
    :alt:  onmedusa_server.png
    :align: center
    :width: 100%
    
First Login to medusa Server. 


.. figure:: ./images/images_win_putty_vnc/first_vncpasswd.png
    :name: first_vncpasswd.png
    :alt:  first_vncpasswd.png
    :align: center
    :width: 100%
    
Then set the vnc server password with :

.. code::
    vncpasswd
    
    
.. figure:: ./images/images_win_putty_vnc/then_start_vncserver.png
    :name: then_start_vncserver.png
    :alt:  then_start_vncserver.png
    :align: center
    :width: 100%
    
    Then start the vnc Server with
    
.. code::
    vncserver
    
and remember your Session number you need it for the putty configuration 


Download Putty & then install it

https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

.. figure:: ./images/images_win_putty_vnc/hostname_putty.png
    :name: hostname_putty.png
    :alt:  hostname_putty.png
    :align: center
    :width: 100%

1. Specify host name as your medusa login (name@medusa.ovgu.de) and Port 22
    
.. figure:: ./images/images_win_putty_vnc/SSH_knotenpunkt.png
    :name: SSH_knotenpunkt.png
    :alt:  SSH_knotenpunkt.png
    :align: center
    :width: 100%
    
    
find on the left side the SSH option
   
.. figure:: ./images/images_win_putty_vnc/ssh_tunnels.png
    :name: ssh_tunnels.png
    :alt:  ssh_tunnels.png
    :align: center
    :width: 100%
    
after that the ssh tunnels option

.. figure:: ./images/images_win_putty_vnc/sourceport.png
    :name: sourceport.png
    :alt:  sourceport.png
    :align: center
    :width: 100%
    
3. Type 59 + your session number for Source port (e.g. if your session number is 8 type 5908).
 
 
.. figure:: ./images/images_win_putty_vnc/add_localhost.png
    :name: add_localhost.png
    :alt:  add_localhost.png
    :align: center
    :width: 100%
       
4. Type localhost:59(session number) as Destination then click Add. (e.g. localhost:5908)


.. figure:: ./images/images_win_putty_vnc/GiveyourSession_a_nameandSave.png
    :name: GiveyourSession_a_nameandSave.png
    :alt:  GiveyourSession_a_nameandSave.png
    :align: center
    :width: 100%
  
  
5. Go back to session and you can save this session so you don’t have to repeat these steps each time you want to connect.

.. figure:: ./images/images_win_putty_vnc/Load_save_settings_onputty.png
    :name: Load_save_settings_onputty.png
    :alt:  Load_save_settings_onputty.png
    :align: center
    :width: 100%
    
6. Load and open session and connect to medusa and start the VNC Server (after setting up your password)
   
   
   
.. figure:: ./images/images_win_putty_vnc/downloadTightVNC_use_putty_configuration.png
    :name: downloadTightVNC_use_putty_configuration.png
    :alt:  downloadTightVNC_use_putty_configuration.png
    :align: center
    :width: 100%
    
7. Open a VNC Viewer, type localhost:59(session number) and connect.
  
  
.. figure:: ./images/images_win_putty_vnc/vncauthentication.png
    :name: vncauthentication.png
    :alt:  vncauthentication.png
    :align: center
    :width: 100%
    
    
8. You will be required to enter your VNC password, afterwards you will have access to the GUI.  
    
.. figure:: ./images/images_win_putty_vnc/youmadeit.png
    :name: youmadeit.png
    :alt:  youmadeit.png
    :align: center
    :width: 100%
    
    
you made it!
    


In short follow the steps without pictures: 

A) PuTTY configuration: is an SSH telnet client which, with a VNC Viewer, connects to the GUI. The steps after downloading PuTTY is as follows:

      1. Specify host name as your medusa login (name@medusa.ovgu.de) and Port 22
      2. On the right hand side, click on the + next to SSH and then click Tunnels.
      3. Type 59 + your session number for Source port (e.g. if your session number is 8 type 5908).
      4. Type localhost:59(session number) as Destination then click Add. (e.g. localhost:5908)
      5. Go back to session and you can save this session so you don’t have to repeat these steps each time you want to connect.
      6. Load and open session and connect to medusa and start the VNC Server (after setting up your password)
      7. Open a VNC Viewer, type localhost:59(session number) and connect.
      8. You will be required to enter your VNC password, afterwards you will have access to the GUI.



    


Config & Settings 
******

In case of problems from too many started vncServers: 

Looks like this: 

show how many processes are started.

.. code::

ps aux | grep Benutzer | grep vnc


kill the process from to many started vnc server:
.. code::

vncserver -kill :9

.. code::

pkill -u Benutzer



