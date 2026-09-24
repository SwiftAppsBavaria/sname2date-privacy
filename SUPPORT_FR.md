# Aide de sName2Date

## Ce que fait l'app

sName2Date cherche une date dans le nom de fichier et l'écrit comme date de prise de vue dans
le fichier image, vidéo ou audio. S'il n'y a pas encore de date de prise de vue, elle est
créée.

En haut de la fenêtre figurent pour cela deux cases à cocher, qui ne s'excluent pas :

| | |
|---|---|
| **Écrire la date dans le fichier** | place la date comme date de prise de vue dans le fichier lui-même — la tâche principale de l'app |
| **Convertir les noms de fichiers** | met le nom à l'écriture ISO, pour **tout** type de fichier |

Les deux ensemble constituent le cas normal. Si seule la seconde est cochée, l'app n'ouvre
aucun fichier et se contente de renommer.

## Premiers pas

1. Choisissez un fichier avec « Choisir un fichier… » ou faites-le glisser sur la fenêtre. La
   version complète accepte aussi des dossiers entiers avec leurs sous-dossiers.
2. La liste indique pour chaque fichier la date reconnue et, le cas échéant, la date de prise
   de vue déjà en place.
3. « Écrire la date » exécute la modification.

## Questions fréquentes

**Pour un fichier, il est écrit « Aucune date trouvée dans le nom ».**
Le nom ne contient aucune indication de date reconnaissable. Sont reconnus entre autres
`2024-01-15 10-30-00`, `IMG_20240115_103000`, `2024-01-15`, `2024 01 15`, `2024_01_15`,
`15.01.2024`, `15-01-2024`, `15.01.24` ainsi que les noms de mois écrits en toutes lettres
comme `15 janv. 2024`, `15 mars 2024` ou `January 15 2024`. `2016 04` et `04-2016` sont lus
également — le premier du mois s'applique alors, et la ligne le précise.

L'app reconnaît les noms de mois dans la langue de votre système et en anglais. Les
transcriptions ne sont pas reconnues : en allemand, un nom écrit `15 Maerz 2024` avec ae/oe/ue
au lieu du tréma reste sans date. Saisissez-la alors à la main à droite de la ligne.

**Une date est lue comme un mauvais jour.**
Le 3 avril s'écrit `3/4` en français et `4/3` en anglais — les deux mêmes nombres avec un sens
inversé. Pour `15-03-2024`, cela ne change rien, un mois 15 n'existe pas. Ce n'est que
lorsque les deux nombres peuvent passer pour un mois (`03-05-2024`) qu'il faut trancher :
une barre orange apparaît alors au-dessus de la liste avec les deux lectures au choix, et les
lignes concernées sont signalées. L'écriture de votre région système est préréglée.

**Le nom contient deux indications de date.**
La première l'emporte : dans `IMG_20240115_modifie_2019-03-02`, c'est donc la prise de vue et
non la note ultérieure. Une indication avec heure a toujours priorité sur une indication sans
heure.

**Le nom ne contient qu'une date, pas d'heure.**
Une heure est alors supposée — midi par défaut. Elle se modifie dans les réglages.

**Je souhaite dater une vieille photo numérisée.**
C'est possible : les dates saisies à la main remontent jusqu'à 1826, l'année de la plus
ancienne photographie conservée.

**Ma photo perd-elle en qualité ?**
Non. Les données d'image sont reprises telles quelles, un JPEG n'est pas recompressé. Pour les
films, les pistes sont transmises telles quelles, il n'y a pas de réencodage.

**Quels formats sont pris en charge ?**
L'app écrit la date de prise de vue dans le fichier lui-même pour les images (JPEG, PNG, TIFF,
HEIC, GIF), les films (MP4, MOV, M4V) et les enregistrements audio (M4A, M4B) — la coche de la
ligne est alors verte.

La liste accepte toutefois **tout** fichier. Lorsque le format n'accueille pas de date de
prise de vue — un PDF par exemple, un fichier texte ou un tableur —, l'app règle à la place la
date de création et de modification du fichier ; la coche est alors orange. Les
applications, les alias et les documents au format paquet n'apparaissent pas dans la liste.

**Pour mon fichier HEIF, WebP ou AVI, la coche est bleue.**
Ces trois formats n'accueillent pas de date de prise de vue. L'app l'écrit donc dans un
fichier annexe portant le même nom et l'extension `.xmp`, que les programmes photo comme
Lightroom ou digiKam lisent également.

Pour HEIF, l'extension suffit souvent : les mêmes données portent, sous `.heic`, le nom d'un
autre format et sont alors écrites dans le fichier lui-même.

**Je souhaite seulement mettre de l'ordre dans les noms de fichiers, sans toucher aux
fichiers.**
En haut de la fenêtre, désactivez « Écrire la date dans le fichier » et activez « Convertir
les noms de fichiers ». L'app n'ouvre alors aucun fichier et ne modifie que le nom et, si
l'option est activée dans les réglages, la date de création et de modification —
`Facture 15.03.2024.pdf` devient `2024-03-15 12-00-00 Facture.pdf`, et le dossier se trie par
date dans le Finder. Cela vaut pour tout type de fichier, y compris PDF, texte ou tableurs.

Si la date doit rester là où elle figurait dans le nom, désactivez « Date au début ».

Le renommage modifie l'entrée du dossier, et macOS exige pour cela l'autorisation portant sur
le dossier. Si, dans la version complète, vous choisissez directement le dossier, elle est
ainsi accordée. Si vous avez choisi des fichiers isolés — toujours le cas dans
sName2Date Lite —, l'app demande une seule fois le dossier ; un dossier parent suffit, et
l'autorisation vaut aussi après un redémarrage. Dans la version complète, le bouton
« Choisir un dossier » présente les derniers utilisés dans un menu.

**À côté de mon fichier se trouve un fichier portant l'extension `.xmp`.**
Soit il provient d'un autre programme — Lightroom et digiKam créent de tels fichiers
annexes —, soit sName2Date l'a créé parce que le format n'accueille pas lui-même la date de
prise de vue (HEIF, WebP, AVI ; la coche est alors bleue). ⌘Z supprime une annexe ainsi
créée. L'app entraîne celle qui existe lorsqu'elle modifie la date de prise de vue : sinon le
fichier dirait une chose et son annexe une autre, et la plupart des programmes lisent
l'annexe en premier.

**Pour un grand dossier, l'app demande si elle doit poursuivre la lecture.**
Cela ne concerne que la version complète : sName2Date Lite n'accepte pas de dossiers.
À partir de 5 000 fichiers — par exemple pour le dossier de l'utilisateur avec ses
sous-dossiers —, elle s'arrête et pose la question. Pendant la lecture et l'analyse, elle
affiche un compteur et une barre de progression ; l'écriture n'est possible qu'une fois la
liste complète. C'est plus rapide avec un dossier plus petit ou sans « Inclure les
sous-dossiers ».

**Puis-je annuler une modification ?**
Oui. ⌘Z annule tout un passage — date de prise de vue, date de création et de modification
et, si l'option est activée, le nom de fichier modifié également. ⌘⇧Z le rétablit.

Une remarque tout de même : effectuez une sauvegarde avant de traiter une grande collection.
L'annulation rétablit les valeurs, mais ne remplace pas une copie de sauvegarde.

**Le renommage n'a pas fonctionné, mais la date se trouve bien dans le fichier.**
Si un fichier isolé a été sélectionné, l'app n'a le droit de travailler que sur ce fichier,
pas dans son dossier — or le renommage modifie l'entrée du dossier. Sélectionnez le dossier
plutôt que le fichier isolé, ou accordez l'autorisation lorsque l'app la demande. Une
autorisation accordée une fois vaut aussi après un redémarrage et couvre tous les
sous-dossiers.

## Quelque chose ne va pas ?

Réglages → Diagnostic → « Enregistrer le journal… » consigne les messages des sept derniers
jours dans un fichier texte. N'hésitez pas à le joindre à votre description du problème.

## Contact

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
