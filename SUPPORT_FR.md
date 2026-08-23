# Aide de sName2Date

## Ce que fait l'app

sName2Date cherche une date dans le nom de fichier et l'écrit comme date de prise de vue dans
le fichier image ou vidéo. S'il n'y a pas encore de date de prise de vue, elle est créée.

La version complète dispose pour cela de **deux modes**, commutables en haut de la fenêtre :

| | |
|---|---|
| **Date de prise de vue** | écrit la date dans le fichier — la tâche principale de l'app |
| **Noms de fichiers** | met seulement le nom à l'écriture ISO, pour **tout** fichier |

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
Dans le mode *Date de prise de vue* : les images JPEG, PNG, TIFF, HEIC et GIF, les films MP4,
MOV et M4V. Dans tous ces formats, l'app écrit la date dans le fichier lui-même.

Dans le mode *Noms de fichiers*, **aucune extension ne compte** — seul le nom y est modifié,
et tout fichier en possède un.

**Mon fichier HEIF, WebP ou AVI n'apparaît pas du tout dans la liste.**
Ces trois formats n'accueillent pas de date de prise de vue — l'app ne pourrait qu'y déposer
la date à côté au lieu de l'écrire dedans, et ce n'est précisément pas sa raison d'être. Ils
sont donc ignorés au chargement dans le mode *Date de prise de vue* ; une ligne au-dessus de
la liste indique combien il y en avait.

Ils peuvent malgré tout être renommés : basculez pour cela sur *Noms de fichiers*.

Pour HEIF, l'extension suffit souvent : les mêmes données portent, sous `.heic`, le nom d'un
autre format et sont alors écrites.

**Je souhaite seulement mettre de l'ordre dans les noms de fichiers, sans toucher aux
fichiers.**
Basculez en haut de la fenêtre sur *Noms de fichiers*. L'app n'ouvre alors aucun fichier et
ne modifie que le nom — `Facture 15.03.2024.pdf` devient `2024-03-15 12-00-00 Facture.pdf`,
et le dossier se trie par date dans le Finder. Cela vaut pour tout type de fichier, y compris
PDF, texte ou tableurs.

Si la date doit rester là où elle figurait dans le nom, désactivez « Date au début ».

⚠️ Dans ce mode, l'app n'accepte que des **dossiers**, pas des fichiers isolés. La raison
tient au renommage lui-même : il modifie l'entrée du dossier, et macOS exige pour cela
l'autorisation portant sur le dossier — elle naît du fait que vous le sélectionnez. Une fois
choisi, l'app le retient ; le bouton « Choisir un dossier » présente les derniers utilisés
dans un menu.

**À côté de mon fichier se trouve un fichier portant l'extension `.xmp`.**
Il provient d'un autre programme — Lightroom et digiKam créent de tels fichiers annexes.
sName2Date n'en crée aucun, mais entraîne celui qui existe lorsqu'elle modifie la date de
prise de vue. Sinon le fichier dirait une chose et son annexe une autre, et la plupart des
programmes lisent l'annexe en premier.

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

Andreas Heiligtag · andreas.heiligtag@gmx.de
