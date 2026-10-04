# StageMon 2027.1.3

## Français

Essai complet de 30 jours inchangé. Après l'essai, un décompte de 5 secondes
remplace les 60 secondes au démarrage, une seule fois par processus. Toutes les
fonctions restent disponibles après le décompte, sans blocage définitif.
Une licence valide supprime rappel et attente et garde ses droits hors ligne.
L'activation, les signatures, tarifs et formats ne changent pas. L'essai et
l'activation enregistrée ne sont pas réinitialisés par la mise à jour.

Les écrans et notices FR/EN sont actualisés. Les anciennes notes restent
historiques. Les circuits physiques, l'écoute téléphone et LIVE sont préservés,
sans démarrage audio automatique. Voir RELEASE-NOTES-2027.1.3-FR.md.

## English

The full 30-day trial remains unchanged. Afterwards, a 5-second countdown
replaces the 60-second startup wait, only once per process. All features remain
available after the countdown, without a permanent lock. A valid license
removes the reminder and wait and retains its offline rights. Activation,
signatures, pricing and license formats are unchanged. Updating does not reset
the trial or saved activation.

License screens and FR/EN notices are updated. Older notes remain historical.
Physical circuits, phone listening and LIVE are preserved, without automatic
audio startup. See RELEASE-NOTES-2027.1.3-EN.md.

## Qualification limits

Windows: 356 tests and 83 isolated license-screen assertions passed, without a
visible native window in this pass. Mac packages passed Codemagic CI tests;
Apple Silicon launched and closed from the mounted DMG with a Keychain roundtrip.
Intel was cross-built on M2 and its architecture checked, not executed natively.

No physical audio, real-phone or show-network acceptance, no Codemagic visual
desktop acceptance and no dedicated native Mac expired-license countdown test
are claimed. Native-results JSON was not retained by the workflow: the success
log and inspected smoke script are the available evidence. Packages are ad-hoc
signed, without Developer ID or Apple notarization. See the separate FR/EN
QUALIFICATION-2027.1.3 notices for the exact validation scope.
