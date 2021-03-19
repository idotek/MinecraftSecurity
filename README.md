**Anti kikou griefeur Minkraftt**

## J'en ai rien à faire si vous arrivez à bypass tout ça cest juste des conseils, venez pas faire les fouts dans mes mp

 - Accès au Dashboard admin du site obligatoirement par un VPN.
- Accès au compte admins ingame par un proxy particulié (on aura deux proxy redondé pour les joueurs et un proxy réserver aux admin/fonda/compte OP). Les users qui ont des perms importantes seront bloqués sur le proxy joueurs.
- un /pin sur le faction avec un mot de passe qui change tout les jours qui serait envoyé aux admins dans un groupe télégram) que seulement les gens OP/ayant des perms admins connaitront 
- Un plugin d'antiOP: toutes personnes qui devient OP, qui change son gamemode, qui se give quelques choses sur le serveur ou qui s'attribue des permissions admin (*) ( se sont des examples hein, mettez toutes les commandes sensible ) qui n'est pas dans les fichiers de config du plugin sont INSTANT ban
- Les commandes de luckperm sont executable uniquement en console
- Desactivation du OP dans le server.proprieties
- Faites des backups incrementale sur un disque dur different de celui de votre dédié et en meme temps sur un object storage de scaleaway ( outil conseiller: Borgbackup y'a tout un systeme de rotation de log et ne prend pas beaucoup de place sur le disque. Logique cest incrémentale) Perso j'avais une backup par heure, 2 backups par jours, une backup par semaine et une backup par mois
- Niveau antibot vous pouvez faire du racisme sur iptable, venez mp si vous voulez le script mais c'est out to update avec les methodes qui vont pas tarder à sortir. GL à vous ( tcpshield est bypassable )
- Niveau DDoS de site CF free c'est une passoire, meme si vous faites du racisme. Essayer de vous orientez sur du AWS mais faut avoir les compétences 
- Nos chères hackers de l'internet aime bien le scan de port aussi avec nmap, bloquer le avec iptables cest pas compliqué.
- Niveau firewall temps qu'on y est. Il faut ABSOLUMENT restreindre les ports de vos serveurs de jeux UNIQUEMENT à l'ip du bungeecord. Sinon ils pourront se co directement sur le serveur sans passer par votre bungeecord.
- Ah oui aussi, le firewall d'ovh que tout le monde oublie de config est pas mal aussi. Vous pouvez utiliser le firewall d'ovh et utilise iptable uniquement pour gerer le L7 ( antibot par exemple )
- ipset c'est bien aussi si vous voulez ban des longue liste d'ip
