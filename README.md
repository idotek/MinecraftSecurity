## Vous trouverez ci-dessous une petite liste de choses à faire pour limiter au max les relou qui grief vos serveurs. La liste est tout sauf parfaite et je ne dis pas qu'elle n'est pas bypassable. C'était juste un petit cadeau de départ lol. Faites des pull requests si vous voulez modifier ou ajouter un truc

- Accès au Dashboard admin du site obligatoirement par un VPN.

- Accès au compte admins ingame par un proxy particulié (on aura deux proxy redondé pour les joueurs et un proxy réservé aux admin/fonda/compte OP). Les users qui ont des perms importantes seront bloqués sur le proxy joueurs.

- un /pin sur le faction avec un mot de passe qui change tous les jours qui seraient envoyé aux admins dans un groupe télégram) que seulement les gens OP/ayant des perms admins connaitront, ou une 2FA avec une libs Google Auth MISE A JOUR.

- Un plugin d'antiOP / perm étoile: toutes personne qui devient OP, qui change son gamemode, qui se give quelques choses sur le serveur ou qui s'attribue des permissions admin (*) (se sont des examples hein, mettez toutes les commandes sensibles ) qui n'est pas dans les fichiers de config du plugin sont INSTANT ban.

- Un plugin d'antiGM. Tout est dis dans le titre.

- Les commandes de luckperm sont éxecutables uniquement en console.

- Desactivation du OP dans le server.properties

- Faites des backups incrementales sur un disque dur different de celui de votre dédié et en même temps sur un object storage de scaleaway ( outil conseiller: Borgbackup y'a tout un systeme de rotation de log et ne prend pas beaucoup de places sur le disque. Logique c'est incrémentale) Perso j'avais une backup par heure, 2 backups par jour, une backup par semaine et une backup par mois.

- Niveau antibot vous pouvez faire du racisme sur iptable, venez mp si vous voulez le script mais c'est out to update avec les methodes qui ne vont pas tarder à sortir. GL à vous ( tcpshield est bypassable ).

- Niveau DDoS de site CF free c'est une passoire, même si vous faites du racisme. Essayer de vous orienter sur du AWS mais faut avoir les compétences pour le maintenir sans payer trop chère

- Nos chères hackers de l'internet aime bien le scan de port aussi avec nmap, bloquer-le avec iptables c'est pas compliqué.

- Niveau firewall temps qu'on y est. Il faut ABSOLUMENT restreindre les ports de vos serveurs de jeux UNIQUEMENT à l'ip du bungeecord. Sinon nos chers h4xor minecraft pourront se connecter directement sur le serveur sans passer par votre PROXY.

- Ah oui aussi, le firewall d'ovh que tout le monde oublie de config est pas mal aussi. Vous pouvez utiliser le firewall d'ovh et utilise iptable uniquement pour gerer le L7 ( antibot par exemple )

- ipset c'est bien aussi si vous voulez ban des longues liste d'ip.
