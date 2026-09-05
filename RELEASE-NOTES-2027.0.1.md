# StageMon 2027.0.1 — Windows et macOS

Correctif de la génération v2027. Le raccourci Windows conserve le nom
`StageMon v2027`. Source privée, distribution publique sans code source.

## Circuits sur Mac

SETUP propose un éditeur réel du nom, de la couleur et du plafond de chaque
circuit. A/B restent les seuls circuits par défaut ; C–F apparaissent seulement
si ajoutés. Une vue individuelle conserve la lettre et la sélection du circuit
concerné. La vue générale ne modifie pas les CUE.

Abaisser le plafond réduit le niveau à la valeur autorisée. Le relever ne monte
pas le niveau. Le mute local, le mute distant, les CUE/Toujours et le patch mono
ou stéréo sont préservés. Les plafonds s'appliquent aussi à la Remote. Noms,
couleurs et plafonds sont conservés dans les projets StageMon et StageFlow.

## Remote et liens StageFlow

Les commandes web attendent leur application réelle. Un changement de projet,
de patch ou de circuits invalide les anciennes commandes en attente. Un même
identifiant ne peut pas répéter une action ; aucun rejeu automatique n'est
effectué après perte de connexion. Les refus sont lisibles en FR/EN, et les
contrôles deviennent indisponibles hors connexion. Le niveau affiché suit les
réglages du poste, même lorsque le curseur a encore le focus clavier.

Une télécommande active conserve son accès par ses échanges autorisés ; cela
ne prolonge jamais une session LIVE révoquée. Les commandes globales StageFlow
revalident identité, bail et délai au moment de l'application. Un projet LIVE
réseau est annoncé sans chemin de fichier local et avec son marqueur explicite.

StageMon attend que sa connexion locale soit prête avant de se déclarer
disponible à StageFlow. La connexion suivante est préparée avant de confirmer
la commande courante, y compris si le client se déconnecte. Un échec de
démarrage ou l'arrêt du serveur retire sa présence ; aucun délai n'est allongé
et aucune commande n'est rejouée pour masquer une connexion indisponible.

Sur Windows, OSC/MIDI ne peuvent plus retirer un mute local. Changer de projet
retire l'ancien écouteur OSC ; il faut le réactiver. Les anciens événements
MIDI en file sont refusés et Note/CC utilisent un front de pression pour les
actions bouton. Program Change reste une action par message. UDP OSC et le
matériel MIDI ne fournissent pas de garantie universelle de livraison unique.

## HF EW-DX sur Windows et Mac

Le panneau HF/RF associe explicitement un récepteur HTTPS et un RX ; le TX de
batterie est optionnel et distinct. Modèles EW-DX EM 2, EM 2 Dante et EM 4 Dante,
firmware 4.0.0 minimum, SSCv2 et schéma OpenAPI compatible 1.7 uniquement.

Les seules opérations sont les lectures documentées. RSSI, qualité, niveau
audio, batterie et autonomie utilisent les unités constructeur et un état
inconnu en l'absence de valeur. Une erreur invalide les mesures et demande une
nouvelle association. Mot de passe non enregistré, certificat système ou
empreinte exacte vérifiée séparément, aucun repli non sécurisé.

Ce parcours est testé avec des réponses synthétiques et doit encore être
qualifié avec le matériel. Aucun adaptateur Shure ou Wisycom n'est annoncé.
Les documents et éléments manquants sont détaillés dans la note HF du dépôt.

## Documentation et plateformes

Deux PDF StageMon FR/EN dédiés accompagnent les deux guides communs SiLeMIO
approuvés et copiés sans variante locale. Windows : installeur x64 autonome.
Mac : DMG natif Apple Silicon et DMG natif Intel, CoreAudio, runtime inclus.

La signature des paquets StageMon Mac est ad hoc ; Developer ID et notarisation
ne font pas partie de cette livraison. Les cartes audio, le réseau physique et
les appareils HF demandent une recette sur site. Conservez vos projets avant
mise à jour. Les anciennes releases restent disponibles pour retour arrière.
