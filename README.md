# Synthèse d'invariants en SMT-LIB

Cours de Logique, L3 Informatique, Université de Paris, 2022–2023

## Objectif du projet

Ce projet permet d'automatiser la synthèse d'invariants de
boucle pour un très petit langage de programmation, décrit
ci-dessous.

## Langage WA

Nous définissons un langage de programmation « WA » (While-Assert),
qui modélise des programmes Java de la forme générale suivante :

```java
int x1 = a1;
// (...)
int xk = ak;
while (s) {
    x1 = b1;
    // (...)
    xk = bk;
}
assert (t);
```

Plus formellement, un programme WA est défini comme un uplet
`(k, a1, ..., ak, b1, ..., bk, s, t)`, où `k` est un entier représentant le
nombre de variables utilisées par le programme, `a1`, ..., `ak` et
`b1`, ..., `bk` sont des `termes`, et `s` et `t` sont des `tests`. Les
variables utilisées dans les termes et les tests seront `x1`, ...,
`xk`, toujours de type entier. Ici, un `terme` de WA est construit à
partir de variables et de constantes entières en appliquant les
opérations arithmétiques `+` et `*`, et un `test` est défini comme une
formule atomique, qui compare deux termes par l'égalité ou par
l'ordre. Par exemple, le programme Java donné dans l'exercice 1
correspond, après l'application du renommage de `i` en `x1`
et de `v` en `x2`, au programme WA suivant :
`(2, 0, 0, x1 + 1, x2 + 3, x1 < 3, x2 = 9)`.

## Tester le projet

Le fichier `invariants.ml` contient le programme de l'exercice 1 dans
`p1`. Un autre programme WA `p2` teste notre solution
pour l'exercice 2. Vous pouvez utiliser Z3 pour vérifier que notre code SMT-LIB
est bien correct (en ligne : https://jfmc.github.io/z3-play/).

## Auteurs du projet

CHERIFI Rayan

DEBBAH Martin
