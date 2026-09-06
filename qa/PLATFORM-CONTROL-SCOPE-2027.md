# StageMon - capacités exactes par plateforme et chemin de contrôle

Inventaire source du 6 septembre 2026. Windows 2027.0.2 en préparation ; Windows
et macOS publics 2027.0.1. Une bibliothèque de protocole commune ou un test MIDI
réussi sur Mac ne signifie pas qu'un port MIDI est raccordé à l'application Mac.

| Chemin | Windows | macOS public 2027.0.1 | Circuits et limites |
| --- | --- | --- | --- |
| Matrice, sorties, snapshots CUE | Oui | Oui | A/B par défaut, C-F seulement ajoutés volontairement ; mêmes projets StageMon et domaine StageFlow |
| Télécommande web QR | Oui | Oui | Général ou vues A-F ; protections poste, mutes prioritaires et plafonds ; activation volontaire |
| Mon écoute mémorisée | Nouveau correctif 2027.0.2 | Pas dans le DMG 2027.0.1 | Préférence de présentation par navigateur/origine, pas un droit |
| OSC moderne `/stage-monitoring/v1/` | Oui, serveur activé par l'opérateur | Pas de serveur OSC raccordé dans l'hôte Mac | Résolution par ID du bus configuré, dont C-F ; CUE/persistant/focus/pas/clear/niveau/mute |
| TouchOSC historique | Oui, profil legacy | Pas raccordé dans l'hôte Mac | Ancien layout A/B, ne représente pas C-F |
| Catalogue automatisation `/silemio/stagemon/` | Oui | Pas de serveur OSC raccordé dans l'hôte Mac | Clear A/B, mute A/B, choix/pas de patch, start/stop audio ; pas de raccourci C-F dans ce catalogue |
| MIDI Note/CC/Program Change, learn, retour | Oui, pont NAudio Windows | Pas de pont CoreMIDI raccordé dans l'hôte Mac | Commandes du catalogue d'automatisation ; pas de faders MIDI A-F ni de promesse C-F |
| ASIO / WASAPI / WDM | Oui | Non | Hybride ASIO entrée vers sortie Windows possible ; horloges non compensées |
| CoreAudio | Non | Oui | Périphérique duplex ou agrégat déjà préparé par l'opérateur ; aucun agrégat créé automatiquement |
| HF EW-DX en lecture seule | Oui | Oui | EM 2, EM 2 Dante, EM 4 Dante ; firmware ≥4.0, SSCv2, schéma compatible 1.7 ; recette matérielle restante |
| Shure / Wisycom | Non | Non | Étude précise ci-dessous ; pas d'adaptateur ou de compatibilité de marque globale annoncés |

## Preuves de raccordement

- Windows : `ExternalControlWindow`, `MainViewModel.StartExternalOscAsync`,
  `StageMonMidiBridge`, `StageMonAutomationCommandCatalog`, `OscCommandRouter`.
- Mac : `MacMainWindow`, `.Connections`, `.Remote`, `.Live` : vrais chemins
  CoreAudio, télécommande, projets et association LIVE ; absence de création
  d'un `OscUdpService` ou d'un pont MIDI. Les tests communs du décodeur MIDI ne
  changent pas cette absence.
- Les projets et réglages ne sont pas supprimés lorsqu'une plateforme n'expose
  pas un contrôle. Aucune suppression de compatibilité dans ce lot.

## HF : revue constructeur du 6 septembre

EW-DX suit les familles de la [documentation SSC officielle](https://docs.cloud.sennheiser.com/en-us/api-docs/api-docs/sound-control-protocol.html).
Le lecteur valide `EWDX2CHS`, `EWDX2CHDS` ou `EWDX4CHDS`, le protocole 2, le
schéma compatible 1.7 et le firmware avant les mesures. Les identifiants restent
en mémoire ; HTTPS vérifié, GET uniquement, RX/TX associés explicitement.
[Détail existant du protocole et de la sécurité](HF-PROTOCOL-SCOPE.md).

Shure : familles ciblées AD4D/AD4Q (Axient Digital), ULXD4D/ULXD4Q. Les pages
officielles [AD4](https://www.shure.com/en-US/docs/commandstrings/AD4) et
[ULXD](https://www.shure.com/en-US/docs/commandstrings/ULXD) n'ont livré que leur
coquille documentaire lors de cette revue. Le PDF AD4 lié à ces commandes est
toujours refusé par le serveur (HTTP 403), malgré des extraits indexés. Aucun
contournement. Il manque une lecture complète vérifiable de la syntaxe, des
unités, sentinelles, index TX, cadences et versions, puis les essais identifiés.
Un extrait GET ALL n'est pas une spécification suffisante pour une télémétrie
complète. Aucun SET ni abonnement constructeur envoyé.

Wisycom : [MRK980](https://wisycom.com/product/mrk980/) documente l'arrivée
d'Ember+ dans le firmware 2.6. Cela ne définit pas l'arbre de télémétrie.
[MCR54](https://wisycom.com/product/mcr54/) présente le contrôle via USB-C ou
Bluetooth et Manager ; cela ne constitue pas une API réseau équivalente au
MRK980. Il manque l'arbre officiel/SDK par modèle et firmware, ses types, unités,
droits de lecture et valeurs absentes. Aucun nœud supposé compatible, aucune
découverte ou interrogation des appareils de l'utilisateur.

## Pont hybride : qualification honnête

Le buffer mesuré réemploie le `CircularBuffer` NAudio 2.2.1 utilisé par
[`BufferedWaveProvider`](https://github.com/naudio/NAudio/blob/v2.2.1/NAudio.Core/Wave/WaveProviders/BufferedWaveProvider.cs).
Le [tampon constructeur](https://github.com/naudio/NAudio/blob/v2.2.1/NAudio.Core/Utils/CircularBuffer.cs)
renvoie les octets lus/écrits. Ces valeurs servent aux compteurs, sans verrou
supplémentaire dans les opérations audio, sans allocation après préallocation,
sans rééchantillonnage ni compensation d'horloge. Tests de comparaison avec le
buffer précédent, débordement, sous-remplissage, ordre concurrent et allocations
prévus dans `StageMonitoring.NAudio.Tests` ; résultats à consigner après exécution.
