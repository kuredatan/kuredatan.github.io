---
title: "3. Le raisonnement par contraposition"
date: 2017-01-01
excerpt: "Pour comprendre le raisonnement par contraposition, il est utile de préciser ce que l'on entend par Si A alors B (A représentant les hypothèses de l'énoncé et B ses conclusions).

Pour cela, on va définir ou, et, non par des tables de vérité. A est vrai si A est évalué à 1 et A est faux si A est évalué à 0..."
---

La version PDF de cet article est disponible [ici]({{ site.surl }}/assets/Contraposition-et-absurde.pdf).

Pour comprendre le raisonnement par contraposition, il est utile de préciser ce que l'on entend par "Si A alors B" (A représentant les hypothèses de l'énoncé et B ses conclusions).

Pour cela, on va définir ou, et, non par des tables de vérité. A est vrai si A est évalué à 1 et A est faux si A est évalué à 0.

La première table ci-dessous correspond bien à l'utilisation habituelle du ou : "A ou B" est vrai si et seulement si au moins l'un des deux est vrai.

La seconde table correspond bien à l'utilisation habituelle du et : "A et B" est vrai si et seulement si les deux sont vrais.

| A | B |A ou B|
|---|---|-----|
| 0 | 0 |0|
| 0 | 1 |1|
| 1 | 0 |1|
| 1 | 1 |1|

| A | B | A et B |
|---|---|--------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

La table de vérité de non est la suivante :

| A  | non A |
|----|-------|
| 0  | 1|
| 1  | 0|

Cette table correspond bien à l'utilisation habituelle du non : non A est vrai si et seulement si A est faux. On remarque que non(non A) est équivalent à A (ils ont la même table de vérité, en d'autres termes A est vrai si et seulement si non(non A) est vrai).

On définit "Si A alors B" (ou "A implique B", noté A $\Rightarrow$ B) par la table de vérité suivante :

| A  | B  | A $\Rightarrow$ B |
|----|----|-------------------|
| 0  | 0  | 1 |
| 0  | 1  | 1 |
| 1  | 0  | 0 |
| 1  | 1  | 1 |


Cette table correspond bien à l'utilisation habituelle de "Si A alors B" : lorsque A est faux, B peut être vrai ou faux, lorsque A est vrai, B est vrai.

Considérons à présent la table de vérité de "(non A) ou B".

| A  | B  | (non A) ou B |
|----|----|--------------|
| 0  | 0  | 1 |
| 0  | 1  | 1 |
| 1  | 0  | 0 |
| 1  | 1  | 1 |

C'est la même table de vérité que celle de "A implique B". En d'autres termes, "A implique B" est équivalent à "(non A) ou B".

De la même manière, "(non B) implique (non A)" est équivalent à "(non(non B)) ou (non A)" donc à "B ou (non A)".

Or "B ou (non A)" est équivalent à "(non A) ou B" qui est équivalent à "A implique B" donc "(non B) implique (non A)" est équivalent à "A implique B".

Plutôt que de démontrer "Si A alors B", on peut donc démontrer "Si (non B) alors (non A)". C'est le raisonnement par contraposition.

## Le raisonnement par l'absurde. ##

Pour les énoncés de la forme "B" (avec B les conclusions), on peut également mener un raisonnement par contraposition, en réécrivant l'énoncé sous la forme "Si A alors B", avec le même B et avec A la proposition toujours vraie (dont la table de vérité n'a que des 1 dans la dernière colonne), et en démontrant "Si (non B) alors (non A)", avec (non A) la proposition toujours fausse (dont la table de vérité n'a que des 0 dans la dernière colonne).
 
 "$2 = 2$" est un exemple de proposition toujours vraie et sa négation "$2 \neq 2$" est un exemple de proposition toujours fausse. Comme on aboutit à quelque chose d'absurde (la proposition toujours fausse) on préfère souvent appeler cette forme du raisonnement par contraposition le raisonnement par l'absurde.

Énoncé : Il y a une infinité de nombres premiers.

Supposons qu'il y a un nombre fini de nombres premiers, notons-les $p_1,...,p_n$ avec $n\in\mathbb{N} \setminus${$0$}. Notons $p = p_1 \times ... \times p_n + 1$. Le produit des $p_i$ est supérieur à 1 donc $p$ est supérieur à 2. $p$ admet donc une décomposition en facteurs premiers (voir article 2). Il existe donc $i \in${$1,...,n$} tel que $p = p_i \times q$ avec $q$ un entier. Notons $m$ le produit des $p_j$ différents de $p_i$. On a donc :
$$1 = p - p_i \times m = p_i \times (q - m) $$
Or $p_i \geq 2$ (car $p_i$ est premier) et $q-m$ est un entier (car $q$ et $m$ sont des entiers) strictement positif (car c'est $\frac{1}{p_i}$) donc $(q-m) \geq 1$ donc $1 \geq 2$ : ceci est absurde (c'est la proposition toujours fausse).
On en déduit qu'il y a une infinité de nombres premiers.

Une autre forme de raisonnement par l'absurde est la suivante : pour montrer "Si A alors B", on peut montrer "Si A et non B alors C" avec C la proposition toujours fausse. En effet, (A et non B) $\Rightarrow$ C est équivalent à (non C) $\Rightarrow$ (non(A et non B)) et (non(A et non B)) est équivalent à (non A ou B) (comparez les deux tables de vérité), c'est-à-dire à A $\Rightarrow$ B.

Clémentine Lemarié--Rieusset
