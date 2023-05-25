## Vous trouverez ci-dessous une petite liste de choses à faire pour limiter au max les relou qui grief vos serveurs. La liste est tout sauf parfaite et je ne dis pas qu'elle n'est pas bypassable. C'était juste un petit cadeau de départ lol. Faites des pull requests si vous voulez modifier ou ajouter un truc.

- Accès au Dashboard admin du site obligatoirement par un VPN.

- Accès aux comptes admins ingame par un proxy particulier (on aura deux proxy redondés pour les joueurs et un proxy réservé aux admin/fonda/compte OP). Les users qui ont des perms importantes seront bloqués sur le proxy joueurs. Le proxy pour les admins doit également implémenter l'authentification à 2 facteurs (afin d'éviter en désastre en cas de hack d'un compte admin).

- un /pin sur le faction avec un mot de passe qui change tous les jours (qui seraient envoyés aux admins dans un groupe télégram) que seulement les gens OP/ayant des perms admins connaitront, ou une 2FA avec une lib Google Auth MISE A JOUR.

- Un plugin d'antiOP / perm étoile: toute personne qui devient OP, qui change son gamemode, qui se give quelque chose sur le serveur ou qui s'attribue des permissions admin (*) (se sont des exemples hein, mettez toutes les commandes sensibles ) qui n'est pas dans les fichiers de config du plugin sont INSTANT ban.

- Un plugin d'antiGM. Tout est dit dans le titre.

- Les commandes de luckperm sont exécutables uniquement en console.

- Désactivation du OP dans le server.properties

- Faites des backups incrémentales sur un disque dur différent de celui de votre dédié et en même temps sur un object storage de scaleaway ( outil conseiller: Borgbackup y'a tout un système de rotation de log et ne prend pas beaucoup de places sur le disque. Logique c'est incrémental) Perso j'avais une backup par heure, 2 backups par jour, une backup par semaine et une backup par mois.

- Niveau antibot vous pouvez faire du racisme sur iptable,  GL à vous ( tcpshield est bypassable ).

- Niveau DDoS de site CF free c'est une passoire, même si vous faites du racisme. Essayez de vous orienter sur du AWS mais faut avoir les compétences pour le maintenir sans payer trop cher.

- Nos chers hackers de l'internet aiment bien le scan de port aussi avec nmap, bloquez-le avec iptables c'est pas compliqué.

- Niveau firewall tant qu'ont y est, il faut ABSOLUMENT restreindre les ports de vos serveurs de jeux UNIQUEMENT à l'ip du bungeecord. Sinon nos chers h4xor minecraft pourront se connecter directement sur le serveur sans passer par votre PROXY.

- Ne pas oublier de config le firewall d'ovh. Vous pouvez utiliser le firewall d'ovh et iptable uniquement pour gérer le L7 ( antibot par exemple )

- ipset c'est bien aussi si vous voulez ban des longues listes d'IPs.

- Installer Port-Sentry en mode Advanced et le configurer de sorte de blacklist les ip détectées 

- Bloquer les packets de netcat / curl

- N'utilisez pas PhpMyadmin, sinon bloquez-le par un accès VPN ou avec un mot de passe sur la page.

- Si vous utilisez Pterodactyl, autorisez le uniquement sous VPN

- Ne donnez pas les permissions * à tous pour rien, si une personne a les perms * /op (car c'est plus simple à gérer souvent) il aura plein de commandes qui ne lui serviront à rien, mais qui pourraient être dévastatrices si cette personne se fait hack son compte. 

- Sur vos serveurs de dev, mettez dès le début votre système d'authentification (c'est souvent sur les serveurs de devs, que les h4xors viennent mettre des pnj give, gm, op etc...) 

- Avant l'open, vérifiez chaque PNJs et chaque zones Worldguard, vérifier qu'il n'y en a pas une étrange,  vérifiez aussi les permissions qu'ont les players. 

- Faites attention à avoir toujours vos plugins à jour

- Passez vos plugins dans un remover-backdoor. Exemple : (https://github.com/AbhigyaKrishna/JavaAssistBackdoorRemover)

- Ne pas utiliser l'extension javascript de Papi (Reverse shell possible)

- Ne pas utiliser HolographicDisplay en dessous de la version 2.0 (Possibilité d'afficher des fichiers systèmes)

- Bloquer les commandes : /fill, //sphere, /bc, /execute

- Ne pas utiliser de plugins qui sont crack ou autres car vous aurez de sûr une backdoor dedans

- Utilisez Xcord ou LPX mais pas les deux en même temps, cela vous causerait des problèmes

- Mettez vos bases de données sur une machine externe pour éviter de vous faire scrap la db de votre serveur s'ils arrivent à
  à s'emparer du dédié (Externaliser au maximum vos services)

- N'oubliez pas que personne est de confiance donc mettez pas des accès machines à tout le monde pour x raison

- Faites vérifier vos plugins personnalisés par des personnes qui savent tester les plugins, trouver les failles et autres.
