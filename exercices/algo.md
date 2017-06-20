# Exercices d'algorithme

Résoudre les problèmes suivants en écrivant les solutions sur une feuille. 

*Aide* :

Pour les exercices suivants, considérez que vous pouvez accèder aux lettres d'une chaîne de caractère comme si c'était un tableau 

Exemple : 

Afficher chaque lettre, une par une, du mot "hey"

```
mot <- "hey"
Afficher(mot[0])  
Afficher(mot[1])
Afficher(mot[2])
```

## Exercice 1 

Un des plus anciens systèmes de cryptographie (aisément déchiffrable) consiste à décaler les lettres d’un message pour le rendre illisible. Ainsi, les A deviennent des B, les B des C, etc. 

Ecrivez un algorithme qui demande une phrase à l’utilisateur et qui la code selon ce principe. 

## Exercice 2

Une amélioration (relative) du principe précédent consiste à opérer avec un décalage non de 1, mais d’un nombre quelconque de lettres. Ainsi, par exemple, si l’on choisit un décalage de 12, les A deviennent des M, les B des N, etc.

Réalisez un algorithme sur le même principe que le précédent, mais qui demande en plus quel est le décalage à utiliser. Votre sens proverbial de l'élégance vous interdira bien sûr une série de vingt-six "Si...Alors"

## Exercice 3 

Une technique ultérieure de cryptographie consista à opérer non avec un décalage systématique, mais par une substitution aléatoire. Pour cela, on utilise un alphabet-clé, dans lequel les lettres se succèdent de manière désordonnée, par exemple :
HYLUJPVREAKBNDOFSQZCWMGITX
C’est cette clé qui va servir ensuite à coder le message. Selon notre exemple, les A deviendront des H, les B des Y, les C des L, etc.

Ecrire un algorithme qui effectue ce cryptage (l’alphabet-clé sera saisi par l’utilisateur, et on suppose qu'il effectue une saisie correcte).