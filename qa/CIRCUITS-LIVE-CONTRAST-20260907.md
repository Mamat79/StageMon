# StageMon — circuits, autorité LIVE et contraste (candidate locale)

État au 7 septembre 2026. Branche `codex/circuits-live-20260907`, base main
`285839beeab78a9f10d224b9678602998c6fc9ff`. Aucun changement de version,
publication, installation, site ou pipeline Mac dans ce lot. Aucun projet,
profil ou licence utilisateur modifié ; aucun moteur audio démarré.

## Résultats fonctionnels

- **Reproduit et corrigé** : un suivi StageFlow LIVE local avait une annonce
  `Live=true` et un voyant connecté, mais un texte « PROJET STAGEFLOW LOCAL ·
  AUTONOME ». Le texte ne tenait compte que du client réseau.
- Les annonces, le voyant, le texte et la disponibilité des alertes utilisent
  maintenant le même contrôle de projet, de session demandée et de bail valide.
  Un simple libellé réseau `Connected` ne suffit plus. Le follower refuse une
  autre session que le GUID demandé et revérifie cette portée après lecture.
- **Corrigé** : une actualisation de snapshot réseau remettait `_projectDirty`
  à faux, y compris après une modification locale du nombre de circuits.
  Seule l'adoption initiale remet désormais cet indicateur à zéro.
- Les boutons du centre de connexion reconnaissent aussi le suivi local pour
  les actions d'association et l'acquittement des alertes.
- La configuration reste **2 à 6 circuits A–F**. Sept n'est pas une option.
  Une valeur hors plage donne une raison explicite. Pendant le traitement
  audio, le sélecteur est désactivé et le texte demande d'arrêter l'audio.
- **Non reproduit / non déclaré résolu** : compteur bloqué à deux circuits.
  La liaison WPF TwoWay accepte 3, 4, 5, 6 puis 2 en natif, projet local et
  suivi LIVE local. Réouvrir le même projet par `suite.project.open` conserve
  les six circuits et l'indicateur de modifications. La reproduction native
  du parcours utilisateur reste nécessaire.

Tests ciblés : **98 PASS** (`--circuits-live-check`, fixture `final-r1`) :
comptage, dimensions A–F, rejet de 7, verrou audio simulé par un marqueur sans
traitement, pause/reprise LIVE, autre session refusée, bail réseau expiré et
autre projet non connectés, sauvegarde native et export partagé, réouverture
native, mono/couleur/CUE/TOUJOURS conservés. Le cas réseau utilise une portée
synthétique et la vraie adoption de snapshots, avec un handler interdisant les
requêtes à un hôte : **ce n'est pas une recette de connexion réseau réelle**.

Autres recettes : Infrastructure **203/203** (dont 22 tests LIVE), Core
**43/43**, centre de connexion **218 assertions**, suite header **932
assertions** FR/EN clair/sombre et cinq largeurs. La recette ViewModel générale
(CUE A–F, snapshots, automatisation HTTP locale) passe aussi. Les échanges HTTP
de ces bancs restent sur boucle locale isolée ; aucun audio envoyé.

## Contraste : corrections et méthode

Les couleurs de circuits, vumètres et données utilisateur restent inchangées.
Les couleurs de **texte** d'accent, d'avertissement et d'erreur sont séparées
des couleurs de remplissage. Correction du texte du mode d'entrée sélectionné
(style TextBlock global qui masquait le premier plan du RadioButton), des
infobulles et du bandeau dépliable héritant de fonds système clairs, des
boutons d'action et textes secondaires clairs. Les boutons conservent leur
paire fond/texte au survol ; les états désactivés utilisent une paire opaque
lisible au lieu d'empiler des transparences.

`--contrast-check` charge les vrais styles XAML, conserve les contrôles dans
leur arbre logique Window **sans Show ni HWND**, puis fait Dark → Light → Dark
sur les mêmes instances. FR/EN, fenêtre principale à 1360×820, dialogues à
640×640. Mesure des TextBlock disposés et de leur plus proche fond opaque
peint, excluant le fond de puce des CheckBox/RadioButton. Rapport de revue
conservateur à 4,5:1, même pour les grands titres ; ce n'est ni une mesure de
chaque pixel anticrénelé ni une certification WCAG de toute l'application.

Le premier banc valide (`contrast-baseline-r3`) relevait 110 échantillons sous
4,5. Le dernier (`contrast-final-r2`) contient **1506 échantillons uniques, zéro
texte activé relevé sous 4,5 sur ce périmètre**.

Les états désactivés font l'objet d'un résultat séparé : **20 textes désactivés
relevés, zéro sous 4,5, minimum 4,645:1 en clair et 6,405:1 en sombre**. Sont
inclus les boutons Rejoindre, Se déconnecter et Tout acquitter du centre ainsi
que les bouton et sélection désactivés de la galerie. Cela ne couvre pas toutes
les commandes désactivables de chaque écran.

Un `TextBox` en lecture seule ne rend pas son contenu avec un `TextBlock` et
n'entre donc pas dans les 1506 échantillons. La galerie emploie néanmoins le
vrai style partagé : même paire opaque `InputTextBrush` / `InputBrush` que le
champ éditable, sans réduction d'opacité. Les rendus `controls-Light.png` et
`controls-Dark.png` ont été examinés et les deux textes sont lisibles. Cela ne
constitue pas une recette de toutes les cellules de grille en édition ou lecture
seule.

Les versions r1/r2 de la baseline étaient des essais
de harnais (ToolTip non parentable et invalidation de ressources sur arbre
détaché) : ne pas les citer comme défauts du produit.

## Matrice de couverture

| Surface / état | Sombre | Clair | Preuve et limite |
| --- | --- | --- | --- |
| Matrice, patch sorties, diagnostics, aide ; textes disposés | Vérifié hors écran | Vérifié hors écran | FR/EN, vrais onglets ; 1360×820 ; le compteur réel est lié au modèle |
| En-tête, langue, navigation, centre | Vérifié hors écran | Vérifié hors écran | Bancs existants 932/218 ; cinq largeurs pour l'en-tête, deux tailles pour le centre |
| Tests des entrées, mode sélectionné | Défaut corrigé | Défaut corrigé | Rendus `input-tests-*.png` examinés ; aucun test sonore lancé |
| Nouveau projet, modèle Excel, nom de snapshot, choix non enregistré | Vérifié hors écran | Vérifié hors écran | Texte/fond FR/EN ; actions d'écriture des dialogues non exécutées |
| Champ éditable et champ `TextBox` en lecture seule | Rendu examiné | Rendu examiné | Même paire opaque du style partagé ; hors des 1506 TextBlock ; pas de saisie clavier/focus HWND |
| Boutons désactivés du centre et galerie | 8 textes, min. 6,405:1 | 8 textes, min. 4,645:1 | Zéro sous 4,5 ; ne couvre pas toutes les commandes désactivables |
| Sélection ComboBox désactivée de la galerie | 2 textes, 15,299:1 | 2 textes, 16,383:1 | Popup fermé ; les éléments ouverts restent à vérifier en GUI |
| ComboBoxItem sélectionné hors popup | Vérifié hors écran | Vérifié hors écran | Vrai style, mais pas dans une liste déroulante native ouverte |
| Infobulle simple et détail dépliable | Défaut corrigé | Défaut corrigé | Styles et disposition hors écran ; ouverture native / clavier à vérifier |
| Bandeau d'alertes LIVE | Rendu examiné | Rendu généré | `--render-alerts`, portée synthétique valide ; 2 PNG ; pas d'acquittement distant |
| Menus/contextuels et listes déroulantes ouvertes | Vérifié sur fixture GUI isolée | Non couvert en GUI | Le popup réel du nombre de circuits n'affiche que 2 à 6 ; le menu Thème sombre est lisible |
| Survol et focus clavier réels | Partiel | Non couvert en GUI | Le focus natif a été observé, mais pas une traversée clavier complète ; le survol n'a pas été exercé de manière fiable |
| Grille en édition, erreurs de validation, toutes les combinaisons de sélection | Non couvert intégralement | Non couvert intégralement | Aucun succès global extrapolé depuis la matrice en lecture seule |
| Licence, contrôles externes, HF/RF et boîtes système fichier/message | Non couvert dans ce lot | Non couvert dans ce lot | Rôles de texte partagés mis à jour ; ne vaut pas recette de ces fenêtres |
| Télécommande web et navigateur du téléphone | Non couvert dans ce lot | Non couvert dans ce lot | Les tests de scope/HTTP ne constituent pas une recette visuelle web |
| macOS | Non couvert | Non couvert | Aucun build ou lancement Mac autorisé dans ce lot |

## Preuves et reprise

Preuves locales sous `artifacts/circuits-live-20260907/` :

- `final-r1/` : projets synthétiques natifs et `.stageflow` des 98 checks.
- `contrast-final-r2/samples.json` et `review.json` : relevés de couleurs, thèmes,
  langues, textes, surfaces et état activé. Six rendus PNG du produit/galerie.
- `alerts-final/` : deux rendus du bandeau d'alertes.

Commandes depuis la racine du dépôt (choisir des dossiers de sortie neufs) :

```powershell
dotnet run --project tools/StageMon.ViewModelConformance -c Release -- --circuits-live-check artifacts/circuits-live-20260907/recheck-new
dotnet run --project tools/StageMon.ViewModelConformance -c Release -- --contrast-check artifacts/circuits-live-20260907/contrast-new
dotnet run --project tools/StageMon.ViewModelConformance -c Release -- --connections-check
dotnet test tests/StageMonitoring.Infrastructure.Tests -c Release --no-restore
dotnet test tests/StageMonitoring.Core.Tests -c Release --no-restore
```

## Recette GUI native isolée

Après le GO explicite de Control général
(`01a060ec-01c9-7371-8422-fe98007795af`), la fixture
`--interactive-fixture` a détaché le contenu de `MainWindow` avant son événement
`Loaded`. Elle n'a donc démarré ni licence, ni console de suite, ni serveur QR,
ni moteur audio et n'a ouvert aucun projet utilisateur.

Dans la vraie fenêtre Windows :

- le popup du nombre de circuits ne proposait que **2, 3, 4, 5 et 6** ;
- la séquence visible **2 → 3 → 4 → 5 → 6 → 2** a bien reconstruit la page
  Patch sorties et son résumé A–F ;
- le popup et le menu Thème en sombre étaient lisibles ;
- la recette clair GUI, le survol complet et la traversée clavier exhaustive
  n'ont pas été poursuivis après reprise d'activité utilisateur sur l'écran.

Cette observation ne reproduit pas le blocage intermittent à deux et ne permet
donc pas de le déclarer corrigé. Les transitions local/LIVE restent couvertes
par le banc synthétique, pas par une session distante réelle. La fixture a été
fermée et le créneau GUI libéré. Ne pas publier ni installer cette candidate
dans ce lot.
