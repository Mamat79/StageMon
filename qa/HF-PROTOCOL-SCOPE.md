# Télémétrie HF — StageMon 2027.0.1

Recherche sur les sources constructeur, les 4 et 5 septembre 2026. Aucun appareil de
l'utilisateur n'a été interrogé, découvert ou reconfiguré. Ne pas annoncer une
compatibilité matérielle sur la seule base des tests simulés.

## EW-DX : parcours opérateur en lecture seule sur Windows et Mac

La documentation [SSCv2 Sennheiser](https://docs.cloud.sennheiser.com/en-us/api-docs/api-docs/sound-control-protocol.html)
couvre les EW-DX EM2, EM2 Dante et EM4 Dante avec firmware à partir de 4.0.
Elle ne justifie pas de traiter un Digital 6000 comme un EW-DX.

`EwDxReadOnlyClient` suit exclusivement l'[OpenAPI EW-DX 1.7](https://docs.cloud.sennheiser.com/en-us/api-docs/api-docs/open-api-ew-dx.html)
et son [schéma constructeur](https://bgzkwm.files.cmp.optimizely.com/download/assets/EW-DX_openapi_3rdparty_release_1.7.yaml/8b56f9fee7d711f0ae307aeaa9c3764a).
Le schéma complet consulté a pour SHA-256
`9e8aa6ca92ecf7a41d4553af62b7a6b14f9b5cffe83bfb5c550f35d960665849`.
Lectures explicites : identité et version publiques, état/version du firmware,
RSSI en dBm, qualité en pourcentage, niveau audio en dBFS, batterie en
pourcentage/minutes. L'index
émetteur est explicite ; aucune correspondance avec les entrées audio n'est
inventée. Les trois modèles sont vérifiés, ainsi que protocole 2 et schéma
compatible 1.7 avant l'envoi des identifiants.

Avant les mesures, le GET documenté `/api/firmware/update/state` doit retourner
un état Idle et une version de périphérique au moins 4.0.0. Aucun déclenchement
de mise à jour n'est envoyé. L'API batterie peut retourner 422 pour un émetteur
non lié : cet état est affiché explicitement, et non comme une batterie à 0 %.

HTTPS 443, utilisateur `api`, mot de passe fourni explicitement (10 à 64
caractères), certificat vérifié normalement par le système. En option,
l'opérateur peut renseigner l'empreinte SHA-256 exacte du certificat feuille,
vérifiée séparément auprès de l'administrateur. Cette confiance ne concerne que
cette association : certificat absent, différent, expiré ou connu révoqué
refusé ; aucune acceptation globale ni désactivation TLS. Aucune persistance de mot de passe, aucun
proxy, cookie, suivi de redirection ou repli SSCv1. Limite de réponse 16 Kio et
délai de trois secondes incluant la lecture du corps, cycle total borné à dix
secondes puis pause de deux secondes. Valeur absente = inconnue,
jamais zéro fabriqué. Erreurs et valeurs hors plage restent des erreurs.

Uniquement les GET sans effet de bord ci-dessus : même le GET de création
d'abonnement SSC est volontairement exclu. Aucun constructeur, démarrage
d'application ou test n'ouvre une connexion matérielle en arrière-plan.

Selon [la configuration d'accès officielle](https://docs.cloud.sennheiser.com/en-us/control-cockpit/control-cockpit/ew-dx-access.html),
l'accès tiers doit être activé par l'opérateur. StageMon ne l'active pas.
`Outils → HF / RF · EW-DX` sur Windows et `SETUP → HF / RF · EW-DX` sur Mac
ouvrent les vrais contrôles : adresse, mot de passe masqué, empreinte optionnelle,
annotation, RX 1–4 et TX optionnel distinct. Rien ne se connecte avant
« Associer et lire ». Seize associations au maximum dans la fenêtre ; aucune
découverte automatique ni déduction du TX depuis l'entrée audio. L'interface
FR/EN montre modèle, firmware, protocole, mesures, unités, horodatage et état.
Déconnecter, retirer ou fermer annule les lectures et efface les mesures. Une
réponse tardive ne peut pas restaurer les mesures après déconnexion. Une erreur
réseau, TLS, délai, accès ou format arrête le polling, invalide les mesures et
demande une nouvelle association volontaire. Les secrets ne sont ni sauvegardés
ni journalisés. Les essais sur appareils réels restent à effectuer.

## Shure et Wisycom : pas d'adaptateur supposé compatible

Le [guide ULX-D officiel](https://www.shure.com/en-US/docs/guide/ulxd-dq) documente
la commande réseau sur TCP 2202. Le [document constructeur de commandes](https://content-files.shure.com/Pubs/ulx/ulx-d-network-string-commands.pdf)
était accessible seulement par extraits indexés (lecture complète refusée, HTTP
403). Les pages officielles de commandes
[ULX-D](https://www.shure.com/en-US/docs/commandstrings/ULXD) et
[AD4](https://www.shure.com/en-US/docs/commandstrings/AD4) ont été consultées :
leur HTML et script public indiquent les documents 8338 et 7483, mais le rendu
documentaire était lui aussi refusé par l'outil. Aucune tentative de
contournement de ces refus n'a été effectuée.
Cela ne suffit pas à implémenter et valider une télémétrie RF/audio complète.
Aucune commande de mesure ni aucun comportement Axient/ULX-D partagé n'est
supposé ; aucune commande SET n'est envoyée pour activer un flux de mesures.
Il manque le document complet de chaque famille avec syntaxe GET/réponses,
unités, sentinelles d'indisponibilité, versions et cadence supportées, puis une
qualification avec récepteurs/émetteurs et firmwares identifiés. Un extrait de
moteur de recherche ou le seul port TCP ne suffit pas.

[Wisycom Manager](https://wisycom.com/product/wisycom-manager/) et son
[aide officielle complète de 17 pages](https://wisycom.com/app/uploads/Wisycom-Manager-Help.pdf)
ont été consultés. Le contrôle distant du Manager est documenté sur TCP 32789 ;
ce n'est pas le protocole télémétrique des récepteurs. L'aide documente aussi
l'activation Ember+ (port par défaut 9000), notamment pour MRK980, et un
fournisseur autonome MRK980. Les
[notes de firmware MRK980](https://wisycom.com/product/mrk980/) situent
l'introduction Ember+ en 2.6. Cela ne fournit pas l'arbre de paramètres.
Il manque l'arbre Ember+ officiel par modèle/firmware (ou un SDK officiel), les
types, unités, accès lecture seule et valeurs d'indisponibilité, ainsi que les
conditions de rafraîchissement. Une capture de cet arbre autorisée et le matériel
correspondant permettraient ensuite de vérifier la spécification ; aucune
correspondance de nœuds ni commande de contrôle n'est inventée dans StageMon.

## Preuves et limites

Tests du véritable lecteur EW-DX avec transport HTTP synthétique : requêtes GET
exactes, unités, identité/version incompatibles avant authentification, absence
de valeurs, limites de canaux/réponses, erreurs HTTP et refus d'origine HTTP.
Ils n'utilisent que `receiver.invalid` et n'ouvrent aucun socket. Des contrôles
supplémentaires exercent les vrais panneaux Windows et Mac avec un transport
synthétique : association volontaire, effacement du mot de passe, mesure rendue,
absence d'inférence TX et arrêt sur fermeture. Le détail de la recette courante
est séparé des validations matérielles. Aucun essai logiciel ne certifie la
compatibilité avec le matériel d'un utilisateur. Licence commerciale inchangée.
