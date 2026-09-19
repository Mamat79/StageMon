# StageMon 2027.1.0 — Windows et macOS

## Projets et fiabilité

- Un projet StageMon modifié peut être enregistré, fermé sans enregistrer ou
  conservé ouvert en annulant la fermeture, sous Windows comme sous macOS.
- Les sauvegardes natives sont atomiques et gardent une génération `.bak` pour
  la récupération si le fichier principal devient illisible.
- Sous Windows, la fermeture finale est différée après la confirmation afin
  d'éviter une fermeture réentrante, y compris depuis le rappel de licence.

## Licence

- L'essai reste entièrement fonctionnel. Un rappel d'achat apparaît pendant les
  30 premiers jours et peut être fermé immédiatement.
- Après 30 jours, une attente de 60 secondes est appliquée une seule fois au
  démarrage du processus, puis toutes les fonctions restent disponibles.
- Une licence valide retire le rappel et l'attente. Le prix public reste 49 € TTC.

## StageFlow LIVE et télécommandes

- Le contrat LIVE 2027.1 reste additif et compatible avec le protocole précédent.
  Les snapshots hors projet ou session sont refusés et les commandes sont
  acquittées une seule fois.
- Le suivi du groupe StageFlow est optionnel. Clear Cue A/B, les alertes et la
  télécommande directe restent indépendants.
- Le serveur QR est arrêté au lancement. Il ne s'ouvre qu'après l'action
  explicite de l'utilisateur dans Connexions.

## Écoute téléphone

- L'écoute WebRTC/Opus sur téléphone est facultative et indépendante des sorties
  physiques A à F. Elle ne démarre jamais automatiquement.
- Aucun flux audio n'est envoyé tant que l'écoute n'est pas activée. Son niveau
  et son mute sont propres au téléphone ; aucun microphone du téléphone n'est
  utilisé et aucun enregistrement n'est créé.
- Le téléphone peut suivre A, B ou A+B lorsque LINK est actif. Cette copie de
  contrôle ne modifie ni les CUE ni le patch des sorties physiques.

## Interface et plateformes

- Les panneaux de navigation et de monitoring s'adaptent mieux aux fenêtres
  étroites, tout en respectant le choix manuel de l'opérateur.
- Les thèmes clair et sombre, le français et l'anglais, les informations de
  version et les guides restent disponibles sur Windows et macOS.
- Windows est livré en installateur x64. Les paquets macOS Apple Silicon et Intel
  sont construits par Codemagic à partir du même tag produit.

## Validation et limites

- Tests automatisés : cœur, infrastructure, licence, NAudio, CoreAudio et logique
  macOS, plus la télécommande Chromium isolée et les contrôles LIVE croisés.
- Le démarrage de l'audio reste volontaire. Les tests logiciels ne qualifient pas
  une carte audio particulière, deux horloges matérielles, un Wi-Fi de spectacle,
  un téléphone physique ni la latence réelle d'un casque Bluetooth.
- Les paquets macOS utilisent une signature d'intégrité ad hoc. La signature
  Apple Developer ID et la notarisation ne font pas partie de cette livraison.

---

# StageMon 2027.1.0 — Windows and macOS

StageMon now provides safer project close/save recovery, an additive StageFlow
LIVE 2027.1 contract, responsive panels and an explicit opt-in QR server. The
optional WebRTC/Opus phone listening path is separate from physical monitors A
to F: it sends no audio until enabled, never uses the phone microphone and never
records audio.

The 30-day trial remains fully functional. During the trial the purchase reminder
can be closed immediately; afterwards one 60-second wait applies per process and
all features remain available. A valid licence removes both. Public price remains
€49 including VAT.

Windows is distributed as an x64 installer. Codemagic builds Apple Silicon and
Intel macOS packages from the same product tag. Hardware audio, a physical phone,
show Wi-Fi and Bluetooth latency require validation on the actual equipment.
macOS packages are ad-hoc signed; Apple Developer ID signing and notarization are
outside this release.
