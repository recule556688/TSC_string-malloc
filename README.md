# Chaîne de charactères **``char*``** et **``malloc()``**

Bienvenue sur le repo TSC du cour sur les chaînes de charactères et la fonction malloc().

Le but de ce cour est de vous apprendre à manipuler les chaînes de charactères en C et de vous faire découvrir la fonction malloc().

## Sommaire

- [Introduction](#introduction)
- [Les chaînes de charactères](#les-chaînes-de-charactères)
- [La fonction malloc()](#la-fonction-malloc)
- [Ressources](#ressources)

## Introduction

Dans ce cour nous allons revoir ce qu'est une chaine de charactères en C, comment en créer une et comment la manipuler.

Dans un second temps nous allons voir comment créer une chaine de charactères dynamiquement avec la fonction malloc().

## Les chaînes de charactères

Une chaîne de caractères en C est une séquence de caractères, stockée dans un tableau de caractères (``char[]``), avec un caractère nul (``'\0'``) à la fin pour indiquer la fin de la chaîne. Elle est utilisée pour représenter du texte ou des données textuelles et offre de nombreuses fonctionnalités de manipulation de texte telles que la copie, la concaténation, la comparaison, etc.

Vous pouvez retrouver un cour complet sur les chaînes de charactères [ici](./chaine_de_charactère.md).

## La fonction malloc()

La fonction ``malloc()`` permet d'allouer de la mémoire dynamiquement. Elle est très utilisée en C. Elle est déclarée dans le fichier d'en-tête ``<stdlib.h>``. Elle prend en paramètre la taille de la mémoire à allouer en octets. Elle retourne un pointeur sur la mémoire allouée. Si la mémoire n'a pas pu être allouée, elle retourne ``NULL``.

```c
void *malloc(size_t taille);
```

Vous pouvez retrouver un cour complet sur la fonction malloc() [ici](./malloc.md).

## Conclusion

Vous savez maintenant manipuler les chaînes de charactères en C et vous savez utiliser la fonction malloc().

## Ressources

- [Chaîne de charactères](./chaine_de_charactère.md)
- [malloc()](./malloc.md)
- [documentation malloc()](https://en.cppreference.com/w/c/memory/malloc)
- [Exercices](./exercices.md)
- [Chaîne de charactères](https://learn.microsoft.com/fr-fr/cpp/c-language/c-string-literals?view=msvc-170)

## Auteur

- **[Baptiste LEROYER](https://github.com/ZiplEixels)** - _Travail initial_
- **[Arthur DELBARRE](https://github.com/ArthurDelbarre)** - _Relecture_
