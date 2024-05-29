---
cover: ../../.gitbook/assets/IMG_20211029_154122 (1).jpg
coverY: 0
---

# Installer Recalbox

## Tutoriel : Installer Recalbox sur un Raspberry Pi

Recalbox est un système d'exploitation spécialement conçu pour transformer votre Raspberry Pi en une machine de rétro-gaming. Avec une interface intuitive et une compatibilité avec une large gamme de consoles et de jeux, Recalbox est l'une des meilleures options pour les amateurs de rétro-gaming. Voici comment installer Recalbox sur votre Raspberry Pi.

### Étape 1 : Télécharger Recalbox

1. Rendez-vous sur le site officiel de Recalbox : [Télécharger Recalbox](https://www.recalbox.com/fr/download/stable/).
2. Sélectionnez la version de Recalbox compatible avec votre modèle de Raspberry Pi.
3. Téléchargez l'image disque de Recalbox (.img.xz).

### Étape 2 : Préparer la carte microSD

1. Téléchargez et installez un logiciel pour écrire des images disque sur des cartes SD. Nous recommandons [balenaEtcher](https://www.balena.io/etcher/).
2. Insérez la carte microSD dans le lecteur de carte de votre ordinateur.
3. Lancez balenaEtcher et sélectionnez l'image de Recalbox que vous avez téléchargée.
4. Choisissez la carte microSD comme périphérique de destination.
5. Cliquez sur "Flash!" pour commencer le processus d'écriture de l'image sur la carte microSD.
6. Une fois l'écriture terminée, retirez la carte microSD de votre ordinateur.

### Étape 3 : Installer Recalbox sur le Raspberry Pi

1. Insérez la carte microSD préparée dans le Raspberry Pi.
2. Connectez le Raspberry Pi à un écran via le câble HDMI.
3. Branchez le câble d'alimentation pour démarrer le Raspberry Pi.
4. Recalbox se lancera automatiquement. Suivez les instructions à l'écran pour la configuration initiale, y compris le choix de la langue et la configuration de la manette de jeu.

### Étape 4 : Ajouter des ROMs

Pour ajouter des jeux (ROMs) à votre Recalbox :

1. Connectez votre Raspberry Pi à votre réseau local (Wi-Fi ou Ethernet).
2. Sur votre ordinateur, ouvrez un explorateur de fichiers et accédez à votre réseau local. Vous devriez voir un appareil nommé "RECALBOX".
3. Ouvrez le dossier "RECALBOX" et naviguez jusqu'au dossier "roms".
4. Copiez vos ROMs dans les dossiers correspondants aux consoles (par exemple, placez les ROMs de Super Nintendo dans le dossier "snes").
5. Redémarrez Recalbox pour que les nouveaux jeux soient reconnus.

***

Pour plus de détails et des tutoriels supplémentaires, consultez la documentation officielle de Recalbox : [Documentation Recalbox](https://recalbox.gitbook.io/documentation/).

Avec ces étapes simples, vous pouvez transformer votre Raspberry Pi en une console de jeu rétro puissante et profiter des classiques du jeu vidéo sur votre téléviseur. Bon jeu !
