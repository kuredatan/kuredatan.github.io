---
title: "4. Le raisonnement par analyse-synthèse"
date: 2017-03-01
excerpt: "Le raisonnement par analyse-synthèse est utilisé pour déterminer l'ensemble des solutions à un problème. La phase d'analyse donne des conditions nécessaires pour être solution (elle met en évidence des candidats) et la phase de synthèse vérifie quelles sont les solutions (elle détermine quels candidats sont solutions)..."
---

La version PDF de cet article est disponible [ici]({{ site.surl }}/assets/Analyse-Synthèse.pdf).

Le raisonnement par analyse-synthèse est utilisé pour déterminer l'ensemble des solutions à un problème. La phase d'analyse donne des conditions nécessaires pour être solution (elle met en évidence des "candidats") et la phase de synthèse vérifie quelles sont les solutions (elle détermine quels "candidats" sont solutions).

Définition : Une fonction $f$ de $\mathbb{R}$ dans $\mathbb{R}$ est paire si pour tout $x$ dans $\mathbb{R}$ $f(-x) = f(x)$.

Exemple : Toute fonction constante est paire (si $f$ associe le même nombre à tout réel alors, en particulier, pour tout réel $x$ elle associe le même nombre à $x$ et à son opposé $-x$).

Définition : Une fonction $f$ de $\mathbb{R}$ dans $\mathbb{R}$ est impaire si pour tout $x$ dans $\mathbb{R}$ $f(-x) = -f(x)$.

Exemple : La fonction signe, qui à un nombre strictement négatif associe $-1$, à $0$ associe $0$ et à un nombre strictement positif associe $1$, est impaire (car l'opposé d'un nombre strictement positif est un nombre strictement négatif (et vice-versa) et l'opposé de $0$ est $0$). 

Énoncé : Toute fonction de $\mathbb{R}$ dans $\mathbb{R}$ s'écrit de manière unique comme la somme d'une fonction paire et d'une fonction impaire.

Démontrons cet énoncé par analyse-synthèse.

Soit $f$ une fonction de $\mathbb{R}$ dans $\mathbb{R}$.

Analyse : Supposons $f = p + i$ avec $p$ une fonction paire et $i$ une fonction impaire.

Pour tout $x$ dans $\mathbb{R}$ : $f(x) = p(x) + i(x)$ et $f(-x) = p(-x) + i(-x) = p(x) - i(x)$.

En sommant ces deux égalités, on obtient $f(x) + f(-x) = 2 \times p(x)$.

En soustrayant la deuxième égalité à la première on a :
$$f(x) - f(-x) = 2 \times i(x).$$

Il y a donc au plus un couple $(p,i)$ de fonctions respectivement paire et impaire telles que $f = p+i$.

Synthèse : Posons pour tout $x$ dans $\mathbb{R}$ : 
$$p(x) = \frac{f(x)+f(-x)}{2} \ \text{ et }\  i(x) = \frac{f(x)-f(-x)}{2}.$$

$p(x) + i(x) = \frac{f(x)+f(-x)+f(x)-f(-x)}{2} = \frac{2f(x)}{2} = f(x)$

$p(-x) = \frac{f(-x)+f(x)}{2} = p(x)$

$i(-x) = \frac{f(-x)-f(x)}{2} = -i(x)$

$(p,i)$ est donc bien un couple de fonctions respectivement paire et impaire telles que $f = p+i$.

## Le raisonnement par disjonction de cas. ##

Le raisonnement par disjonction de cas consiste à prouver $A \Rightarrow B$ en prouvant $A_1 \Rightarrow B$, ..., $A_n \Rightarrow B$ avec $A_1,...,A_n$ tels que $A$ correspond à $A_1$ ou $...$ ou $A_n$.

Définition : Soit $n \in \mathbb{N}$. $n$ est pair s'il existe $l \in \mathbb{N}$ tel que $n = 2 \times l$, impair sinon.

Remarque : Si $n$ est pair alors $n+2$ est pair. Un nombre impair est donc de la forme $2 \times l + 1$ avec $l \in \mathbb{N}$.

Énoncé : Soit $n \in \mathbb{N}$. $n \times (n+1)$ est pair.

Ici, on veut montrer $A \Rightarrow B$ où $A$ est la proposition toujours vraie et $B$ est $n \times (n+1)$ est pair. On remarque que $A$ correspond à "$n$ est pair ou $n$ est impair" donc il suffit de montrer que si $n$ est pair alors $n \times (n+1)$ est pair et que si $n$ est impair alors $n \times (n+1)$ est pair.

Cas $n$ pair :

Il existe $l \in \mathbb{N}$ tel que $n = 2 \times l$. $n \times (n+1) = 2 \times l \times (n+1)$ et $l \times (n+1) \in \mathbb{N}$ donc $n \times (n+1)$ est pair.

Cas $n$ impair :

$n$ est impair donc $n+1$ est pair (voir Remarque). Ainsi, il existe $l \in \mathbb{N}$ tel que $n+1 = 2 \times l$. $n \times (n+1) = 2 \times l \times n$ et $l \times n \in \mathbb{N}$ donc $n \times (n+1)$ est pair.

On a montré que $n \times (n+1)$ est pair.

Pour montrer que le raisonnement par disjonction de cas est correct, on commence par montrer que si $A$ correspond à $A_1$ ou $A_2$ alors $A \Rightarrow B$ est équivalent à ($A_1 \Rightarrow B$ et $A_2 \Rightarrow B$) c'est-à-dire que la table de vérité de $(A_1$ ou $A_2) \Rightarrow B$ est la même que celle de ($A_1 \Rightarrow B$ et $A_2 \Rightarrow B$) (voir article 3). Ensuite on montre que si $A$ correspond à $A_1$ ou ... ou $A_n$ alors $A \Rightarrow B$ est équivalent à ($A_1 \Rightarrow B$ et ... et $A_n \Rightarrow B$) par récurrence (voir article 2) : $A$ correspond à $A_1$ ou ($A_2$ ou ... ou $A_n$) donc $A \Rightarrow B$ est équivalent à ($A_1 \Rightarrow B$ et $(A_2$ ou ... ou $A_n \Rightarrow B$)) et on utilise $(A_2$ ou ... ou $A_n \Rightarrow B$)) équivalent à ($A_2 \Rightarrow B$ et ... et $A_n \Rightarrow B$) comme hypothèse de récurrence.

Clémentine Lemarié--Rieusset

