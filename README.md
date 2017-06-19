# Algorithme

Comment penser "code" pour mieux écrire du code.

## Qu'est ce que l'algorithme ?

Une façon de réfléchir et d'écrire en "pseudo-code" pour résoudre un problème.

## Les algorithmes célébres

* Google, afficher des pages correspondantes à la recherche demandée par l'internaute.
* Facebook, afficher des posts de vos amis et des posts qui pourraient vous intéresser.
* Trouver le chemin le plus court (path-finding).

### Mise en situation

Pour un algorithme on a besoin :

- d'un but : une phrase qui commence par "je veux que la machine".

```
   Exemples de but :
   Je veux que la machine :
   * compte mes doigts
   * cueille des pommes
   * écrive "bonjour" sur mon clavier
   * me reveille à 7h00
```

- d'une machine avec des capacités matérielles définies

```
   Ma machine a :
   * une mémoire (par défaut)
   * une camera
   * un bras articulé
   * un petit écran
```

- d'une façon d'écrire les ordres concis et rigoureux.

```
  Exemple d'étapes 1 (mauvais algorithme) :
  1. Attraper et lever ma main droite jusqu'à camera
  2. Stocker en memoire cette main sous le nom : mainDroite
  3. Réserver espace memoire pour un nombre sous le nom : nombreDeDoigts
  4. Regarder mainDroite
  5. Si nombre de doigt est 1, nombreDeDoigts = 1
  6. Si nombre de doigt est 2, nombreDeDoigts = 2
  ...

  Exemple d'étapes 2 (meilleur algorithme) :
  1. Attraper et lever ma main droite jusqu'à camera
  2. Stocker en memoire cette main sous le nom : mainDroite
  3. Réserver espace mémoire pour un nombre sous le nom : nombreDeDoigts
  4. Écrire en mémoire que nombreDeDoigts est égale à 0
  5. Regarder avec la camera chaque doigt de **mainDroite** l'un après l'autre en allant de droite à gauche
  6. À chaque doigt, ajouter 1 à la valeur de nombreDeDoigts
  7. Quand il n'y a plus de doigt vers la gauche, montrer la valeur de nombreDeDoigts à l'écran

```

### Activité 1 : Dessiner c'est gagné

En vous inspirant de ce qui a été fait ci-dessus, écrivez la suite d'ordre à donner à la machine dans un éditeur de texte pour faire  dessiner une maison par le formateur !

## Comment l'utiliser concrètement pour le langage informatique

Nous allons utiliser des termes simples pour résoudre les problèmes afin de traduire plus simplement dans le langage de la machine. Différents concepts seront utilisés.

Nous allons les détailler, décrire leur but et définir la syntaxe (la façon d'écrire) à respecter. Une syntaxe bien définie permet de se concentrer sur la résolution du problème et non sur comment écrire la solution pour être compréhensible.

### Les variables

Les  variables sont des objets dont le contenu peut varier pendant l’exécution du programme. Les variables portent un nom et sont d’un type donné. Il y a plusieurs type de données (nombre, chaîne de caractères, booléen, etc.)

Exemples:

* **a** : variable de type numérique
* **nom** : variable de type caractères
* **visible** : variable de type booléen

Pour y stocker des informations (y affecter une valeur) nous écrirons de cette façon (la syntaxe) : ```nom <- valeur```

Exemples:

```
a <- 56
nom <- "Simplon"
visible <- true
```

*Remarque : Les chaînes de caractères peuvent être des nombres, des lettres ou des caractères spéciaux. C'est pourquoi, par convention, nous utiliserons les guillemets pour différencier les chaînes de caractères.*

Faire les [exercices](exercices/variables.md) suivants et les faire valider. D'abord par votre camarade d'à côté puis par les facilitateurs.

### Les conditions

Les conditions permettent d'exécuter ou non certaines parties du programme.

Il existe 3 structures conditionnelles :

**La structure SI**

Si la condition est vraie alors on exécute l'instruction

Syntaxe (ou façon d'écrire):

```
SI condition  ALORS
    Instructions
FINSI
```

Exemple :

```
SI sexe="M"  ALORS
    Afficher ("Bienvenue Monsieur")
FINSI
```

**La structure SI..SINON**

Si la condition est vraie alors on exécute l'*Instruction A* sinon on exécute l'*Instruction B*

Syntaxe :

```
SI condition  ALORS
    Instructions A
SINON
    Instructions B
FINSI
```

Exemple :

```
SI sexe="M"  ALORS
    Afficher("Bienvenue Monsieur")
SINON
    Afficher("Bienvenue Madame")
FINSI
```

**Remarque**

Les conditions peuvent être composées.

Comme par exemple, pour qu'une porte s'ouvre il faut qu'elle soit dévérouillée **ET** que quelqu'un actionne la poignée.

Ou, pour allumer la télé il faut appuyer sur le bouton de la télécommande **OU** sur le bouton sur la télé directement.

Exemple :

```
SI sexe="M" ET age > 18 ALORS
    Afficher("Bonjour monsieur")
SINON
    Afficher("Bonjour jeune homme")
FINSI

SI sexe="M" OU sexe="F" ALORS
    Afficher("Genre définit")
SINON
    Afficher("Genre non définit")
FINSI
```

Vous pouvez mettre des priorités dans des conditions avec des parenthèses. La machine commencera par vérifier d'abord ce qu'il y a à l'intérieur
des parenthèses puis le reste.

Exemple :

```
SI (sexe="M" ET age > 18) OU (sexe="F" ET age > 18) ALORS
    Afficher("Bonjour jeune gens")
SINON
    Afficher("Bonjour")
FINSI
```

**La structure CAS..DE**

Suivant le cas d'une variable on effectue des instructions.

Syntaxe (ou façon d'écrire):

```
CAS variable  DE
    valeur1:  Instructions A
    valeur2:  Instructions B
    .......
    Autre:     Instructions C
FINCAS
```

Exemple :

```
CAS genre  DE
    "Masculin":  Afficher ("Bienvenue Monsieur")
    "Féminin" :  Afficher ("Bienvenue Madame")
    AUTRE:       Afficher ("Bienvenue indéterminé")
FINCAS
```

*Remarque: le terme *AUTRE* concerne tous les autres cas dont on n'a pas spécifié de valeurs*

Faire les [exercices](exercices/conditions.md) suivants et les faire valider. D'abord par votre camarade d'à côté puis par les facilitateurs.


### Les boucles ou itérations

Elles permettent d'exécuter plusieurs fois les mêmes instructions.

Il existe plusieurs structures itératives :

**La structure TANT QUE**

Les instructions seront répétées tant que la condition est vraie

Syntaxe :

```
TANT QUE condition
    Instructions
FTQ
```

*Remarque: FTQ veut dire FIN TANT QUE*

Exemple :

```
genre <- "Rien"
TANT QUE genre <> "M" ET genre <> "F"
    Afficher("Entrez votre genre (M/F)")
    Entrer(genre)
FTQ
Afficher "Saisie acceptée"
```

*Remarque : le signe **<>** signifie **différent de***

**La structure REPETER...JUSQU'A**

Les instructions seront répétées jusqu'à ce que la condition soit vraie.

Syntaxe (ou façon d'écrire):

```
REPETER
    Instructions
JUSQU'A condition
```

Exemple :

```
REPETER
    Afficher("Voulez vous un café ? (O/N))
    Entrer(reponse)
JUSQU'A reponse="O" OU reponse="o" OU reponse="N" OU reponse="n"
Afficher "Saisie acceptée"
```

La boucle ci-dessus s'effectuera tant que l'utilisateur n'a pas rentré une des lettres suivantes : *O,o,N,n*

**La structure POUR ... FINPOUR**

Les instructions seront exécutées un "nombre fini de pas".

Syntaxe :

```
POUR variable <- valeur_initiale A valeur_finale PAS p
    Instructions
FINPOUR
```

Exemple :

```
POUR i<- 0 à 100 PAS 2
    Afficher(i)
FINPOUR
```

Cela affichera les nombres de 2 en 2 de 0 à 100.

Faire les [exercices](exercices/boucles.md) suivants et les faire valider. D'abord par votre camarade d'à côté puis par les facilitateurs.

### Les tableaux

Les variables ne peuvent contenir qu'*une seule valeur* à un instant donné.

Si l'on veut entrer 50 notes il faudra alors 50 variables (ce qui est long) ou utiliser un  tableau (ce qui plus simple).

Un tableau est une structure pouvant contenir un grand nombre d'éléments à un instant donné.

Voyez le tableau comme une grosse boîte avec des compartiments à l'intérieur pour ranger les éléments.

Les tableaux portent un nom et peuvent contenir plusieurs valeurs. 

Syntaxe :

```
nomTableau <- [valeur1, valeur2, valeur3]
```

Pour pouvoir accéder aux valeurs spécifiques dans le tableau nous allons utiliser un nombre qui correspondra à la position de l'élément : *l'indice*.

Exemple :

```
ville <- ["Saint-Denis","Saint-André", "Saint-Pierre"]
```

* Pour accéder à *Saint-Denis* qui se trouve à la **position O** : ```ville[0]```
* Pour accéder à *Saint-André* qui se trouve à la **position 1** : ```ville[1]```
* Pour accéder à *Saint-Pierre* qui se trouve à la **position 2** : ```ville[2]```

Vous pouvez même changer la valeur d'un élément du tableau :

* Pour modifier ce qui se trouve à la **position O** : ```ville[0] <- "Paris"```
* Pour modifier ce qui se trouve à la **position 1** : ```ville[1] <- "New York"```
* Pour modifier ce qui se trouve à la **position 2** : ```ville[2] <- "Tokyo"```

Vous l'avez compris, l'*indice* du tableau *commence à 0*.

Quand on parle de la taille d'un tableau on parle du nombre total d'éléments qu'il contient. Par exemple, le tableau précédent, ```ville```, a une taille qui vaut 3.

Faire les [exercices](exercices/tableaux.md) suivants et les faire valider. D'abord par votre camarade d'à côté puis par les facilitateurs.


## À vous de jouer

On va commencer tranquillement par un petit minecraft :) cliquez sur ce [lien](https://studio.code.org/s/mc/stage/1/puzzle/1) et finissez les 13 niveaux.

Maintenant que ça commence à rentrer amusez-vous avec [blockly](https://blockly-games.appspot.com/).

*IMPORTANT*:

Quand ça devient un peu compliqué, utilisez une feuille et un stylo pour écrire l'algo puis testez le pour voir si ça marche !

Il est important de passer par cette étape où on écrit d'abord sur le papier puis on revient sur la machine.

——————

## Quelques références

* https://www.grafikart.fr/formations/apprendre-algorithmique/
* https://www.tutorialspoint.com/data_structures_algorithms/data_structure_overview.htm
* http://www.geeksforgeeks.org/fundamentals-of-algorithms/
* https://www.programiz.com/article/algorithm-programming
