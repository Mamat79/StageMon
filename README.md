# SiLeMIO Stage Monitoring

Stage Monitoring est une matrice d’écoute Windows pensée pour le line-check et
les changements de plateau rapides. Elle propose deux écoutes stéréo
indépendantes, un changement immédiat de patch et une télécommande locale par
QR code, dans le style de la suite SiLeMIO.

## Fonctions principales

- jusqu’à 256 canaux d’entrée et deux bus stéréo ;
- sélection de plusieurs sources par écoute ;
- sources permanentes `∞` toujours entendues pendant les solos et changements
  de patch ;
- numéros de patch, noms des sources, micros et notes visibles ;
- patchs interchangeables sans redémarrage du moteur audio ;
- niveaux bornés, mutes locaux prioritaires et rampes anti-clic ;
- télécommande web locale par QR code, sans service cloud ;
- adaptateur TouchOSC historique optionnel ;
- intégration StageFlow LIVE V1 en lecture seule, avec repli autonome.

## StageFlow LIVE

Lorsqu’un projet `.stageflow` est ouvert, Stage Monitoring peut suivre les
groupes, numéros, labels, micros, notes et patchs compatibles pendant une
session LIVE valide. L’option est activée par défaut et peut être désactivée.

Les quatre états sont visibles en français et en anglais : LIVE connecté, LIVE
disponible mais suivi désactivé, autonome et conflit. Une mise à jour LIVE ne
redémarre pas l’audio et ne remplace pas les routes, sources permanentes,
niveaux ou mutes locaux.

La passerelle QR unifiée StageFlow est une évolution future. La télécommande QR
locale propre à Stage Monitoring reste la fonction disponible dans cette
version.

## Prix et essai

La licence permanente coûte **49 € TTC**. Un essai de 30 jours permet d’utiliser
toutes les fonctions. L’activation peut être réalisée en ligne ou hors ligne.

## Installation

1. Téléchargez `StageMonitoring-2026.2-Setup.exe` et son fichier `.sha256` dans
   la [dernière release](https://github.com/Mamat79/Stage-Monitoring/releases/latest).
2. Vérifiez le SHA-256 de l’installeur.
3. Fermez Stage Monitoring s’il est déjà ouvert, puis lancez l’installeur.
4. Choisissez `Simulation` pour découvrir l’interface ou sélectionnez votre
   driver ASIO et vos quatre sorties avant un essai matériel encadré.

Windows 10/11 x64 est requis. Le backend ASIO doit être qualifié sur le matériel
et le driver réellement utilisés avant toute exploitation critique.

## Confidentialité et réseau

Stage Monitoring ne requiert aucun compte cloud pour l’écoute ou la
télécommande. Le QR code ouvre un serveur sur le réseau local avec un jeton
éphémère ; un seul appareil peut piloter à la fois. L’utilisateur reste maître
des autorisations de pare-feu Windows.

© 2026 SiLeMIO — By Mamat----[]---. Logiciel commercial propriétaire.
