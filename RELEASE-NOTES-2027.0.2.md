# StageMon 2027.0.2 - Windows - connections-20260906-r2

Build Windows `connections-20260906-r2`, sous le numéro public 2027.0.2 conservé.
Le binaire produit est celui compilé depuis `12a3351` et accepté sous la candidate
connexions r1 ; l’emballage r2 le reprend sans recompilation. La recette native
de la livraison initiale décrite plus bas ne valide pas ce nouveau binaire.
L’installeur contient la note de candidate gelée avant publication ; cette note
publique identifie le nouveau build et son périmètre exact.

- Installeur : **58 592 968 octets** ; SHA-256
  `8278D10F9730E6A5F73AACEBD20C05D3810A7E7D93ADCA2685F7A1BB126D9447`.
- Exécutable : **2027.0.2.0** ; SHA-256
  `55FF05984F15B8462699ED8A3F163D3266203F6CF5FE3825E013640F25BE939F`.
- Sources d’emballage : `b97e982` ; manifeste de livraison joint.
Les derniers paquets publics macOS restent 2027.0.1, Intel et Apple Silicon ;
ils ne sont ni modifiés ni renommés par ce correctif Windows.

## Français

### Build connexions du 6 septembre 2026

- Un seul centre non modal, organisé comme StageMark : Connexion StageFlow,
  projet courant et Retour au projet, puis StageFlow LIVE / Télécommande StageMon.
  L’icône téléphone ouvre la même page, dans la rubrique télécommande. Le QR,
  Copier le lien, l’arrêt et les contrôleurs restent intégrés ; le client mobile
  lui-même n’est pas modifié. La disposition s’adapte aux petites fenêtres.
- Les sessions sur ce PC ou le réseau local, l’association LIVE et le service
  de télécommande ont des états distincts. Le service arrêté n’est plus annoncé
  accessible à StageFlow. Un état absent dans une ancienne version reste inconnu.
  Le service actif n’accorde aucun droit et ne contourne pas le projet, la session,
  le bail, le ticket ou la révocation.
- Démarrage et préférences préexistants conservés ; ouvrir le centre n’active pas
  la télécommande ni l’audio. Une erreur de démarrage n’est plus remplacée par un
  message « QR active ». Vérification du pare-feu uniquement sur demande.
- Validation ciblée : 218 assertions centre/handoff, 912 assertions de bandeau,
  30 tests SuiteConsole réussis, compilation sans erreur ni avertissement.
  Croisement réel avec le producteur StageFlow : 40 assertions de fixture ;
  recette Chromium de la page Remote réussie. Observation native FR/sombre,
  focus clavier, centre en accessibilité et mesure de la fenêtre à 96 DPI.
  Aucun essai téléphone réel, audio matériel ou matrice native multi-DPI revendiqué.

### Livraison initiale — historique conservé

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

### Connections build, 6 September 2026

Build `connections-20260906-r2` retains public version 2027.0.2 and packages the
accepted `12a3351` executable unchanged. The exact installer and executable hashes
are listed above. The embedded candidate note was frozen before publication;
this public note identifies the replacement Windows build. Mac packages stay unchanged.

- One non-modal centre following StageMark: StageFlow connection, current project
  and Back to project, then StageFlow LIVE / StageMon remote. The phone icon opens
  the remote section of this same centre. QR, Copy link, stop and controllers stay
  embedded; the mobile client itself is unchanged. The layout adapts to small windows.
- Sessions on this PC or the local network, LIVE association and the remote service
  have separate states. A stopped remote is no longer advertised as accessible to
  StageFlow. Missing state in older versions stays unknown. A running service grants
  no permissions and bypasses no project, session, lease, ticket or revocation checks.
- Existing startup behaviour and preferences are preserved. Opening the centre
  starts neither remote nor audio. Startup errors are no longer overwritten by
  a “QR active” message. Firewall inspection is an explicit action only.
- Targeted verification: 218 centre/handoff assertions, 912 header assertions and
  30 SuiteConsole tests passed; build has no warnings or errors. Real StageFlow
  producer interop: 40 fixture assertions; Chromium Remote page checks passed.
  Native French/dark view, keyboard focus, centre accessibility and exact-window
  DPI measured at 96. No physical-phone/audio or multi-DPI native matrix claim.

### Initial delivery — retained history

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

## Recette de la livraison initiale / Initial delivery acceptance

Ces preuves concernent uniquement le binaire initial, pas le nouveau build connexions.
251 exécutions de tests réussies, 32 groupes de contrôles WPF dont 912 assertions
de cohérence, et tests de télécommande sur boucle locale. Recette native du même
binaire : FR/EN, clair/sombre, focus clavier et une largeur compacte ; aucun audio
démarré. Échelle du profil Windows déclarée à 96 DPI ; pas de qualification
multi-DPI. Une capture de composant hors écran n'est pas une capture du bureau
installé. Les étapes release, installation et site sont tracées séparément.
Tests matériels audio/HF/téléphone
non réalisés pour ce lot. Aucun nouveau job macOS lancé sans coordination et
preuve de minutes disponibles. Aucun changement de budget.
