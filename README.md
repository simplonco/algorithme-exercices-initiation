# algorithm-thinking
Comment penser code pour mieux écrire du code

## Qu'est ce que l'algorithme ?

Une façon de réfléchir et d'ecrire en pseudo-code pour résoudre un problème.


## Les algorithmes célébres

* Google, afficher des pages correspondantes à la recherche de l'utilisateur
* Facebook, afficher des posts de vos amis et des posts de pourraient vous intéresser
* Trouver le chemin le plus court (path-finding)


### Mise en situation

Pour un algorithme on a besoin : 

- d'un but : une phrase qui commence par "je veux que la machine"

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

- d'une façon d'ecrire les ordres concises et rigoureuses. 

``` 
  Exemple d'etapes 1 (mauvais algorithme) :
  1. Attraper et lever ma main droite jusqu'à camera
  2. stocker en memoire cette main sous le nom : mainDroite
  3. Reserver espace memoire pour un nombre sous le nom : nombreDeDoigts
  4. Regarder mainDroite
  5. Si nombre de doigt est 1, nombreDeDoigts = 1
  6. Si nombre de doigt est 2, nombreDeDoigts = 2
  ...
  
  Exemple d'etapes 2 (meilleur algorithme) : 
  1. Attraper et lever ma main droite jusqu'à camera
  2. stocker en memoire cette main sous le nom : mainDroite
  3. Reserver espace memoire pour un nombre sous le nom : nombreDeDoigts
  4. Ecrire en memoire que nombreDeDoigts est égale à 0
  5. Regarder avec la camera chaque doigt de **mainDroite** l'un après l'autre en allant de droite à gauche
  6. A chaque doigt, ajouter 1 à la valeur de nombreDeDoigts
  7. Quand il n'y a plus de doigt vers la gauche, montrer la valeur de nombreDeDoigts à l'ecran
  
```

### Activité 1 : Compter les doigts

En vous inspirant de qui a été fait ci-dessus, écrivez la suite d'ordre à donner à la machine dans un éditeur de texte pour faire compter ses doigts aux formateurs et le faire écrire le résultat au tableau !

## Comment l'utiliser concrètement pour le langage informatique

Nous allons utiliser des termes simples pour résoudre le problème afin de traduire plus simplement dans le langage de la machine. Différents concepts seront utilisé. 

Nous allons les détaillés, décrire leur but et définir la syntaxe (la façon d'écrire) à respecter. Une syntaxe bien définit permet de se concentrer sur la résolution du problème et non sur comment 
écrire la solution pour être compréhensible.

### Les variables

Les  variables sont des objets dont le contenu peut varier pendant l’exécution du programme. Les variables portent un nom et sont d’un type donné. Il y a plusieurs type de données (nombre, chaines de caractères, etc.)

Exemples: 
* **a** : variable de type numérique
* **nom*** : variable de type caractères
* **visible** : variable de type Booléen

Pour y stocker des informations (y affecter une valeur) nous écrirons de cette façon (syntaxe) : ```nom <- valeur```

Exemples: 

```
a <- 56
nom <- "Simplon"
visible <- true
```

*Remarque : Les chaînes de caractères pouvant être un nombre, une lettre ou un caractère spécial. C'est pourquoi, par convention, nous utiliserons les guillemets pour identifier la valeur d'une variable comme chaînes de caractères.*

Faire les [exercices](exercices/variables) suivants et les faire valider.


### Les conditions
Les conditions permettent d'exécuter ou non certaines parties du programme.

Il existe 3 structures conditionnelles :

**La structure SI **

Si la condition est vraie alors on exécute l'instruction

Syntaxe (ou façon d'écrire) :
```
SI condition  ALORS
    Instructions
FINSI
```

exemple : 

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

exemple : 

```
SI sexe="M"  ALORS
    Afficher ("Bienvenue Monsieur")
SINON
    Afficher ("Bienvenue Madame")
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

exemple : 

```
CAS genre  DE
    "Masculin":  Afficher ("Bienvenue Monsieur")
    "Féminin" :  Afficher ("Bienvenue Madame")
    AUTRE:       Afficher ("Bienvenue indéterminé")
FINCAS
```

*Remarque: le terme *AUTRE* concernce tous les autres cas dont on n'a pas spécifié de valeurs*

Faire les [exercices](exercices/conditions) suivants et les faire valider.


### Les boucles ou itérations

Elles permettent d'exécuter plusieurs fois les mêmes instructions.

Il existe plusieurs structures itératives

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

Les instructions seront répétées jusqu'à ce que la condition soit vraie

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

La boucle ci-dessus s'effectuera tant que l'utilisateur n'a pas rentrée une des lettres suivantes : *O,o,N,n*

**La structure POUR ... FINPOUR**

Les instructions seront exécutées un nombre fini de pas.

Syntaxe : 

```
POUR variable <- valeur initiale A valeur finale PAS p
    Instructions
FINPOUR
```

Exemple : 

```
POUR i<- 0 à 100 PAS 2
    Afficher(i)
FINPOUR
```

Cela affichera les nombres de 2 en 2 de 0 à 100

——————

## Quelques références
* https://www.grafikart.fr/formations/apprendre-algorithmique/
* http://silentteacher.toxicode.fr/
* https://www.kwyk.fr/algorithme/
* https://www.tutorialspoint.com/data_structures_algorithms/data_structure_overview.htm
* http://www.geeksforgeeks.org/fundamentals-of-algorithms/
* https://pdf.k0nsl.org/C/Computer%20and%20Internet%20Collection/2015%20Computer%20and%20Internet%20Collection%20part%209/Packt%* 20Publishing%20Learning%20JavaScript%20Data%20Structures%20and%20Algorithms%20(2014).pdf
* https://www.programiz.com/article/algorithm-programming
