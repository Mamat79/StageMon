# StageMon 2027.1.5 — Windows x64

Complément Windows du 19 octobre 2026 à la release 2027.1.5.
Les indications « macOS uniquement » des notes initiales décrivent la première
publication de cette release. L’installeur Windows est désormais ajouté ; les
quatre fichiers macOS, leur tag et leur qualification restent inchangés.

## Windows : livraison et contrôles effectués

- Installeur autonome pour Windows x64, version de fichier 2027.1.5.0.
- Navigation F10 vérifiée sur une vraie fenêtre Windows : depuis le bouton
  d’effacement CUE B, F10 place le focus sur Fichier sans ouvrir son menu.
- 438 tests unitaires, 927 assertions de conformité, 10 groupes navigateur et
  deux cas de protocole ont réussi sur le candidat Windows livré. Quinze
  assertions ciblent également le gestionnaire F10.
- Les 19 fichiers extraits de l’installeur et installés sur le poste de
  validation correspondent aux empreintes du paquet. La mise à jour a été
  contrôlée avec sauvegardes privées et comparaison des six emplacements de
  données avant/après, y compris les flux supplémentaires et métadonnées.
  Réglages, données de licence et fichiers personnels contrôlés sont conservés.
  Aucune activation, réinitialisation de licence ou ouverture de projet réel
  n’a été effectuée par cette validation.

## Limites

La vérification native porte sur le candidat exact à 96 DPI ; la matrice complète
de DPI, le matériel audio, le réseau réel et les téléphones restent non validés.
L’application installée n’a pas été relancée après la mise à jour ; son
exécutable est identique au candidat ayant passé les contrôles natifs.
Le blocage intermittent du sélecteur à deux circuits n’a pas été reproduit et
n’est pas présenté comme corrigé. L’installeur Windows ne porte pas de signature
Authenticode.

Les notes de préparation embarquées dans le paquet gardent leur date d’origine.
Le présent document décrit l’état livré et vérifié au 19 octobre 2026.
Les échanges V1 restent le parcours par défaut ; les restrictions V2 et les
limites propres aux paquets macOS restent celles de leurs recettes respectives.

## English

Windows 2027.1.5 is added to the existing release without changing its four macOS
assets or tag. The exact Windows executable passed 438 unit tests, 927
conformance assertions, 10 browser groups, two protocol cases and 15 focused
F10-handler assertions. Native F10 focus was observed in a real Windows window
at 96 DPI. All 19 installer payload files were extracted and verified, and a
local upgrade preserved the six checked data locations and their metadata.
The installed application was not started after the upgrade. Physical audio,
live networks, phones and full DPI coverage remain unverified. The intermittent
two-circuit selector issue is not claimed fixed. The installer is not
Authenticode-signed. Existing macOS qualification is unchanged.
