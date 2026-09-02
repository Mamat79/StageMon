# StageMon 2026.3

## LIVE réseau StageFlow

- découverte locale du maître StageFlow par UDP multicast, puis association explicite par code à six chiffres ;
- états visibles **Projet StageMon / Projet StageFlow local / Session StageFlow LIVE**, avec nom de la session et point d’état accessible ;
- réception des alertes de labels activée par défaut à la jonction, avec ancien → nouveau, origine, heure, compteur et acquittement local persistant ;
- interrupteur propre à StageMon : en mode désactivé, aucune alerte ne s’accumule ni ne réapparaît en retard, sans affecter le maître ou les autres postes ;
- snapshots et assets adoptés explicitement dans un cache privé vérifié par taille et SHA-256, sans exposer le chemin distant ni modifier les domaines étrangers ;
- commandes stables Clear Cue A/B, navigation de patch, audio et mute A/B acquittées vers StageFlow ;
- écran commun **OSC · MIDI · Stream Deck**, avec les neuf mêmes identifiants en autonomie et en LIVE ;
- écoute et retour OSC configurables, MIDI Learn et sortie MIDI de feedback ;
- accès direct au plugin/kit Stream Deck publié avec StageFlow ;
- retrait manuel sans fermer le projet ni empêcher StageMon de fonctionner seul.

Mise à jour Windows de StageMon centrée sur l’accès à la télécommande locale et
la cohérence graphique de la suite SiLeMIO.

## Nouveautés

- les libellés et liens inter-suite adoptent le nom public **StageDesk** ; les identifiants techniques et les anciens formats restent compatibles ;
- petite icône `▦` discrète en haut à droite, commune à StageFlow et StageMark ;
- barre de menus redessinée avec les mêmes déclencheurs sobres et panneaux arrondis que StageMark ;
- fenêtre QR dédiée, bilingue et compatible avec les thèmes clair et sombre ;
- matrice libérée de l’ancien grand panneau QR permanent ;
- volets de navigation et de monitoring repliables par une petite flèche ;
- bouton `LINK A ↔ B` très visible entre les deux monitors : en mode exclusif ou additif, une cue choisie ou retirée agit sur A et B ;
- vocabulaire opérateur unifié : `CUE` et `CLEAR CUE` en français comme en anglais ;
- diagnostic explicite lorsqu’une règle entrante du pare-feu Windows bloque StageMon ;
- réparation volontaire sous contrôle UAC, désormais exécutée directement par StageMon sans script PowerShell opaque : chaque règle entrante de blocage visant l’exécutable est retirée, y compris les doublons TCP/UDP portant le même nom ;
- création d’une autorisation TCP limitée au sous-réseau local lorsqu’aucune autorisation active n’existe ;
- vérification automatique après réparation et message précis si Windows conserve encore une règle de blocage ;
- explications directes si le téléphone et le PC ne sont pas sur le même réseau ;
- jusqu’à 24 téléphones ou tablettes simultanés, avec une identité et un bail séparés pour chacun, liste locale et révocation individuelle ;
- conservation du jeton éphémère et de l’absence de cloud.

Les fonctions audio, les projets natifs `.stagemon.json`, les projets communs
`.stageflow`, les backends ASIO/WASAPI/WDM et le prix permanent de 49 € TTC
restent inchangés. La qualification du matériel audio demeure nécessaire avant
une exploitation live critique.

La recette Windows du 2 septembre 2026 compile sans avertissement, réussit
les 86 tests automatisés et le benchmark 64/128/192/256 canaux sans allocation
ni callback tardive. L’ouverture réelle de la fenêtre, ses quatre onglets et le
démarrage/arrêt OSC ont aussi été contrôlés dans le binaire Release.
