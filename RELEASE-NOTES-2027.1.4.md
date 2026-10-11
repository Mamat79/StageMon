# StageMon 2027.1.4 — Windows

[Français](RELEASE-NOTES-2027.1.4-FR.md) · [English](RELEASE-NOTES-2027.1.4-EN.md)


Cette maintenance passe le candidat Windows à .NET 10. Les formats de projets, niveaux, mutes, routages, snapshots, contrats StageFlow LIVE et droits de licence sont conservés. Le rappel après essai reste de cinq secondes. Audio et télécommande nécessitent toujours une activation volontaire.

L’EXE livré est le candidat 2027.1.4 compilé depuis `e7eb8431b1e06bedb4c489cc23968e20516f6687`, réutilisé octet pour octet. L’installeur a été fabriqué par la recette officielle au commit d’empaquetage `3af79540c06f3089c6c06a499cde1e57af6b5703`. Il ne s’agit pas d’un ancien EXE 1.3 renommé.

Les preuves conservées du candidat comptent 348 exécutions de tests sur cinq runs, dix groupes de scénarios Chromium et six contrôles CLI : bandeau 596, fermeture 1, connexions 218, interop réseau 68, interop locale 26 et aller-retour partagé 18. Ces contrôles n’ont pas été relancés pour le seul empaquetage. Les nouveaux contrôles vérifient la source d’empaquetage, les onze fichiers du candidat, le contenu préparé pour Inno Setup, la version, les guides approuvés, les manifestes et les SHA-256.

Publication autorisée explicitement le 11 octobre 2026 avec qualification native en attente. Le rendu de la fenêtre OS et la navigation clavier ne sont pas qualifiés ; les captures automatisées sont inconclusives et leur cause n’est pas établie. La matrice DPI complète, l’audio matériel, le réseau réel et le téléphone ne sont pas qualifiés. L’installation réelle du nouveau Setup standard, sa mise à niveau, ses raccourcis et son retour arrière n’ont pas été exercés. Les contrôles logiciels ne remplacent pas ces essais. Aucun remplacement personnel n’est effectué par cette publication.

macOS reste disponible en **2027.1.3**, dans sa release existante. Cette release 1.4 publie Windows uniquement et ne revendique aucun nouveau DMG 1.4. Le contrôle complet des avis NuGet reste à confirmer.

Les conditions commerciales sont inchangées. Consulter `QUALIFICATION-2027.1.4.md`, `release-manifest.json` et `SHA256SUMS.txt`.

---


This maintenance moves the Windows candidate to .NET 10. Project formats, levels, mutes, routing, snapshots, StageFlow LIVE contracts and licence rights are preserved. The expired-trial reminder remains five seconds. Audio and remote control still require deliberate activation.

The delivered executable is the verified 2027.1.4 candidate compiled from `e7eb8431b1e06bedb4c489cc23968e20516f6687`, reused byte for byte. The standard installer was produced by the official recipe at packaging commit `3af79540c06f3089c6c06a499cde1e57af6b5703`. No 1.3 executable was renamed.

Retained candidate evidence records 348 test executions across five runs, ten Chromium scenario groups and six CLI checks: suite header 596, shutdown 1, connections 218, remote interop 68, local interop 26 and shared round trip 18. These checks were not repeated for packaging alone. New checks verify packaging source, all eleven candidate files, the payload prepared for Inno Setup, version, approved guides, manifests and SHA-256 digests.

Published on explicit human instruction on 11 October 2026 with native qualification pending. OS-window rendering and keyboard navigation were not qualified; automated captures were inconclusive and their cause was not established. Full DPI coverage, physical audio, live networks and phones remain unqualified. Actual standard installer execution, upgrade, shortcuts and rollback were not exercised for this delivery. Software tests do not replace these checks. This publication performs no installation on the personal PC.

macOS remains available as **2027.1.3** in its existing release. This 1.4 release publishes Windows only and claims no new 1.4 DMG. Complete NuGet advisory auditing remains to be confirmed.

Commercial terms are unchanged. Read `QUALIFICATION-2027.1.4.md`, `release-manifest.json` and `SHA256SUMS.txt`.
