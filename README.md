# audio_confess

A timer controller to record audio files.


POUR iNSTALLATION

1/ installer une raspian standard

> sudo raspi-config
activer les GPIO's (menu->interface-> activer les GPIO's)

2/ Configurer la clé usb qui contiendra les fichiers sons
créer une clé usb en FAT32 et ka nommer USB1

3/ Installer le script
> sudo git clone https://github.com/julienweiss/audio_confess/
> cd audio_confess

*configurer si besoin le script
> sudo nano confess.py
  
 4/ Tester le script
 
 > sudo python /chemin/du/dossier/confess.py
 
 Appuyer sur le bouton
 vérifier si un fichier est apparu dans la clé usb
 
 5/ configurer l'autolaunch du script python 'confess.py'
 
 > crontab -e
 
 choisir editeur nano
 
 rajouter la ligne suivante à la fin
 
 @reboot sudo python /chemin/du/dossier/confess.py &
 
 puis faire ctrl+o [entrée] ctrl+x [entrée]
  
  6/ redémarrer
  
  Appuyer sur le bouton et vérifier si un fichier son est apparu dans la clé usb
  
  7/ récupération des confessions audio
  
  Il faut systématiquement éteindre ou débrancher le raspi pour enlever la clé usb.
  
  
  
  8/ Utiliser la boite à confession sans écran
  

> sudo raspi-config
boot option
dans b1 desktop/CLI 
cocher b2 console autologin

puis faire 
> sudo mkdir /media/pi/USB1
> sudo chmod 777 /media/pi/USB1

Dans le crontab rajouter les lignes suivantes au dessus de la ligne lançant python

@reboot sudo umount -a

@reboot sudo mount /dev/sda1 /medi/pi/USB1


puis faire ctrl+o [entrée] ctrl+x [entrée]




9/ pour une maintenance 

> sudo raspi-config
boot option
dans b1 desktop/CLI 
puis cocher b4 desktop autologin
  
  
