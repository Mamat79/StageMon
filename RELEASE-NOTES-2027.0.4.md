# StageMon 2027.0.4 — Windows

## Français

Cette livraison Windows améliore la cohérence du suivi StageFlow LIVE, le réglage
des circuits d'écoute A à F et la lisibilité des thèmes sombre et clair.

- L'autorité LIVE locale et réseau repose désormais sur la même combinaison
  projet, session et bail. Une session ou un projet inattendu est refusé avant
  l'application d'un snapshot.
- Un rafraîchissement LIVE distant ne supprime plus à tort l'indicateur de
  modifications locales.
- Le nombre de circuits configurables est limité explicitement de 2 à 6. Le
  sélecteur est verrouillé pendant le traitement audio avec une explication
  visible ; les réglages mono, couleur, CUE et Toujours sont conservés.
- Les textes d'accent, d'avertissement et d'erreur, les sélections et les états
  désactivés utilisent des paires fond/texte dédiées dans les deux thèmes.

Les contrôles logiciels ciblés ont réussi : 98 vérifications circuits/LIVE, 203
tests Infrastructure, 43 tests Core, 218 assertions du centre de connexion et
932 assertions du bandeau de suite. Le relevé de contraste compte 1 506 textes
activés et 20 désactivés, sans échantillon sous 4,5:1 dans le périmètre mesuré.

Une fixture Windows isolée a confirmé le popup 2–6 et la séquence visible
2 → 3 → 4 → 5 → 6 → 2. Elle n'a lancé ni audio, ni serveur QR, ni licence, ni
projet utilisateur. Le thème clair n'a pas fait l'objet d'une seconde recette
GUI native complète et aucun matériel audio, téléphone ou réseau de spectacle
n'est qualifié par cette livraison.

Important : l'intermittence signalée où le sélecteur resterait bloqué à 2 n'a
pas été reproduite. Elle n'est donc pas présentée comme corrigée.

Fermez StageMon avant toute installation. Les projets, préférences, licences et
le prix restent inchangés. Les paquets macOS 2027.0.3 ne sont pas modifiés.

## English

This Windows release improves StageFlow LIVE authority handling, A–F monitor
circuit configuration and dark/light theme readability.

- Local and network LIVE now use the same project, session and lease authority.
  Unexpected sessions or projects are rejected before a snapshot is applied.
- A remote LIVE refresh no longer clears the local dirty state incorrectly.
- The configurable monitor count is explicitly limited to 2–6. The selector is
  locked with a visible explanation while audio is processing; mono, colour,
  CUE and Always settings are preserved.
- Accent, warning and error text, selections and disabled controls use dedicated
  foreground/background pairs in both themes.

Targeted checks passed: 98 circuits/LIVE checks, 203 Infrastructure tests, 43
Core tests, 218 connection-centre assertions and 932 suite-header assertions.
The contrast scan measured 1,506 enabled and 20 disabled text samples with none
below 4.5:1 within its stated scope.

An isolated native Windows fixture confirmed the 2–6 popup and the visible
2 → 3 → 4 → 5 → 6 → 2 sequence. It started no audio, QR server, licence flow or
user project. Light theme did not receive a second complete native GUI pass, and
this release does not qualify physical audio, a phone or a show network.

Important: the reported intermittent condition in which the selector could
remain stuck at 2 was not reproduced. It is therefore not claimed as fixed.

Close StageMon before installation. Projects, preferences, licences and pricing
are unchanged. The macOS 2027.0.3 packages are not modified.
