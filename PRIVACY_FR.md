# Politique de confidentialité de sName2Date

Mise à jour : 2026-08-22

## En bref

sName2Date ne collecte, n'enregistre et ne transmet **aucune** donnée personnelle. L'app
travaille exclusivement sur votre Mac et n'établit aucune connexion à Internet.

## Quelles données l'app traite

sName2Date lit les fichiers que vous lui confiez expressément — par sélection dans la boîte
de dialogue d'ouverture ou en les faisant glisser sur la fenêtre. Sont lus le nom du fichier
et les métadonnées du fichier ; est écrite la date de prise de vue dans ces fichiers
précisément.

Sur demande, l'app renomme en outre ces fichiers et définit leur date de création et de
modification. Ces deux options sont désactivées par défaut et doivent être activées
expressément.

Dans le mode **Noms de fichiers**, l'app n'ouvre **aucun fichier** : elle lit uniquement le
nom et modifie uniquement le nom. Le contenu n'est alors ni lu ni écrit.

Sans votre sélection, l'app n'accède à aucun fichier. macOS l'impose au moyen du bac à sable
(App Sandbox).

## Ce que l'app dépose sur votre Mac

- **Les réglages** dans un fichier `config.json` situé dans le dossier protégé de l'app.
- **Un journal de diagnostic** au même endroit, supprimé automatiquement au bout de sept
  jours. Il contient des horodatages et des nombres d'opérations. Vous pouvez l'enregistrer
  et le transmettre via Réglages → Diagnostic ; sinon, il ne quitte pas votre Mac.
- **Les chemins des dossiers que vous avez autorisés**, avec l'autorisation de macOS de les
  rouvrir au prochain démarrage. C'est le seul moyen pour que l'app n'ait pas à redemander à
  chaque fois. Cette liste contient des chemins de dossiers, pas de contenus de fichiers, et
  le bouton « Choisir un dossier » vous la montre.

Tout cela est supprimé avec l'app lorsque vous la supprimez.

**À côté de vos fichiers, l'app ne crée rien de nouveau.** Si un fichier annexe portant
l'extension `.xmp` s'y trouve déjà — il provient alors d'un autre logiciel de photo —, sa
date de prise de vue est mise à jour elle aussi, afin que le fichier et son annexe ne disent
pas des choses différentes. Ce que l'app n'y comprend pas reste intact.

## Aucune transmission, aucune analyse

Il n'y a ni publicité, ni services d'analyse, ni rapports de plantage envoyés à des tiers, ni
comptes.

## Contact

Andreas Heiligtag · SwiftAppsBavaria@gmx.net
