## Vous trouverez ci-dessous une petite liste de choses à faire pour limiter au max les relou qui grief vos serveurs. La liste est tout sauf parfaite et je ne dis pas qu'elle n'est pas bypassable. C'était juste un petit cadeau de départ lol. Faites des pull requests si vous voulez modifier ou ajouter un truc

- Accès au Dashboard admin du site obligatoirement par un VPN.

- Accès au compte admins ingame par un proxy particulié (on aura deux proxy redondé pour les joueurs et un proxy réservé aux admin/fonda/compte OP). Les users qui ont des perms importantes seront bloqués sur le proxy joueurs. Le proxy pour les admins doit également implémenter l'authentification à 2 facteurs (afin d'éviter en désastre en cas de hack d'un compte admin).

- un /pin sur le faction avec un mot de passe qui change tous les jours qui seraient envoyé aux admins dans un groupe télégram) que seulement les gens OP/ayant des perms admins connaitront, ou une 2FA avec une libs Google Auth MISE A JOUR.

- Un plugin d'antiOP / perm étoile: toutes personne qui devient OP, qui change son gamemode, qui se give quelques choses sur le serveur ou qui s'attribue des permissions admin (*) (se sont des examples hein, mettez toutes les commandes sensibles ) qui n'est pas dans les fichiers de config du plugin sont INSTANT ban.

- Un plugin d'antiGM. Tout est dis dans le titre.

- Les commandes de luckperm sont éxecutables uniquement en console.

- Desactivation du OP dans le server.properties

- Faites des backups incrementales sur un disque dur different de celui de votre dédié et en même temps sur un object storage de scaleaway ( outil conseiller: Borgbackup y'a tout un systeme de rotation de log et ne prend pas beaucoup de places sur le disque. Logique c'est incrémentale) Perso j'avais une backup par heure, 2 backups par jour, une backup par semaine et une backup par mois.

- Niveau antibot vous pouvez faire du racisme sur iptable,  GL à vous ( tcpshield est bypassable ).

- Niveau DDoS de site CF free c'est une passoire, même si vous faites du racisme. Essayer de vous orienter sur du AWS mais faut avoir les compétences pour le maintenir sans payer trop chère

- Nos chères hackers de l'internet aime bien le scan de port aussi avec nmap, bloquer-le avec iptables c'est pas compliqué.

- Niveau firewall temps qu'on y est. Il faut ABSOLUMENT restreindre les ports de vos serveurs de jeux UNIQUEMENT à l'ip du bungeecord. Sinon nos chers h4xor minecraft pourront se connecter directement sur le serveur sans passer par votre PROXY.

- Ah oui aussi, le firewall d'ovh que tout le monde oublie de config est pas mal aussi. Vous pouvez utiliser le firewall d'ovh et utilise iptable uniquement pour gerer le L7 ( antibot par exemple )

- ipset c'est bien aussi si vous voulez ban des longues liste d'ip.

- Installer Port-Sentry en mode Advanced et le configurer de sorte de blacklist les ip détectées 

- Bloquer les packet de netcat / curl

- N'utilisez pas PhpMyadmin, sinon bloquez le par accés VPN ou avec un mot de passe sur la page.

- Si vous utilisez Pterodactyl, autorisez le uniquement en VPN

- Ne donnez pas les permissions * a tous pour rien, si une personne a les perms * /op (car c'est plus simple a gérer souvent)  il aura pleins de commandes qui ne lui serviront a rien, mais qui pourrait être dévastateur si cette personne se fait hack sont compte. 

- Sur vos serveurs de dev, mettez dés le début votre système d'authentification (c'est souvent sur les serveurs de devs, que les h4xors viennent mettre des pnj give, gm, op etc...) 

- Avant l'open, véririfiez chaque PNJ et chaque zone Worldguard, vérifier qu'il n'y en a pas une étrange,  vérifiez aussi les permissions qu'on les players. 

- Faites attention à avoir toujours vos plugins à jours 

- Passez vos plugins dans un remover-backdoor. Exemple : (https://github.com/AbhigyaKrishna/JavaAssistBackdoorRemover)

- Ne pas utilisé l'extension javascript de Papi (Reverse shell possible)

- Ne pas utilisé holographicdisplay en desous de la version 2.0 (Possibilité d'afficher des fichiers sytemes)

- Bloquer les commandes : /fill, //sphere, /bc, sqlexec select * from {history}, /execute

- Ne pas utilisé de plugins qui sont crack ou autres car vous aurez de sûr une backdoor dedans

- Utilisez Xcord ou LPX mais pas les deux en même temps qui causeras des problèmes

- Mettez vos base de données sur une machine externe pour éviter de se faire scrap la db de votre serveur si ils arrivent à
  à s'emparer du dédier (Externaliser au maximum vos services)

- N'oubliez pas que personne est de confiance donc mettez pas des accèss machines a tous le monde pour x raison

- Faites vérifier vos plugins personnalisés par des personnes qui savent tester les plugins, trouver les failles et autres.
