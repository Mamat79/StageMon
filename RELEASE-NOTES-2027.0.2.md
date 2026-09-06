# StageMon 2027.0.2 - Windows

Notes du correctif Windows, validé par tests logiciels et recette visuelle native
courte le 6 septembre 2026. Publication et installation sont tracées séparément.
Les derniers paquets publics macOS restent 2027.0.1, Intel et Apple Silicon ;
ils ne sont ni modifiés ni renommés par ce correctif Windows.

## Français

- Bandeau de suite commun : icône produit, menus, Connexion StageFlow, Alertes,
  choix Clair/Sombre, FR/EN, Guide de suite et Aide StageMon. Les commandes
  passent sur une seconde ligne selon leur largeur réelle ; cibles de 36 points,
  noms accessibles et focus clavier. Le bandeau reste bleu nuit en thème clair.
  Le sélecteur de langue garde un contraste lisible. À petite largeur, la
  navigation se replie initialement pour laisser de la place à la grille CUE ;
  votre choix explicite avec la flèche reste prioritaire lors du redimensionnement.
- Connexion StageFlow : état écrit et point coloré, projet complet consultable,
  projet local distinct d'une session LIVE. Le même centre regroupe ouverture
  locale, découverte, association par code, actualisation et déconnexion.
  Aucun démarrage audio implicite ; autonomie conservée.
- Alertes : le bouton ouvre le centre sans désactiver la réception. Le compteur,
  la réception désactivée et la suspension côté hôte sont distingués ; les
  actions existantes d'acquittement restent séparées du réglage de réception.
- Téléphone : « Mon écoute » mémorise Général ou A à F dans le navigateur pour
  l'adresse de la télécommande. Un circuit non configuré n'apparaît pas : retour
  à Général, puis restauration du choix si ce circuit redevient disponible.
  Un autre navigateur, une autre adresse ou un autre port a sa propre préférence.
  Aucun droit ou niveau n'est mémorisé ici ; aucun ordre audio au chargement.
- Mode hybride ASIO vers WASAPI/WDM : latence de sortie demandée explicite
  (60/100 ms), file instantanée et capacité, manques, silence ajouté et
  débordements visibles dans Diagnostics. Le silence initial est compté à part.
  La capacité de 500 ms n'est pas une latence totale mesurée. Tampon NAudio,
  politique de débordement et latences inchangés, sans compensation de dérive.
  Mesures logicielles uniquement, pas un verdict sur la carte ou le Wi-Fi.
  Les diagnostics longs défilent et se réactualisent aussi moteur arrêté.
- CUE, Toujours, LINK, snapshots, couleurs A-F, plafonds, mutes, fichiers,
  licence et prix inchangés. Contrôles HF et distinctions par plateforme :
  [matrice exacte](qa/PLATFORM-CONTROL-SCOPE-2027.md).

## English

- Shared suite header: product icon, menus, StageFlow connection, Alerts,
  explicit Light/Dark choices, FR/EN, suite Guide and StageMon Help. Commands
  wrap according to measured width, with 36-point targets, accessible names
  and keyboard focus. The header remains dark blue in Light mode.
  The language selector keeps readable contrast. Narrow layouts initially fold
  navigation to retain CUE grid space; an explicit arrow choice wins on resize.
- StageFlow connection: text plus status dot, full project name available,
  local projects distinct from LIVE sessions. One centre exposes local open,
  discovery, code-based join, refresh and disconnect. No implicit audio start.
- Alerts: opening the centre does not disable reception. Count, reception off
  and host-paused states remain distinct; acknowledgement and reception are
  separate actions using the existing safety rules.
- Phone: My monitor remembers General or A-F in this browser for this remote
  address. Unconfigured circuits remain hidden, temporarily falling back to
  General. Another browser, address or port has its own preference. This stores
  neither permissions nor levels and sends no audio command on page load.
- ASIO to WASAPI/WDM hybrid mode: requested output latency (60/100 ms), current
  queue/capacity, underruns, inserted silence and overruns appear in Diagnostics.
  Initial silence is counted separately. The 500 ms capacity is not measured
  total latency. Existing NAudio queue policy and latencies are retained; no
  drift compensation is introduced. Software metrics do not establish a
  physical device fault.
  Long diagnostics scroll and also refresh on driver selection while stopped.
- CUE, Always, LINK, snapshots, A-F colours, ceilings, mutes, project formats,
  licensing and price remain unchanged. macOS 2027.0.1 packages remain unchanged;
  these new UI/remote changes require a later accepted Mac build.

## Recette / Acceptance

251 exécutions de tests réussies, 32 groupes de contrôles WPF dont 912 assertions
de cohérence, et tests de télécommande sur boucle locale. Recette native du même
binaire : FR/EN, clair/sombre, focus clavier et une largeur compacte ; aucun audio
démarré. Échelle du profil Windows déclarée à 96 DPI ; pas de qualification
multi-DPI. Une capture de composant hors écran n'est pas une capture du bureau
installé. Les étapes release, installation et site sont tracées séparément.
Tests matériels audio/HF/téléphone
non réalisés pour ce lot. Aucun nouveau job macOS lancé sans coordination et
preuve de minutes disponibles. Aucun changement de budget.
