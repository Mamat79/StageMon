# Confidentialité et sécurité réseau

Stage Monitoring traite localement les noms de sources, références de micros,
sélections d’écoute, niveaux et paramètres audio.

- aucun échantillon audio n’est envoyé vers un service cloud ;
- la télécommande QR fonctionne sur le réseau local ;
- son URL contient un jeton éphémère et un seul pilote est accepté à la fois ;
- aucune règle de pare-feu n’est créée ou acceptée silencieusement ;
- l’adaptateur StageFlow LIVE lit uniquement le projet et le bail local ;
- Stage Monitoring ne crée jamais le bail StageFlow LIVE ;
- la future passerelle QR unifiée StageFlow n’est pas incluse dans la version
  2026.2.

Les journaux et fichiers de session restent sur le poste de l’utilisateur.
