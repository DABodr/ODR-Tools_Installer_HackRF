# ODR tools installer with full DAB+ multiplex and HackRF One auto-configuration


* Auto-install script of ODR tools for Buster, Jessie & Stretch distribution.
* Auto-configuration with system adaptation of a full DAB+ multiplex.                   
* No transmitter needed for listen your mux with DABlin, DAB+ decoder software.

 More infos on www.opendigitalradio.org for ODR tools development.               
 Configuration ready to transmit with an HackRF One: https://greatscottgadgets.com/hackrf/


  * Install:

- sudo adduser (username) sudo 
- git clone https://github.com/DABodr/ODRinstaller_hackrf.git
- cd ODRinstaller_hackrf
- chmod +x ./Install_script_ODR+Config.sh
- ./Install_script_ODR+Config.sh 

It will make a "dab" directory in /home/$USER/ , install all dependency for odr-mmbtools and all tools for run simply a DAB+ multiplex:
   *   ODR-DabMux (DAB/DAB+ multiplexer) 
   *   ODR-AudioEnc (DAB/DAB+ audio encoder)
   *   ODR-PadEnc ( MOT slideshows and DLS encoder)
   *   ODR-DabMod ( Modulator ) 
   *   HackRF Drivers
   *   DABlin ( DAB/DAB+ player for local and remote multiplex)
   *   Auxiliary scripts
   *   The FDK-AAC library with DAB+ patch
   *   Supervisor (automatisation of all tools)

A preconfigured directory with 4 services ,named "config", is also cloned in /home/$USER/dab/ .
You can edit this one and add services. ( need sudo supervisorctl reread and sudo supervisorctl update after modification )

At the end of the script you can select if you want configure Supervisor server and symlink (y/n)
It will configure Supervisor server on port 8001 and add "config" directory files inside.

Go at this adress: http://localhost:8001 and see all services running in supervisor. (login: odr ; pass: odr)

Congratulations everythings is ready :) 

Now you can listen your own DAB+ multiplex with DABlin:

 - Go to "config" folder cd /home/$USER/dab/config 
 - chmod +x ./listen_my_mux.sh
 - ./listen_my_mux.sh
 - Enjoy!
