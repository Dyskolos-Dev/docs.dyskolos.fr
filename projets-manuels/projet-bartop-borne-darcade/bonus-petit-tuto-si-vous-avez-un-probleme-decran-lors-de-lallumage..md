# (Bonus) Petit tuto si vous avez un problème d'écran lors de l'allumage.

* Ouvrir le ssh&#x20;
* se connecter (en root)&#x20;
* ensuite taper : mount -o remount,rw /boot&#x20;
* ouvrir le fichier recalbox-user-config.txt&#x20;
* modifier les lignes hdmi-group et hdmi-mode en enlevant les #:&#x20;

hdmi\_group=2&#x20;

hdmi\_mode=4

dans le recalbox.conf&#x20;

global.videomode=DMT 35 HDMI.
