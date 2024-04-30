**Avec l'aimable contribution de SwartZCoding, GaetanOff, RayxiO, adrgaspard, CerealesMC, Alexmdz77 et Comore**

# Liste des conseils

## Infrastructure

- Avoir un proxy (e.g. [BungeeCord](https://github.com/SpigotMC/BungeeCord) ou [Velocity](https://github.com/PaperMC/Velocity)) dédié uniquement aux administrateurs, en plus du principal dédié uniquement aux joueurs (donc bloquer également les administrateurs sur le proxy joueur !!) ;

- Faire des backups incrémentales sur un serveur annexe et également sur un object storage (e.g. S3 (voire même S3 Glacier), [GCS](https://cloud.google.com/storage), [Scaleway Object Storage](https://www.scaleway.com/en/object-storage/)), [Borgbackup](https://www.borgbackup.org/) fait très bien le boulot (settings que j'utilisais : 1 backup/heure, 2 backups/jour, 1 backup/semaine et 1 backup/mois) ;

- Pour éviter les attaques de bots, n'hésitez pas à ne whitelister que les adresses de pays francophones sur [IPTables](https://linux.die.net/man/8/iptables) ;

- Si vous avez les compétences pour, s'orienter vers les services d'AWS (e.g. [CloudFront](https://aws.amazon.com/cloudfront/)) plutôt que d'utiliser l'[offre gratuite de Cloudflare](https://www.cloudflare.com/plans/free/), qui est pas fofolle ;

- Bloquer le scan de port avec [IPTables](https://linux.die.net/man/8/iptables) ;

- Ouvrir les ports de vos serveurs MC UNIQUEMENT au proxy ;

- Utiliser le firewall d'OVH si possible (e.g. firewall d'OVH + [IPTables](https://linux.die.net/man/8/iptables) seulement pour gérer tout ce qui est bots, ...) ;

- Utiliser [IPSet](https://ipset.netfilter.org/) pour bannir de longues listes d'adresses IP ;

- Installer et configurer [PortSentry](https://manpages.ubuntu.com/manpages/bionic/man5/portsentry.conf.5.html) en mode avancé de façon à ce qu'il blacklist les adresses IPs détectées ;

- Bloquer les paquets de [netcat](https://linux.die.net/man/1/nc) et [curl](https://linux.die.net/man/1/curl) ;

- Éviter d'utiliser des solutions à la [phpMyAdmin](https://www.phpmyadmin.net/), ou limiter leur accès via un VPN ou une authentification sur la page ;

- Ouvrir en général l'accès aux dashboards admins (e.g. panel administrateur de votre site, [Pterodactyl](https://pterodactyl.io/), ...) en tout genre seulement via un VPN.

- Externaliser vos services au maximum sur des machines annexes, ne pas tout mettre sur la même machine (e.g. bases de données) ;

- Limiter le plus possible les accès à vos machines.

## En jeu

- Avoir un plugin de double authentification sur votre serveur de jeu !!.

- Bloquer la permission `*` sur le serveur (e.g. [LuckPerms le permet](https://luckperms.net/wiki/Configuration#enable-ops)) ;

- Avoir un plugin qui bannit automatiquement tout compte non-autorisé d'être en gamemode créatif, d'être OP, ... ;

- Autoriser l'exécution des commandes de votre plugin de permission UNIQUEMENT par votre console ;

- Désactiver l'OP dans votre `server.properties` ;

- Bien limiter les permissions en jeu que vous donnez à votre équipe (voire même à votre compte), ne pas donner la permission `*` à tout va si vous ne la bloquez pas ;

- Bien mettre un système d'authentification, même sur vos serveurs de développement ; 

- Avant votre ouverture, vérifier chaque PNJ intéractif sur votre serveur, chaque zone [WorldGuard](https://worldguard.enginehub.org/en/latest/) et vérifier également les permissions qu'ont tous les joueurs de votre serveur ;

- Bien mettre à jour vos plugins régulièrement ;

- Se renseigner sur les malwares qui traînent (e.g. [vmd-gnu](https://www.reddit.com/r/admincraft/comments/xrfim0/papermc_malware_announcement/)) et vérifier que vous n'êtes pas concernés ;

- Ne pas activer l'extension JS de [PlaceholderAPI](https://github.com/PlaceholderAPI/PlaceholderAPI) ;

- Bloquer les commandes suivantes : 
  - `/fill` ;
  - `//sphere` ; 
  - `/bc` ; 
  - `/execute` ;

- Être un administrateur de serveur responsable et ne pas utiliser de plugins nulled (probabilité très forte d'avoir une connerie dedans) ;

- Tester vos plugins "custom" DE FOND EN COMBLE pour éviter les surprises lors de votre ouverture.
