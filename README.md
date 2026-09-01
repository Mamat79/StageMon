<p align="center">
  <img src="stagemon-icon.png" width="112" alt="Icône StageMon">
</p>

<h1 align="center">StageMon</h1>

<p align="center">
  <strong>Deux écoutes, un patch instantané, un contrôle clair pour le line-check et les changements de plateau.</strong><br>
  Hors ligne · Français / English · Windows
</p>

<p align="center">
  <a href="https://github.com/Mamat79/StageMon/releases/latest"><strong>⬇ Télécharger StageMon</strong></a>
</p>

---

## StageMon, à quoi ça sert ?

StageMon est une matrice d’écoute conçue pour les techniciens son, les équipes
de plateau et les régies qui doivent vérifier rapidement de nombreuses sources.
Il regroupe jusqu’à 256 entrées, deux écoutes stéréo indépendantes et plusieurs
patchs dans une interface lisible, utilisable sur un seul ordinateur Windows.

L’objectif est simple : **retrouver immédiatement la bonne source dans la bonne
écoute, sans reconstruire la matrice à chaque changement de groupe ou de
plateau**.

StageMon fonctionne seul. Il peut également ouvrir un projet commun
`.stageflow` et collaborer avec StageFlow, Save My Time, Dante Config Editor et
StageMark. Chaque logiciel reste autonome : StageFlow est gratuit et
facultatif.

## Un exemple concret

Vous devez enchaîner les balances de cinq groupes avec 64 sources de plateau et
deux postes d’écoute :

1. créez un projet StageMon ou ouvrez le projet `.stageflow` de la production ;
2. choisissez l’interface d’entrée et les quatre sorties des deux écoutes ;
3. retrouvez les noms de sources, micros et commentaires préparés dans le patch ;
4. sélectionnez un patch ou un groupe sans arrêter le moteur audio ;
5. envoyez une ou plusieurs sources vers l’écoute A, l’écoute B, ou les deux ;
6. conservez les sources indispensables avec les options **Toujours A** et
   **Toujours B** ;
7. effacez une cue, passez à la source suivante ou rappelez un patch en un clic ;
8. si nécessaire, ouvrez la télécommande locale sur un téléphone avec le QR code.

Le technicien garde une vision directe de ce qu’il écoute et peut changer de
groupe sans perdre ses réglages de sécurité.

## Deux écoutes vraiment indépendantes

- Jusqu’à 256 entrées.
- Deux bus stéréo : Monitor A et Monitor B.
- Plusieurs sources simultanées par écoute.
- Mode exclusif pour écouter une seule cue à la fois.
- Mode additif pour construire une écoute avec plusieurs sources.
- Sources permanentes qui restent audibles pendant les changements.
- Niveau et mute propres à chaque Monitor.
- Repli mono indépendant si une seule sortie physique est disponible.
- Affectation libre des sorties physiques A gauche/droite et B gauche/droite.

Les mutes locaux restent prioritaires : une commande distante ne peut pas
réactiver une écoute coupée volontairement sur le poste.

## Changer de patch sans perdre le fil

Chaque patch peut représenter un groupe, une scène, une zone ou un état de la
production. StageMon affiche le numéro de paire, la source, le micro et les
notes utiles, puis remplace immédiatement la liste active sans redémarrer le
moteur audio.

Vous pouvez créer et enregistrer ces patchs dans un projet StageMon autonome,
les importer depuis le classeur Excel StageFlow V3 ou les lire depuis un projet
commun `.stageflow`.

## Tester avant de raccorder le plateau

StageMon contient un mode de simulation pour découvrir l’interface sans carte
son. Des oscillateurs et une lecture musicale permettent aussi de vérifier le
chemin d’écoute avant d’utiliser les entrées réelles.

Pour l’exploitation, l’entrée et la sortie peuvent utiliser ASIO, WASAPI ou
WDM. Les pilotes et les cartes d’entrée/sortie se choisissent séparément lorsque
le matériel l’exige.

## Contrôler depuis le plateau

Le bouton de télécommande affiche un QR code à scanner depuis un téléphone ou
une tablette connectés au même réseau local. Le contrôleur retrouve les mêmes
actions essentielles que dans StageMon, sans compte cloud et sans envoyer le
projet sur Internet.

Jusqu’à 24 téléphones ou tablettes peuvent piloter simultanément. Chaque
appareil reçoit une identité et un bail séparés, révocables depuis l’ordinateur.
La session est temporaire, protégée par un jeton et peut être arrêtée
immédiatement.

## Avec ou sans StageFlow

StageMon sait travailler de deux façons :

- **seul**, avec son propre projet `.stagemon.json` ;
- **dans la suite**, avec le même dossier `.stageflow` que StageFlow, Save My
  Time, Dante Config Editor et StageMark.

Dans un projet partagé, StageMon ne modifie que sa partie. Les données des
autres logiciels sont conservées. Si le Mode LIVE est actif, les changements
compatibles de groupe, labels, micros, notes et patchs peuvent être suivis en
temps réel. Vous pouvez désactiver ce suivi à tout moment et continuer en mode
autonome.

Depuis la console centrale StageFlow, il est possible d’ouvrir StageMon sur le
projet courant, de voir son état de connexion, d’utiliser les raccourcis de cue
et de retrouver sa télécommande dans le QR code unifié.

## Un classeur Excel commun

StageMon peut créer ou importer le classeur Excel StageFlow V3. Vous choisissez
le nombre de groupes et obtenez une feuille par groupe, ainsi qu’une feuille
commune. Le même classeur peut ensuite être ouvert dans StageFlow ou Save My
Time : il n’est donc pas nécessaire de commencer le projet dans un logiciel
précis.

## Interface de la suite SiLeMIO

StageMon reprend les repères visuels communs à StageFlow, StageMark, Save My
Time et Dante Config Editor :

- thème clair ou sombre ;
- langue FR ou EN ;
- bouton d’aide accessible en permanence ;
- mêmes termes pour ouvrir, enregistrer, enregistrer sous et actualiser ;
- signature SiLeMIO · By Mamat----[]--- ;
- informations de projet et d’état visibles sans masquer la matrice.

## Prix et essai

La licence permanente de StageMon coûte **49 € TTC**. Un essai de 30 jours
permet de vérifier l’interface et le fonctionnement avec votre configuration.
L’activation peut être réalisée en ligne ou hors ligne.

StageFlow reste entièrement gratuit et n’est jamais nécessaire pour utiliser
StageMon.

## Installation Windows

1. Téléchargez `StageMon-2026.3-Setup.exe` et son fichier `.sha256` depuis la
   [dernière release](https://github.com/Mamat79/StageMon/releases/latest).
2. Fermez une éventuelle ancienne instance de StageMon.
3. Lancez l’installeur et conservez les options proposées.
4. Ouvrez **StageMon v2026** depuis le raccourci du Bureau.
5. Commencez en mode Simulation, puis sélectionnez vos pilotes et sorties.

Windows 10/11 x64 est requis. Avant une exploitation critique, vérifiez avec le
matériel réel les drivers, les canaux physiques, la fréquence d’échantillonnage,
la latence et les niveaux.

---

<a id="english"></a>

## English

**StageMon** is a Windows monitoring matrix for line checks, stage changes and
fast source verification. It brings up to 256 inputs, two independent stereo
monitors and multiple patches into one clear interface.

StageMon can be used on its own with a `.stagemon.json` project. It can also
open the same `.stageflow` project as StageFlow, Save My Time, Dante Config
Editor and StageMark. StageFlow is free and optional; every application remains
fully usable by itself.

### Main features

- Up to 256 inputs and two independent stereo monitors.
- Exclusive or additive cue selection.
- Persistent sources that remain audible while patches change.
- Previous, next, clear A, clear B and global clear controls.
- Per-monitor level, mute, stereo routing and mono fold-down.
- Instant patch changes without restarting the audio engine.
- ASIO, WASAPI and WDM input/output choices.
- Simulation, oscillators and looping music for preparation.
- Local phone/tablet remote control through a QR code, with no cloud account.
- Standalone projects and safe shared `.stageflow` projects.
- StageFlow LIVE following that can be switched off at any time.
- StageFlow V3 Excel workbook creation and import with a configurable number
  of groups.
- Light/dark theme, FR/EN language selector and built-in help.

### Typical workflow

Open or create a project, select the input interface and four monitor outputs,
choose the current patch, then send one or more sources to Monitor A or B. Keep
essential feeds active with the persistent-source options and use the local QR
remote when you need to move away from the computer.

When StageFlow is present, its central console can open StageMon on the current
project, show whether it is connected, expose the cue shortcuts and include the
full StageMon remote in the unified QR portal.

### Price and installation

StageMon is available as a **€49 VAT-included perpetual licence** with a 30-day
trial. Online and offline activation are supported.

Download `StageMon-2026.3-Setup.exe` from the
[latest release](https://github.com/Mamat79/StageMon/releases/latest), close any
running StageMon instance, install it, then open **StageMon v2026** from the
desktop shortcut. Start in Simulation mode before qualifying your real audio
interface, drivers, channels, sample rate, latency and levels.

---

© 2026 SiLeMIO — By Mamat----[]---. Proprietary software.
