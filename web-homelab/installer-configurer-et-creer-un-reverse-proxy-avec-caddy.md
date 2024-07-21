# Installer, configurer et créer un reverse proxy avec Caddy

###

Caddy est un serveur web et un reverse proxy moderne, facile à configurer, avec HTTPS automatique par défaut. Dans ce tutoriel, nous allons voir comment installer Caddy, le configurer en tant que reverse proxy et l'utiliser avec un sous-domaine géré par Cloudflare.

#### Prérequis

1. Un serveur (VPS, serveur dédié, etc.) avec un système d'exploitation basé sur Linux (Ubuntu, Debian, etc.).  Assurez vous que le port 80/443 soient bien accessible et libre depuis internet.
2. Accès SSH au serveur.
3. Un nom de domaine géré via Cloudflare. (On prendra comme exemple CF dans ce tutoreil car c'est le plus uttilisé).

#### Étape 1 : Installation de Caddy

1.  **Connexion au serveur**

    Connectez-vous à votre serveur via SSH :

    ```sh
    ssh uttilisateur@votre_ip
    ```



2. **Téléchargement et installation de Caddy**

Ajoutez le dépôt officiel de Caddy et installez-le :

```sh
sudo apt update
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo apt-key add -
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy
```



3. **Vérification de l'installation**

Vérifiez que Caddy est correctement installé en vérifiant sa version :

```sh
caddy version
```

#### Étape 2 : Configuration de Caddy en tant que reverse proxy

1. **Création du fichier de configuration:**

Créez le fichier de configuration de Caddy (`Caddyfile`) situé dans `/etc/caddy/Caddyfile` :

```sh
sudo nano /etc/caddy/Caddyfile
```



Voici un exemple de configuration pour un reverse proxy :

```plaintext
votre_sous_domaine.domaine.com {
    reverse_proxy votre_backend_server_ip:votre_backend_server_port
}
```



Remplacez `votre_sous_domaine.domaine.com` par votre sous-domaine et votre`_backend_server_ip:votre_backend_server_port` par l'IP et le port de votre serveur backend.

2. **Redémarrage de Caddy**

Après avoir modifié le fichier de configuration, redémarrez Caddy pour appliquer les changements :

```sh
sudo systemctl reload caddy
```

#### Étape 3 : Configuration de Cloudflare

1.  **Connexion à Cloudflare**

    Connectez-vous à votre compte Cloudflare et sélectionnez votre domaine.



2. **Ajout du sous-domaine**

Ajoutez un enregistrement DNS pour votre sous-domaine :

* Allez dans la section DNS de votre tableau de bord Cloudflare.
* Ajoutez un nouvel enregistrement de type `A`. (Ou de type `AAA` si vous uttilisez une IPV6)
  * Nom : `votre_sous_domaine`
  * Contenu : L'adresse IP de votre serveur Caddy
  * TTL : Automatique
  * Proxy status : Proxied (activé)

3. **Configuration du SSL/TLS**

* Allez dans la section SSL/TLS de votre tableau de bord Cloudflare.
* Assurez-vous que le mode SSL/TLS est réglé sur "Full" ou "Full (strict)" pour une connexion sécurisée entre Cloudflare et votre serveur Caddy.

#### Étape 4 : Vérification du fonctionnement

1.  **Accéder à votre sous-domaine**

    Ouvrez un navigateur et allez à l'adresse `https://votre_sous_domaine.domaine.com`. Vous devriez voir la page servie par votre backend via Caddy.
2.  **Vérification des certificats SSL**

    Assurez-vous que le site utilise correctement le certificat SSL fourni par Cloudflare.

#### Conclusion

Vous avez maintenant installé et configuré Caddy en tant que reverse proxy, et configuré un sous-domaine avec Cloudflare. Caddy gère automatiquement les certificats SSL, ce qui simplifie grandement la gestion de la sécurité de votre site. Pour des configurations plus avancées, vous pouvez consulter la documentation officielle de Caddy.

N'hésitez pas à me poser des questions si vous rencontrez des problèmes ou avez besoin de précisions supplémentaires.\






\
_Crédits:_\
_Imagination: Dyskolos\__\
_Rédaction: Dyskolos\__
