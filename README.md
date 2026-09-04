<p align="center">
  <img src="stagemon-icon.png" width="112" alt="Icône StageMon">
</p>

<h1 align="center">StageMon</h1>

<p align="center">
  <strong>Deux à six écoutes, des snapshots CUE, un contrôle clair pour le line-check et les changements de plateau.</strong><br>
  Hors ligne · Français / English · Windows
</p>

<p align="center">
  <a href="https://github.com/Mamat79/StageMon/releases/download/v2027/StageMon-2027-Setup.exe"><strong>⬇ Télécharger StageMon 2027 · Windows x64</strong></a>
</p>

Version actuelle : **2027**, binaire **2027.0.0.0**.
[Nouveautés FR/EN](RELEASE-NOTES-2027.md) ·
[Guide PDF français](guides/Guide-Suite-SiLeMIO-FR.pdf) ·
[English PDF guide](guides/SiLeMIO-Suite-Guide-EN.pdf).

<p align="center">
  <a href="https://github.com/Mamat79/StageMon/releases/download/v2026.3/stagemon-presentation-fr.mp4"><img src="https://github.com/Mamat79/StageMon/releases/download/v2026.3/stagemon-presentation-fr-poster.png" width="820" alt="Présentation vidéo StageMon"></a><br>
  <a href="https://github.com/Mamat79/StageMon/releases/download/v2026.3/stagemon-presentation-fr.mp4">Présentation · FR</a>
  · <a href="https://github.com/Mamat79/StageMon/releases/download/v2026.3/stagemon-presentation-fr.vtt">Sous-titres FR</a>
  · <a href="https://github.com/Mamat79/StageMon/releases/download/v2026.3/stagemon-presentation-en.mp4">Presentation · EN</a>
  · <a href="https://github.com/Mamat79/StageMon/releases/download/v2026.3/stagemon-presentation-en.vtt">EN captions</a>
</p>

La vidéo présente la version 2026.3 ; les nouveautés 2027 sont décrites ci-dessous.

---

## StageMon, à quoi ça sert ?

StageMon est une matrice d’écoute conçue pour les techniciens son, les équipes
de plateau et les régies qui doivent vérifier rapidement de nombreuses sources.
Il regroupe jusqu’à 256 entrées, deux écoutes indépendantes par défaut et jusqu'à
six en option, avec plusieurs patchs dans une interface lisible, utilisable sur
un seul ordinateur Windows.

L’objectif est simple : **retrouver immédiatement la bonne source dans la bonne
écoute, sans reconstruire la matrice à chaque changement de groupe ou de
plateau**.

StageMon fonctionne seul. Il peut également ouvrir un projet commun
`.stageflow`. La suite suit cet ordre de référence : StageFlow,
[StageDesk](https://github.com/Mamat79/StageDesk), StageMark, StageMon,
Dante Config Editor et AutoCAD. Chaque logiciel reste autonome : StageFlow est
gratuit et facultatif.

## Un exemple concret

Vous devez enchaîner les balances de cinq groupes avec 64 sources de plateau et
deux postes d’écoute :

1. créez un projet StageMon ou ouvrez le projet `.stageflow` de la production ;
2. choisissez l’interface d’entrée et les sorties mono ou stéréo des deux écoutes ;
3. retrouvez les noms de sources, micros et commentaires préparés dans le patch ;
4. sélectionnez un patch ou un groupe sans arrêter le moteur audio ;
5. envoyez une ou plusieurs sources vers l’écoute A, l’écoute B, ou les deux ;
6. conservez les sources indispensables avec les options **Toujours A** et
   **Toujours B** ;
7. utilisez Clear Cue, passez à la source suivante ou rappelez un snapshot CUE en un clic ;
8. si nécessaire, ouvrez la télécommande locale sur un téléphone avec le QR code.

Le technicien garde une vision directe de ce qu’il écoute et peut changer de
groupe sans perdre ses réglages de sécurité.

## Deux écoutes par défaut, jusqu'à six à la demande

- Jusqu’à 256 entrées.
- Monitor A et Monitor B par défaut, mono ou stéréo.
- Circuits C à F optionnels dans **Patch sorties → Nombre de circuits monitoring**.
  Ils restent invisibles tant qu'ils ne sont pas ajoutés et n'ont aucune sortie
  physique affectée automatiquement.
- Noms et couleurs propres à chaque circuit.
- Plusieurs sources simultanées par écoute.
- Mode exclusif pour écouter une seule cue à la fois.
- Mode additif pour construire une écoute avec plusieurs sources.
- Sources permanentes qui restent audibles pendant les changements.
- Niveau et mute propres à chaque Monitor.
- Repli mono indépendant si une seule sortie physique est disponible.
- Affectation libre des sorties physiques de chaque circuit configuré.
- LINK A/B facilement activable ; un second clic sur la même CUE la coupe.

Les mutes locaux restent prioritaires : une commande distante ne peut pas
réactiver une écoute coupée volontairement sur le poste.

## Changer de patch sans perdre le fil

Chaque patch peut représenter un groupe, une scène, une zone ou un état de la
production. StageMon affiche le numéro de patch, la source, le micro et les
notes utiles, puis remplace immédiatement la liste active sans redémarrer le
moteur audio.

Vous pouvez créer et enregistrer ces patchs dans un projet StageMon autonome,
les importer depuis le classeur Excel StageFlow V3 ou les lire depuis un projet
commun `.stageflow`.

## Mémoriser et rappeler des snapshots CUE

Préparez les CUE sur A, B et les autres circuits configurés, puis cliquez sur
**+ SNAPSHOT** au-dessus de la matrice. Donnez-lui un nom : un bouton numéroté
apparaît et rappelle cette scène en un clic. Le clic droit permet de renommer,
remplacer avec les CUE actuelles ou supprimer, avec confirmation avant remplacement
ou suppression. Jusqu'à 128 snapshots peuvent être conservés dans un projet.

Les snapshots gardent le patch actif, les CUE, les sources Toujours, le mode
exclusif/additif et LINK A/B. Ils ne rappellent jamais les volumes, les mutes,
les pilotes ou les sorties physiques et ne démarrent pas l'audio. Si un patch,
une source ou un circuit manque, le rappel est refusé sans changement partiel.

**Enregistrez le projet StageMon ou StageFlow local pour conserver les snapshots
sur disque.** Le classeur Excel de patch n'est pas modifié. La gestion et le
rappel des snapshots se trouvent dans l'application Windows ; aucune commande
de snapshot mobile, OSC ou Stream Deck n'est annoncée dans cette édition.

## Tester avant de raccorder le plateau

Configurez le projet à l'arrêt, sans envoyer de son. **Outils → Test des entrées**
donne accès aux oscillateurs et à une musique de votre choix, pour vérifier le
chemin d'écoute avant d'utiliser les entrées réelles. Le choix d'un test ne
démarre pas l'audio ; un témoin TEST reste visible. Les panneaux de test ne
restent pas en permanence sous les monitors.

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

StageMon distingue trois parcours :

- **Projet StageMon**, avec son propre fichier `.stagemon.json` ;
- **Projet StageFlow local**, avec un dossier `.stageflow` accessible sur ce PC,
  même lorsque l’application StageFlow n’est pas lancée ;
- **Session StageFlow LIVE**, rejointe explicitement sur le réseau local avec
  le code à six chiffres affiché par StageFlow.

Dans un Projet StageFlow local ou une Session StageFlow LIVE, StageMon ne
modifie que sa partie. Les données des autres logiciels sont conservées. Le
point d’état commun indique en texte et en couleur si StageMon est autonome,
si une session est disponible, s’il est connecté et synchronisé, ou si la
connexion est perdue. Vous pouvez quitter le LIVE à tout moment et continuer
en mode autonome.

Les alertes de labels StageFlow sont reçues par défaut lorsqu’elles sont
activées par le maître. Elles restent visibles avec compteur, texte, heure et
origine jusqu’à acquittement. Un interrupteur local permet de les couper dans
StageMon seulement, sans créer de backlog ni gêner les autres postes.

Depuis la console centrale StageFlow, il est possible d’ouvrir StageMon sur le
projet courant, de voir son état de connexion, d’utiliser les raccourcis de cue
et de retrouver sa télécommande dans le QR code unifié.

## Un classeur Excel commun

StageMon peut créer ou importer le classeur Excel StageFlow V3. Vous choisissez
le nombre de groupes et obtenez une feuille par groupe, ainsi qu’une feuille
commune. Le même classeur peut ensuite être ouvert dans StageFlow ou
StageDesk : il n’est donc pas nécessaire de commencer le projet dans un logiciel
précis.

## Interface de la suite SiLeMIO

StageMon reprend les repères visuels communs à StageFlow, StageDesk, StageMark,
StageMon, Dante Config Editor et AutoCAD :

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

1. Téléchargez `StageMon-2027-Setup.exe` et son fichier `.sha256` depuis la
   [dernière release](https://github.com/Mamat79/StageMon/releases/latest).
2. Fermez une éventuelle ancienne instance de StageMon.
3. Lancez l’installeur et conservez les options proposées.
4. Ouvrez **StageMon v2027** depuis le raccourci du Bureau.
5. Configurez vos pilotes et sorties à l'arrêt, puis démarrez volontairement l'audio.

Windows 10/11 x64 est requis. Avant une exploitation critique, vérifiez avec le
matériel réel les drivers, les canaux physiques, la fréquence d’échantillonnage,
la latence et les niveaux.

L'installeur ne ferme pas StageMon et ne lance pas l'audio. Le nouveau raccourci
est vérifié avant le retrait des anciens raccourcis StageMon reconnus. Les projets,
réglages et licences existants sont préservés. Les anciennes releases restent
disponibles pour retour arrière ; macOS n'est pas livré comme application commerciale.

---

<a id="english"></a>

## English

**StageMon** is a Windows monitoring matrix for line checks, stage changes and
fast source verification. It brings up to 256 inputs, two independent monitors
by default, optionally up to six, and multiple patches into one clear interface.

StageMon distinguishes three paths: a native **StageMon project**, a **Local
StageFlow project** stored in a `.stageflow` folder available on this PC, and an
explicitly joined **StageFlow LIVE session** on the local network. The suite
reference order is StageFlow,
[StageDesk](https://github.com/Mamat79/StageDesk), StageMark, StageMon,
Dante Config Editor and AutoCAD. StageFlow is free and optional; every
application remains fully usable by itself.

### Main features

- Up to 256 inputs; A/B by default, optionally C–F in Output patch, each mono or stereo.
- Unconfigured circuits remain hidden; new circuits start without physical output assignments.
- Named and coloured circuits, A/B LINK and click-again-to-stop CUE buttons.
- Exclusive or additive cue selection.
- Persistent sources that remain audible while patches change.
- Previous, next, clear A, clear B and global clear controls.
- Per-monitor level, mute, stereo routing and mono fold-down.
- Instant patch changes without restarting the audio engine.
- ASIO, WASAPI and WDM input/output choices.
- On-demand oscillators and looping music in Tools, with a discreet TEST indicator.
- Local phone/tablet remote control through a QR code, with no cloud account.
- Native StageMon projects and safe Local StageFlow projects.
- Explicit StageFlow LIVE sessions with a six-digit pairing code and a clean
  return to standalone mode.
- Label alerts enabled by default when requested by StageFlow, with persistent
  local details, acknowledgement and a workstation-only silent switch.
- StageFlow V3 Excel workbook creation and import with a configurable number
  of groups.
- Light/dark theme, FR/EN language selector and built-in help.

### CUE snapshots

Build your CUE selections across all configured circuits, click **+ SNAPSHOT**
above the matrix, and give the scene a name. Click its numbered button to recall
it; right-click to rename, replace from the current CUEs or delete. Replacement
and deletion require confirmation. Up to 128 snapshots are stored per project.

Snapshots remember the active patch, CUE/Always selections, exclusive/additive
mode and LINK. They never recall levels, mutes, devices or physical outputs and
do not start audio. Missing sources, circuits or patches cause a safe, whole-recall
refusal. **Save the native StageMon or local StageFlow project to keep snapshots
on disk.** No Excel patch is changed. Snapshot management is in the Windows app;
no mobile, OSC or Stream Deck snapshot commands are advertised in this edition.

### Typical workflow

Open or create a project, select the input interface and mono/stereo monitor outputs,
choose the current patch, then send one or more sources to Monitor A or B. Keep
essential feeds active with the persistent-source options and use the local QR
remote when you need to move away from the computer.

When StageFlow is present, its central console can open StageMon on the current
project, show whether it is connected, expose the cue shortcuts and include the
full StageMon remote in the unified QR portal.

### Price and installation

StageMon is available as a **€49 VAT-included perpetual licence** with a 30-day
trial. Online and offline activation are supported.

Download `StageMon-2027-Setup.exe` from the
[latest release](https://github.com/Mamat79/StageMon/releases/latest), close any
running StageMon instance, install it, then open **StageMon v2027** from the
desktop shortcut. Configure the application while stopped, then qualify your real
audio interface, drivers, channels, sample rate, latency and levels outside production.
Software tests are not hardware or physical-phone validation. No commercial Mac
application is shipped. Existing projects, settings and licensing are preserved.

---

© 2026 SiLeMIO — By Mamat----[]---. Proprietary software.
