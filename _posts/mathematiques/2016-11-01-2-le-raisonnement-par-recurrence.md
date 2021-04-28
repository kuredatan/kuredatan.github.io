---
title: "2. Le raisonnement par récurrence"
date: 2016-11-01
excerpt: "Lorsqu'on veut démontrer une propriété qu'ont tous les entiers naturels (c'est-à-dire les entiers positifs, 0, 1, 2 etc) il est parfois pratique d'utiliser un raisonnement par récurrence. Ce type de raisonnement consiste à montrer que la propriété est vérifiée par 0 (initialisation) puis de montrer que si elle est vérifiée par un entier naturel n alors elle est vérifiée par n + 1 (hérédité)..."
---

La version PDF de cet article est disponible [ici]({{ site.surl }}/assets/Récurrence.pdf).

Lorsqu'on veut démontrer une propriété qu'ont tous les entiers naturels (c'est-à-dire les entiers positifs, $0, 1, 2$ etc) il est parfois pratique d'utiliser un raisonnement par récurrence. Ce type de raisonnement consiste à montrer que la propriété est vérifiée par $0$ (initialisation) puis de montrer que si elle est vérifiée par un entier naturel $n$ alors elle est vérifiée par $n + 1$ (hérédité). 

Pour une propriété qui n'est vérifiée qu'à partir d'un certain rang, c'est-à-dire pour les entiers supérieurs à un entier fixé $N$, on montre que la propriété est vérifiée par $N$ (initialisation) puis que si elle est vérifiée par un entier naturel $n$ alors elle est vérifiée par $n + 1$ (hérédité).

Il existe une variante pour la phase d'hérédité, dans ce qu'on appelle la récurrence forte. Au lieu de seulement supposer que la propriété est vérifiée par un entier naturel $n$, on suppose qu'elle est vérifiée par tous les entiers naturels inférieurs à $n$, et on montre qu'elle est alors vérifiée par $n + 1$.

Définition : Un entier naturel $p$ supérieur à $2$ est premier s'il n'existe pas d'entiers naturels $a$ et $b$ tels que $p = a\times b$, $a \neq 1$ et $b \neq 1$ (c'est-à-dire tels que $p$ soit égal au produit de $a$ et de $b$ avec $a$ et $b$ différents de $1$).

Notation : On note $\mathbb{N}$ l'ensemble des entiers naturels.

$n \in \mathbb{N}$ signifie $n$ appartient à $\mathbb{N}$ c'est-à-dire $n$ est un entier naturel.

Remarques : Si $n = a\times b$ avec $n,a,b \in \mathbb{N}$ non nuls alors $n \geq a$ (car $b \geq 1$) et $n \geq b$ (car $a \geq 1$). De plus, si $n = a\times b$ alors $a > 1$ entraîne $n > b$ et $b > 1$ entraîne $n > a$. Pour savoir si $p \in \mathbb{N}$ est premier, il suffit donc de calculer $a\times b$ pour tous les couples $(a,b)$ d'entiers compris strictement entre $1$ et $p$ : si l'un de ces produits est égal à $p$ alors $p$ n'est pas premier, sinon $p$ est premier.

Exemples : $2$ est premier (il n'y a tout simplement pas de couple d'entiers $(a,b)$ tel que $1<a<2$ et $1<b<2$)

$3$ est premier (le seul couple d'entiers à considérer est $(2,2)$ et $2 \times 2 = 4$)

$4$ n'est pas premier (car $2 \times 2 = 4$)

Énoncé : Tout entier naturel $n$ supérieur à $2$ admet une décomposition en facteurs premiers. En d'autres mots, si $n \in \mathbb{N}$ est supérieur à $2$ alors il existe $m \in \mathbb{N}$ supérieur à $1$ et $p_1 \leq ... \leq p_m$ $m$ nombres premiers tels que $n = p_1 \times ... \times p_m$.

Démontrons cet énoncé par récurrence (forte).

Initialisation : $2$ est premier, d'où l'existence de la décomposition en facteurs premiers de $2$.

Hérédité : Soit $n \in \mathbb{N}$ supérieur à $2$. Supposons que, pour tout $2 \leq m \leq n$, $m$ admet une décomposition en facteurs premiers.

Si $n + 1$ est premier alors $n + 1$ admet une décompositon en facteurs premiers.

Sinon, il existe $ 1 < a < n + 1$ et $ 1 < b < n + 1$ tels que $n + 1 = a \times b$.

Par hypothèse de récurrence, $a$ et $b$ admettent une décomposition en facteurs premiers (car $2 \leq a \leq n$ et $2 \leq b \leq n$), notons $a = p_1 \times ... \times p_k$ avec $k \in \mathbb{N}$ supérieur à 1, $p_1, ..., p_k$ premiers et $b = q_1 \times ... \times q_l $ avec $l \in \mathbb{N}$ supérieur à 1, $q_1, ..., q_l$ premiers.

$n + 1 = a \times b = p_1 \times ... \times p_k \times q_1 \times ... \times q_l$ donc $n + 1$ admet une décomposition en facteurs premiers.

### Quelques notations pour la suite. ###

On a introduit dans cet article la notation pour l'ensemble des entiers naturels : $\mathbb{N}$.

L'ensemble des entiers relatifs, c'est-à-dire des entiers négatifs et positifs, se note $\mathbb{Z}$. $\mathbb{Z}$ contient $0, 1, 2$ etc mais aussi $-1, -2$ etc.

L'ensemble des rationnels, c'est-à-dire des fractions d'entiers, se note $\mathbb{Q}$. $\mathbb{Q}$ contient $\frac{1}{2}$, $-4$, $\frac{33}{16}$, $0$, $-\frac{3}{4}$, $2$ etc.

L'ensemble des réels se note $\mathbb{R}$. C'est l'ensemble des longueurs possibles d'un segment (la longueur du rebord de votre table est un réel).

Il existe bien évidemment des manières plus rigoureuses de définir ces ensembles (notamment pour $\mathbb{R}$...) mais elles seront abordées beaucoup plus tard (afin de donner du temps au lecteur pour se familiariser avec les mathématiques).

Tout élément de $\mathbb{N}$ appartient à $\mathbb{Z}$, on dit que $\mathbb{N}$ est inclus dans $\mathbb{Z}$, et on note $\mathbb{N} \subset \mathbb{Z}$. On a aussi $\mathbb{Z} \subset \mathbb{Q}$ et $\mathbb{Q} \subset \mathbb{R}$.

Une autre notation utile est $\setminus$ qui se lit "privé de". Si A et B sont deux ensembles, A$\setminus$B est l'ensemble des éléments qui appartiennent à A mais pas à B. $\mathbb{Z} \setminus \mathbb{N}$ est l'ensemble des entiers strictements négatifs.

{$0$} est l'ensemble constitué de $0$. {$0, 8, -3$} est l'ensemble constitué de $0, 8$ et $-3$. D'une manière plus générale, {$x$} est l'ensemble constitué de $x$, {$x_1, x_2$} est l'ensemble constitué de $x_1$ et $x_2$, et ainsi de suite.

Dans la Remarque, plutôt que d'écrire $n,a,b \in \mathbb{N}$ non nuls, on pouvait écrire $n,a,b \in \mathbb{N}\setminus${$0$}.

Dans l'Énoncé, plutôt que d'écrire si $n \in \mathbb{N}$ est supérieur à $2$, on pouvait écrire si $n \in \mathbb{N}\setminus${$0, 1$}.

Ces notations ensemblistes seront très utiles dans les prochains articles.

Clémentine Lemarié--Rieusset
