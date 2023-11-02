# malloc()

## Introduction

La fonction `malloc()` permet d'allouer de la mémoire dynamiquement. Elle prend en paramètre la taille en octets de la mémoire à allouer et retourne un pointeur sur la zone mémoire allouée. Si la mémoire ne peut pas être allouée, la fonction retourne `NULL`.

## Exemple

```c
#include <stdlib.h>
#include <stdio.h>

int main(void)
{
    int *ptr = malloc(sizeof(int));

    if (ptr == NULL) {
        printf("Erreur lors de l'allocation de mémoire\n");
        return (1);
    }
    *ptr = 42;
    printf("%d\n", *ptr);
    free(ptr);
    return (0);
}
```

## Explication

La fonction `malloc()` prend en paramètre la taille en octets de la mémoire à allouer. Dans l'exemple, on alloue la taille d'un `int` avec `sizeof(int)`. La fonction retourne un pointeur sur la zone mémoire allouée. Si la mémoire ne peut pas être allouée, la fonction retourne `NULL`. Il est donc important de vérifier si le pointeur retourné est `NULL` avant de l'utiliser.

## Utilisation

La fonction `malloc()` est définie dans l'en-tête `stdlib.h`. Il est donc nécessaire d'inclure cet en-tête pour l'utiliser.

```c
#include <stdlib.h>
```
