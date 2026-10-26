# StageMon 2027.1.7 — qualification Windows / Windows qualification

**Cette livraison concerne Windows 2027.1.7. Les paquets et notices macOS restent en 2027.1.6.** Les nouveaux paquets Mac seront publiés après leur propre qualification. Les anciennes releases sont conservées.

**This release delivers Windows 2027.1.7. macOS packages and specific manuals remain at 2027.1.6.** New Mac packages will be published after their separate qualification. Previous releases are preserved.

## Français

Produit privé `17b7c5e8dce0a063e0348c801309b70196d47f54`, recette Windows `b40e4da89a1993a523c68ca5a915f8a50b4b666b`. Construction locale par la recette officielle ; installeur x64 non signé. La correction finale porte sur deux fichiers XAML Windows : contraste des dialogues sombres, sans changement du moteur audio.

Les douze rapports CLI du candidat précédent sont explicitement réutilisés et liés à leurs sources et empreintes ; ils ne sont pas présentés comme une nouvelle exécution intégrale. Le contrôle composite ajoute vingt textes et huit rendus hors écran FR/EN clair/sombre, puis le validateur officiel complet CheckOnly réussit. Ces rendus et les contrôles de navigateur sont distincts de l'observation native.

La véritable application Windows candidate montre la disposition Direction B, les circuits A/B, les cartes et la matrice. Le menu Fichier au clavier et le dialogue sombre de modifications non enregistrées ont été observés ; Annuler conserve le projet de démonstration. Une nouvelle copie privée de ce projet a été enregistrée et analysée : deux entrées, un patch et deux circuits. L'audio, la télécommande et LIVE sont restés arrêtés. Observation à 96 DPI (100 %). La première observation bornée a expiré et reste consignée comme ATTENTION ; le même processus a ensuite été suivi séparément, puis fermé normalement avec un code de sortie 0. L'ancienne tentative du candidat précédent ne reçoit aucun code de sortie inventé ni garantie sur son état mémoire.

Avant mise à jour, deux copies privées indépendantes sur deux volumes ont été vérifiées : 65 fichiers et 321300572 octets, avec restauration d'un échantillon. Les changements de profil liés au test et la copie de démonstration sont conservés séparément. L'installeur réel a été extrait : ses 23 fichiers applicatifs comprennent les 17 fichiers figés du candidat et six documents/icône de la recette officielle, tous identiques aux entrées qualifiées. L'installation existante a été mise à jour de 2027.1.6 vers 2027.1.7 : 23 fichiers installés vérifiés, 20 fichiers personnels et 20 fichiers supplémentaires conservés, version du registre réel et raccourci unique vérifiés. Aucun second lancement natif après installation n'est revendiqué ; les octets installés sont ceux du candidat observé.

Les deux guides StageMon Windows 2027.1.6 et les guides de suite approuvés 2027.3 sont réutilisés sans régénération ; leurs captures et versions historiques restent indiquées. Les notes 2027.1.7 décrivent la nouvelle disposition et ce document précise la portée actuelle. Les paquets Mac restent en 2027.1.6 ; aucune application, notice ou qualification native Mac 2027.1.7 n'est incluse.

Limites : aucune carte audio physique, écoute téléphone, réseau entre postes, activation commerciale ni matrice exhaustive de DPI ou de commandes humaines. Aucun changement de licence, modèle, format ou règle d'essai.

## English

Private product `17b7c5e8dce0a063e0348c801309b70196d47f54`, Windows recipe `b40e4da89a1993a523c68ca5a915f8a50b4b666b`. Locally built through the official recipe; unsigned x64 Setup. The final two-XAML Windows fix improves dark-dialog contrast without changing the audio engine.

Twelve previous candidate CLI reports are explicitly source/hash-bound reused evidence, not a fresh full run. The composite adds twenty text checks and eight FR/EN light/dark offscreen renders; the full official CheckOnly validator passes. Browser and offscreen checks remain separate from native acceptance.

The real candidate showed Direction B, A/B circuits, cards and matrix. Keyboard File navigation and the dark unsaved-changes dialogue were observed; Cancel retained the demo project. A new private demo copy was saved and parsed: two inputs, one patch and two buses. Audio, remote and LIVE stayed stopped. Native observation was at 96 DPI (100%). The initial bounded observation timed out and remains ATTENTION; the same process was later separately observed and closed normally with actual exit code 0. No exit code or in-memory preservation is invented for an earlier predecessor attempt.

Two independent private backups on two volumes verified 65 files, 321300572 bytes, plus a restored sample. Test profile deltas and demo copy were separately preserved. The actual Setup contains 23 exact files: 17 frozen candidate files plus six bounded official recipe documents/icon. The existing 2027.1.6 installation was upgraded to 2027.1.7; installed files, actual registry and unique desktop shortcut passed, while 20 personal files and 20 extra non-product files remained unchanged. There was no second installed native launch; installed bytes equal the observed candidate.

The unchanged Windows 2027.1.6 StageMon guides and approved 2027.3 suite guides retain their historical context. Release notes describe the new layout. Mac stays at 2027.1.6; no Mac 2027.1.7 application, specific manual or native qualification is included. No physical audio/phone/cross-machine networking, commercial activation or exhaustive DPI/human-command acceptance. Licensing, trial, formats and model data are unchanged.
