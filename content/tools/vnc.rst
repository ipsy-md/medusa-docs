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



VNC on Windows
**********






Putty on Windows/Linux/MacOS
**********
All pages and steps found detailed here: 

https://www.ssh.com/academy/ssh/putty/windows

And short here: 



Putty on Windows
**********

Download Putty. 
https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

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
