# malloc() en C

La fonction malloc en C est utilisée pour allouer dynamiquement de la mémoire pendant l'exécution d'un programme. C'est un outil puissant pour gérer la mémoire, mais il est important de l'utiliser correctement pour éviter les fuites de mémoire et les erreurs de segmentation. Voici comment l'utiliser :

## Inclusion de l'En-tête

Pour utiliser la fonction malloc, vous devez inclure l'en-tête <stdlib.h> dans votre programme. Cela vous donne accès à la déclaration de malloc.

```c
#include <stdlib.h>
```

## Allocation de Mémoire

La fonction malloc alloue de la mémoire dynamiquement et renvoie un pointeur vers la mémoire allouée. Elle prend un argument, qui est la taille en octets de la mémoire que vous souhaitez allouer. Voici comment vous pouvez l'utiliser :

```c
char *monTableau;
int taille = 6; // Nombre de charactères à stocker/allouer

monTableau = (char *)malloc(taille * sizeof(char));

if (monTableau == NULL) {
    printf("Allocation de mémoire a échoué.\n");
    exit(1);
}
```

- ``malloc`` prend un argument, qui est la taille en octets de la mémoire que vous souhaitez allouer. Ici, nous demandons de la mémoire pour 6 caractères, ce qui équivaut à ``taille * sizeof(char)`` octets.
- ``malloc`` renvoie un pointeur vers la mémoire allouée, que nous stockons dans ``monTableau``.

> Notez que nous effectuons une conversion de type (char *) car malloc renvoie un pointeur générique void*. Cette converstion de type est optionelle en C, elle est néanmoins conseiller afin de clarifier le code.

- Nous vérifions si ``malloc`` a réussi en vérifiant si le pointeur renvoyé est ``NULL``. Si l'allocation échoue, nous affichons un message d'erreur et sortons du programme.

## Représentation de la Mémoire Allouée

Voici comment cela pourrait être représenté en mémoire :

```txt
+---+---+---+---+---+---+
| ? | ? | ? | ? | ? | ? |
+---+---+---+---+---+---+
       monTableau
```

## Utilisation de la Mémoire Allouée

Une fois la mémoire allouée, vous pouvez l'utiliser comme n'importe quelle autre variable. Par exemple, vous pouvez affecter des valeurs aux éléments de votre tableau dynamique :

```c
monTableau[0] = 'H';
monTableau[1] = 'e';
monTableau[2] = 'l';
monTableau[3] = 'l';
monTableau[4] = 'o';
monTableau[4] = '\0';
```

La mémoire ressemblerait maintenant à ceci :

```txt
+---+---+---+---+---+---+
| H | e | l | l | o | \0|
+---+---+---+---+---+---+
       monTableau
```

## Libération de la Mémoire

Une fois que vous avez terminé d'utiliser la mémoire allouée dynamiquement, vous devez la libérer en appelant la fonction ``free``. Cela permet de libérer la mémoire pour qu'elle puisse être réutilisée par d'autres parties de votre programme. Voici comment vous pouvez l'utiliser :

```c
free(monTableau);
```

La mémoire est maintenant libérée, mais monTableau conserve sa valeur, ce qui est couramment appelé "pointeur pendu". Il est une bonne pratique de réinitialiser le pointeur à NULL après avoir libéré la mémoire pour éviter tout accès indésirable à la mémoire libérée.

```c
monTableau = NULL;
```

## Visualisation de la libération de la mémoire

Après avoir libéré la mémoire, elle ressemblerait à ceci :

Après avoir libéré la mémoire, la représentation de la mémoire ressemblerait à ceci :

```txt
+---+---+---+---+---+---+
| ? | ? | ? | ? | ? | ? |
+---+---+---+---+---+---+
       monTableau
```

## Gestion des Erreurs

Il est essentiel de vérifier si ``malloc`` a réussi en vérifiant si le pointeur renvoyé est NULL. Si l'allocation échoue, il est recommandé de gérer l'erreur de manière appropriée, comme quitter le programme ou prendre d'autres mesures pour gérer la situation.

C'est essentiel de comprendre la gestion de la mémoire en C pour éviter les fuites de mémoire et les erreurs de segmentation. La fonction malloc est un outil puissant, mais elle nécessite une utilisation prudente pour garantir un comportement fiable et sans erreurs de votre programme.

## Exemple Complet

Voici un exemple complet de l'utilisation de malloc :

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *monTableau;
    int taille = 6; // Nombre de charactères à stocker/allouer

    monTableau = (char *)malloc(taille * sizeof(char));

    if (monTableau == NULL) {
        printf("Allocation de mémoire a échoué.\n");
        exit(1);
    }

    monTableau[0] = 'H';
    monTableau[1] = 'e';
    monTableau[2] = 'l';
    monTableau[3] = 'l';
    monTableau[4] = 'o';
    monTableau[4] = '\0';

    printf("%s\n", monTableau);

    free(monTableau);
    monTableau = NULL;

    return 0;
}
```
