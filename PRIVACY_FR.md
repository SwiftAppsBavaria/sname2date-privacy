# Politique de confidentialité de sName2Date

Mise à jour : 2026-09-24

## En bref

sName2Date ne collecte, n'enregistre et ne transmet **aucune** donnée personnelle. L'app
travaille exclusivement sur votre Mac et n'établit aucune connexion à Internet.

## Quelles données l'app traite

sName2Date lit les fichiers que vous lui confiez expressément — par sélection dans la boîte
de dialogue d'ouverture ou en les faisant glisser sur la fenêtre. Sont lus le nom du fichier
et les métadonnées du fichier ; est écrite la date de prise de vue dans ces fichiers
précisément.

Sur demande, l'app renomme en outre ces fichiers (option désactivée par défaut). Elle
définit aussi leur date de création et de modification (option activée par défaut,
désactivable dans les Réglages). Pour les fichiers qui ne peuvent pas contenir de date de
prise de vue — par exemple PDF ou texte —, elle définit à la place toujours uniquement ces
deux dates.

Si la case **Écrire la date dans le fichier** est décochée, l'app n'ouvre
**aucun fichier** : elle lit uniquement le nom et modifie uniquement le nom et, si c'est
réglé, la date de création et de modification. Le contenu n'est alors ni lu ni écrit.

Sans votre sélection, l'app n'accède à aucun fichier. macOS l'impose au moyen du bac à sable
(App Sandbox).

Lorsque l'app parcourt un dossier dans lequel se trouve le dossier « Musique », macOS peut
demander si elle peut accéder à « Médias et Apple Music ». L'app ne lit ni votre
bibliothèque ni votre historique d'écoute. Là comme partout, elle travaille uniquement avec
des fichiers et écrit la date dans les fichiers audio et vidéo dont le nom en porte une.

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

**À côté de vos fichiers, l'app ne crée quelque chose que dans un seul cas :** si un fichier
photo, vidéo ou audio ne peut pas contenir lui-même la date de prise de vue (par exemple
HEIF, WebP ou AVI), l'app l'écrit dans un fichier annexe portant le même nom et l'extension
`.xmp`, que de nombreux logiciels de photo lisent aussi. ⌘Z l'annule. À côté d'autres
fichiers, par exemple PDF ou texte, il n'en est jamais créé. Si un fichier annexe s'y trouve
déjà — il provient alors d'un autre logiciel de photo —, sa date de prise de vue est mise à
jour elle aussi, afin que le fichier et son annexe ne disent pas des choses différentes. Ce
que l'app n'y comprend pas reste intact.

## Aucune transmission, aucune analyse

Il n'y a ni publicité, ni services d'analyse, ni rapports de plantage envoyés à des tiers, ni
comptes.

## Contact

Andreas Heiligtag · SwiftAppsBavaria@gmx.net
