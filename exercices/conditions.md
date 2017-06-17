# Exercices : Les conditions 

Qu'affiche le code ci-dessous

### Exercice 1

```
SI 15 < 20 ALORS
    Affiche("Team Captain America")
SINON
    Affiche("Iron Man")
FINSI
```

### Exercice 2

```
age <- 17
SI age < 18 ALORS
    Affiche ("Vous êtes mineur")
SINON
    Affiche ("Vous êtes majeur")
FINSI
```

### Exercice 3

```
age <- 99
SI age < 18 ALORS
    Affiche("Vous êtes mineur")
SINON
    Affiche("Vous êtes majeur")
FINSI
```

### Exercice 4

```
animal  <- "chat"
couleur <- "marron"
SI animal = "chat" ET couleur = "marron" ALORS
    Affiche ("C'est mon chat")
SINON
    Affiche ("Ce n'est pas mon chat")
FINSI
```

### Exercice 5

```
animal  <- "chat"
couleur <- "blanc"
SI animal = "chat" ET couleur = "blanc" ALORS
    Affiche("C'est mon chat")
SINON
    Affiche("Ce n'est pas mon chat")
FINSI
```

### Exercice 6

```
cadeau  <- "Iphone"
SI cadeau = "Galaxy S7" OU cadeau = "Galaxy S8" ALORS
    Affiche("Merci !!! Ca me fait trop plaisir !")
SINON
    SI cadeau = "Iphone" ALORS
        Affiche("Jette moi ça !!!")
    SINON
        Affiche("Merci :)")
    FINSI
FINSI
```

### Exercice 7

```
cadeau  <- "Galaxy S7"
SI cadeau = "Galaxy S7" OU cadeau = "Galaxy S8" ALORS
    Affiche("Merci !!! Ca me fait trop plaisir !")
SINON
    SI cadeau = "Iphone" ALORS
        Affiche("Jette moi ça !!!")
    SINON
        Affiche("Merci :)")
    FINSI
FINSI
```

### Exercice 8

Compléter la condition ci-dessous pour afficher *C'est mon animal* quand l'animal est un chat de couleur gris ou un chien de couleur "marron".

```
animal  <- "chien"
couleur <- "noir"
SI ..................  ALORS
    Affiche("C'est mon animal")
SINON
    Affiche("Ce n'est pas mon animal")
FINSI
```

### Exercice 9

Compléter la condition ci-dessous pour afficher *C'est mon animal* quand l'animal est un chat de couleur *gris* ou de couleur *marron*.

```
animal  <- "chien"
couleur <- "noir"
SI ..................  ALORS
    Affiche("C'est mon animal")
SINON
    Affiche("Ce n'est pas mon animal")
FINSI
```