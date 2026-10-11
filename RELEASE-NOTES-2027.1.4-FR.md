# StageMon 2027.1.4 — Windows

Cette maintenance passe le candidat Windows à .NET 10. Les formats de projets, niveaux, mutes, routages, snapshots, contrats StageFlow LIVE et droits de licence sont conservés. Le rappel après essai reste de cinq secondes. Audio et télécommande nécessitent toujours une activation volontaire.

L’EXE livré est le candidat 2027.1.4 compilé depuis `e7eb8431b1e06bedb4c489cc23968e20516f6687`, réutilisé octet pour octet. L’installeur a été fabriqué par la recette officielle au commit d’empaquetage `3af79540c06f3089c6c06a499cde1e57af6b5703`. Il ne s’agit pas d’un ancien EXE 1.3 renommé.

Les preuves conservées du candidat comptent 348 exécutions de tests sur cinq runs, dix groupes de scénarios Chromium et six contrôles CLI : bandeau 596, fermeture 1, connexions 218, interop réseau 68, interop locale 26 et aller-retour partagé 18. Ces contrôles n’ont pas été relancés pour le seul empaquetage. Les nouveaux contrôles vérifient la source d’empaquetage, les onze fichiers du candidat, le contenu préparé pour Inno Setup, la version, les guides approuvés, les manifestes et les SHA-256.

Publication autorisée explicitement le 11 octobre 2026 avec qualification native en attente. Le rendu de la fenêtre OS et la navigation clavier ne sont pas qualifiés ; les captures automatisées sont inconclusives et leur cause n’est pas établie. La matrice DPI complète, l’audio matériel, le réseau réel et le téléphone ne sont pas qualifiés. L’installation réelle du nouveau Setup standard, sa mise à niveau, ses raccourcis et son retour arrière n’ont pas été exercés. Les contrôles logiciels ne remplacent pas ces essais. Aucun remplacement personnel n’est effectué par cette publication.

macOS reste disponible en **2027.1.3**, dans sa release existante. Cette release 1.4 publie Windows uniquement et ne revendique aucun nouveau DMG 1.4. Le contrôle complet des avis NuGet reste à confirmer.

Les conditions commerciales sont inchangées. Consulter `QUALIFICATION-2027.1.4.md`, `release-manifest.json` et `SHA256SUMS.txt`.
