VNC on Linux/MacOS/Windows (with Putty) 
********

Download VNC Viewer to the device you want to control.

Make sure you have downloaded VNC® Connect to the computer you want to control.

Download VNC Viewer and VNC Connect, for Linux/MacOS/Windows,  and more ...

https://www.realvnc.com/de/connect/download/viewer/macos/

guter link fuer die installation linux, vncviewer, tightvnc und putty configuration: 

https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-20-04-de



VNC on MacOS
*********

.. figure:: ./images/images_vnc/bar.png
    :name: bar.png
    :alt:  bar.png
    :align: center
    :width: 20%
    
    Finde in der Menueleiste die Systemeinstellungen 
    
.. figure:: ./images/images_vnc/settings.png
    :name: settings.png
    :alt:  settings.png
    :align: center
    :width: 20%
    
    Finde in den Systemeinstellungen die Freigaben 
    
.. figure:: ./images/images_vnc/settings1.png
    :name: settings1.png
    :alt:  settings1.png
    :align: center
    :width: 20%
    
    Finde in den Freigaben die entfernte Anmeldung 
    
.. figure:: ./images/images_vnc/settings2.png
    :name: settings2.png
    :alt:  settings2.png
    :align: center
    :width: 20%
    
    Gebe dein Passwort von deinem Benutzer ein und schalte den Zugang auf entferne Geraete sowohl bei dir als auch bei anderen System per ssh frei
    
.. figure:: ./images/images_vnc/settings3.png
    :name: settings3.png
    :alt:  settings3.png
    :align: center
    :width: 20%
    
    Jetzt muesste es moeglich sein vnc Viewer & Connect zu nutzen! 




VNC on Linux
****

configurate:

for Linux it is important to know the architektur from your hardware and the paketmanagersystem. 
It depend on which architektur you have you can install the right version. 
Choose between yout linux Distribution the right architektur and the right paketmanagersystem: 
rpm 
deb
arm
amd

VNC on Windows
**********
the installation is very straight forward. 

https://www.realvnc.com/en/connect/download/viewer/windows/




Putty on Windows/Linux/MacOS
**********
All pages and steps found detailed here: 

https://www.ssh.com/academy/ssh/putty/windows

And short here: 



Putty on Windows
**********



.. figure:: ./images/images_win_putty_vnc/onmedusa_server.png
    :name: onmedusa_server.png
    :alt:  onmedusa_server.png
    :align: center
    :width: 20%
    
First Login to medusa Server. 


.. figure:: ./images/images_win_putty_vnc/first_vncpasswd.png
    :name: first_vncpasswd.png
    :alt:  first_vncpasswd.png
    :align: center
    :width: 20%
    
Then set the vnc server password with :

.. code::
    vncpasswd
    
    
.. figure:: ./images/images_win_putty_vnc/then_start_vncserver.png
    :name: then_start_vncserver.png
    :alt:  then_start_vncserver.png
    :align: center
    :width: 20%
    
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
    :width: 20%
    
   1. Specify host name as your medusa login (name@medusa.ovgu.de) and Port 22
    
.. figure:: ./images/images_win_putty_vnc/SSH_knotenpunkt.png
    :name: SSH_knotenpunkt.png
    :alt:  SSH_knotenpunkt.png
    :align: center
    :width: 20%
    
   find on the left side the SSH option
   
.. figure:: ./images/images_win_putty_vnc/ssh_tunnels.png
    :name: ssh_tunnels.png
    :alt:  ssh_tunnels.png
    :align: center
    :width: 20%
    
   after that the ssh tunnels option

.. figure:: ./images/images_win_putty_vnc/sourceport.png
    :name: sourceport.png
    :alt:  sourceport.png
    :align: center
    :width: 20%
    
 3. Type 59 + your session number for Source port (e.g. if your session number is 8 type 5908).
 
 
 
.. figure:: ./images/images_win_putty_vnc/add_localhost.png
    :name: add_localhost.png
    :alt:  add_localhost.png
    :align: center
    :width: 20%
    
    
 4. Type localhost:59(session number) as Destination then click Add. (e.g. localhost:5908)

.. figure:: ./images/images_win_putty_vnc/GiveyourSessio_a_nameandSave.png
    :name: GiveyourSessio_a_nameandSave.png
    :alt:  GiveyourSessio_a_nameandSave.png
    :align: center
    :width: 20%

5. Go back to session and you can save this session so you don’t have to repeat these steps each time you want to connect.

.. figure:: ./images/images_win_putty_vnc/Load_save_settings_onputty.png
    :name: Load_save_settings_onputty.png
    :alt:  Load_save_settings_onputty.png
    :align: center
    :width: 20%
    
   6. Load and open session and connect to medusa and start the VNC Server (after setting up your password)
   
   
.. figure:: ./images/images_win_putty_vnc/downloadTightVNC_use_putty_configuration.png
    :name: downloadTightVNC_use_putty_configuration.png
    :alt:  downloadTightVNC_use_putty_configuration.png
    :align: center
    :width: 20%
    
  7. Open a VNC Viewer, type localhost:59(session number) and connect.
  8. You will be required to enter your VNC password, afterwards you will have access to the GUI.  
    
.. figure:: ./images/images_win_putty_vnc/Screenshot (24).png
    :name: Screenshot (24).png
    :alt:  Screenshot (24).png
    :align: center
    :width: 20%
    
    
    you made it !
Putty on Linux
**********

install putty with these desription: 
https://numato.com/blog/how-to-install-putty-on-linux/



Step to Putty configuration below!


Problems on Linux 
******

Putty installation problems: 

globale Varibale definieren: bei problemen mit putty.

eingeben in Terminal:

env GDK_BACKEND=x11 putty

Tipp: if you Download realVNCviewer, you must recognize and check the architketur from the paketmanager and the paket which you want to install


Putty on MacOS
**********

Install Putty here: 

https://macresearch.org/putty-for-mac/

then -> configurate Putty: 

but before start the vnc Server see by medusa/access!!

A) PuTTY configuration: is an SSH telnet client which, with a VNC Viewer, connects to the GUI. The steps after downloading PuTTY is as follows:

      1. Specify host name as your medusa login (name@medusa.ovgu.de) and Port 22
      2. On the right hand side, click on the + next to SSH and then click Tunnels.
      3. Type 59 + your session number for Source port (e.g. if your session number is 8 type 5908).
      4. Type localhost:59(session number) as Destination then click Add. (e.g. localhost:5908)
      5. Go back to session and you can save this session so you don’t have to repeat these steps each time you want to connect.
      6. Load and open session and connect to medusa and start the VNC Server (after setting up your password)
      7. Open a VNC Viewer, type localhost:59(session number) and connect.
      8. You will be required to enter your VNC password, afterwards you will have access to the GUI.


.. figure:: ./images/images_vnc/bar.png
    :name: bar.png
    :alt:  bar.png
    :align: center
    :width: 20%
    
    Finde in der Menueleiste die Systemeinstellungen 
    
.. figure:: ./images/images_vnc/settings.png
    :name: settings.png
    :alt:  settings.png
    :align: center
    :width: 20%
    
    Finde in den Systemeinstellungen die Freigaben 
    
.. figure:: ./images/images_vnc/settings1.png
    :name: settings1.png
    :alt:  settings1.png
    :align: center
    :width: 20%
    
    Finde in den Freigaben die entfernte Anmeldung 
    
.. figure:: ./images/images_vnc/settings2.png
    :name: settings2.png
    :alt:  settings2.png
    :align: center
    :width: 20%
    
    Gebe dein Passwort von deinem Benutzer ein und schalte den Zugang auf entferne Geraete sowohl bei dir als auch bei anderen System per ssh frei
    
.. figure:: ./images/images_vnc/settings3.png
    :name: settings3.png
    :alt:  settings3.png
    :align: center
    :width: 20%
    
    Jetzt muesste es moeglich sein vnc Viewer & Connect zu nutzen! 
    


Config & Settings 
******

Bei Problemen von zu vielen gestarteten vncServern: 

Sieht folgendermassen aus: 

.. figure:: ./images/images_problems/problems_vncserver.png
    :name: problems_vncserver.png
    :alt:  problems_vncserver.png
    :align: center
    :width: 20%

Killen von Prozessen auf dem Medusa Server, notwendig bei mehrfacher Anwendung von dem starten von vnc Servern: 

.. code::

ps aux | grep Benutzer | grep vnc

.. code::

vncserver -kill :9

.. code::

pkill -u Benutzer




----

Important to know: 
links for more understanding: 
