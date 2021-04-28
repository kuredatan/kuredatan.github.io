---
title: "5. Arithmétique"
date: 2017-11-20
excerpt: "L'arithmétique est la branche des mathématiques qui s'intéresse aux nombres (alpha rho iota theta mu o varsigma ou arithmos en grec signifie nombre). Elle est prolongée par la théorie des nombres (il n'y a pas de consensus sur où s'arrête précisément l'arithmétique et où commence précisément la théorie des nombres, mais en général..."
---

La version PDF de cet article est disponible [ici]({{ site.surl }}/assets/Arithmétique.pdf).

L'arithmétique est la branche des mathématiques qui s'intéresse aux nombres ($\alpha \rho \iota \theta \mu o \varsigma$ ou arithmos en grec signifie nombre). Elle est prolongée par la théorie des nombres (il n'y a pas de consensus sur où s'arrête précisément l'arithmétique et où commence précisément la théorie des nombres, mais en général quand on utilise des outils d'algèbre ou d'analyse (voir articles 9 et 10) on parle de théorie des nombres et sinon on parle d'arithmétique). 

## I) Plus grand commun diviseur et plus petit commun multiple. ##

Dans les articles précédents, on démontrait des "énoncés". On va désormais être plus précis : on peut démontrer une proposition, un lemme, un théorème ou un corollaire.  
Un théorème est un énoncé très important, une proposition un énoncé moins important (mais important quand même, sinon on ne se fatiguerait pas à le démontrer), un lemme est un énoncé qui va servir à démontrer un théorème et un corollaire est un énoncé qui va se démontrer grâce à un théorème.  
Certains manuels scolaires désignent des énoncés comme étant des "propriétés", mais dans les cursus universitaires et le monde de la recherche on ne démontre jamais une "propriété" (vous pouvez remplacer vos "propriétés" par des propositions, ou des lemmes si elles servent à démontrer un théorème). 

Commençons par un lemme très important.

__Lemme__ : Toute partie non vide de $\mathbb{N}$ admet un plus petit élément (c'est-à-dire que si $A \subset \mathbb{N}$ n'est pas vide alors il existe $n \in A$ tel que pour tout $a \in A$ $n \leq a$).

_Dém_ : Soit $A \subset \mathbb{N}$. On veut montrer que si $A$ est non vide alors $A$ admet un plus petit élément.
Démontrons la contraposée (cf. article 3) :
Si $A$ n'admet pas de plus petit élément alors $A$ est vide.
Supposons que pour tout $n \in A$ il existe $m \in A$ tel que $m < n$. Montrons par récurrence forte sur $k \in \mathbb{N}$ que $k \not \in A$ ($k$ n'appartient pas à $A$).
$0 \not \in A$ car pour tout $m \in \mathbb{N}$ $0 \leq m$ donc en particulier pour tout $m \in A$ $0 \leq m$.
Supposons que pour tout $l \leq k$ $l \not \in A$.
Pour tout $m \in A$ $k+1 \leq m$ (car sinon $m \in${$0,\dots,k$}) donc $k+1 \not \in A$.
Ainsi, pour tout $k \in \mathbb{N}$, $k \not \in A$, donc $A$ est vide. 

__Remarque__ : Le plus petit élément est unique, car si $a_1$ et $a_2$ sont des plus petits éléments de $A$ alors $a_1 \leq a_2$ (car $a_1$ plus petit élément de $A$ et $a_2 \in A$) et $a_2 \leq a_1$ (car $a_2$ plus petit élément de $A$ et $a_1 \in A$) donc $a_1 = a_2$.

 __Déf__ : $a \in \mathbb{N}$ est divisible par $b \in \mathbb{N}$ s'il existe $c \in \mathbb{N}$ tel que $a = b \times c$. On dit aussi que $a$ est un multiple de $b$ ou que $b$ divise $a$.

__Remarques__ : Si $b$ divise $a$ et si $a \neq 0$ alors $b \leq a$. En effet on a alors $a = b \times c$ avec $c \geq 1$ (on est simplement en train de dire que $b, 2b, 3b$ etc sont supérieurs à $b$).  
Le seul entier divisible par $0$ est $0$ et $0$ est divisible par tous les entiers (car pour tout $c \in \mathbb{N} \ 0 \times c = 0$).  
Tous les entiers sont divisibles par $1$ (car pour tout $c \in \mathbb{N} \ 1 \times c = c$) et $1$ n'est divisible que par $1$.

__Thm__ : Soient $a \in \mathbb{N}$ et $b \in \mathbb{N} \setminus${$0$}. Il existe un unique couple d'entiers naturels $(q,r)$ tel que $0 \leq r < b$ et $a = qb + r$ (division euclidienne de $a$ par $b$).

_Dém_ : Démontrons tout d'abord l'unicité : si $(q,r)$ et $(p,s)$ conviennent, alors $qb + r = pb + s$ et $0 \leq r < b$, $0 \leq s < b$, donc $(q-p)b = s-r$ donc $s-r$ est un multiple de $b$ donc $s-r = 0$ ou $b \leq s-r$ or $s-r \leq s < b$ (voir inégalités ci-dessus) donc $s-r = 0$ donc $(q-p)b = 0$ or $b \neq 0$ donc $q-p = 0$ : ainsi $r = s$ et $q = p$.

Si $a < b$ alors $q = 0$ et $r = a$ conviennent. Sinon, $a - b \geq 0$ donc $0 \not \in A =$ {$n \in \mathbb{N}, a - nb < 0$} $\subset \mathbb{N}$ qui est non vide car $a + 1 \in A$ (car $a + 1 > a$ et $b \geq 1$ (car $b \in \mathbb{N} \setminus${$0$})) donc, avec le lemme précédent, il existe un plus petit élément $n$ de $A$. $a - nb < 0$ (car $n \in A$) et $a - (n-1)b \geq 0$ (car $n-1 < n$ donc $n-1 \not \in A$ car $n$ est le plus petit élément de $A$). Posons $q = n - 1$ et $r = a - qb$. $q \in \mathbb{N}$ et $r$ est un entier vérifiant $0 \leq r < b$.

On peut désormais définir le plus grand commun diviseur de deux entiers :

__Déf__ : Le plus grand commun diviseur de $a \in \mathbb{N}$ et de $b \in \mathbb{N}$, noté pgcd$(a,b)$, est l'entier $d \in \mathbb{N}$ qui vérifie $d$ divise $a$, $d$ divise $b$ et si $c$ divise $a$ et $c$ divise $b$ alors $c$ divise $d$.

Pour que cette définition soit correcte, il faut et il suffit qu'il existe un unique entier $d$ vérifiant ces propriétés (s'il n'y en a pas on est en train de donner un nom à quelque chose qui n'existe pas et s'il y en a plusieurs notre définition est ambigüe car elle désigne plusieurs entiers et pas un seul).

Montrons que cette définition est correcte.

Commençons par l'unicité :
Si $d_1$ et $d_2$ vérifient les propriétés de pgcd de $a$ et de $b$ alors, comme $d_1$ divise $a$ et $d_1$ divise $b$ on a $d_1$ divise $d_2$ et comme $d_2$ divise $a$ et $d_2$ divise $b$ on a $d_2$ divise $d_1$.  
Si $d_1 = 0$ alors comme $d_1$ divise $d_2$ on a $d_2 = 0$. De même, si $d_2 = 0$ alors $d_1 = 0$.  
Si $d_1 \neq 0$ et $d_2 \neq 0$ alors on a $d_1 \leq d_2$ et $d_1 \geq d_2$ (car $d_1$ divise $d_2$ et $d_2$ divise $d_1$) donc on a $d_1 = d_2$.  
On a prouvé l'unicité du pgcd par disjonction de cas.

Montrons à présent l'existence du pgcd.
On remarque que si pgcd($a,b$) existe alors pgcd($b,a$) aussi et pgcd($a,b$) = pgcd($b,a$) (cf. la définition du pgcd (cf signifie confer c'est-à-dire allez voir)).  
On peut donc supposer $b \geq a$ (quitte à échanger $a$ et $b$).  
Si $a=0$ alors $b$ divise $a$ et $b$ divise $b$ et si $c$ divise $a$ et $c$ divise $b$ alors $c$ divise $b$ donc $b = \text{pgcd}(a,b)$.
Sinon, effectuons la division euclidienne de $b$ par $a$ : soient $q_0,r_0 \in \mathbb{N}$ tels que $b = q_0a + r_0$ et $0 \leq r_0 < a$. Montrons que si pgcd$(r_0,a)$ existe alors pgcd$(a,b)$ existe et pgcd$(r_0,a) =$ pgcd$(a,b)$.  
pgcd$(r_0,a)$ divise $r_0$ et $a$ donc divise $b = q_0a + r_0$ et $a$.  
Si $c$ divise $a$ et $b$ alors $c$ divise $r_0 = b - q_0a$ et $a$ donc divise pgcd$(r_0,a)$.  
Ainsi pgcd$(r_0,a) =$ pgcd$(a,b)$.  
Le raisonnement qu'on a mené sur $a$ et $b$ peut être mené sur $r_0$ et $a$ :  
Si $r_0=0$ alors $a = \text{pgcd}(r_0,a) = \text{pgcd}(a,b)$.  
Sinon on effectue la division euclidienne de $a$ par $r_0$ : on a $q_1,r_1 \in \mathbb{N}$ tels que $a = q_1 r_0 + r_1$ et $0 \leq r_1 < r_0$; on a que si pgcd$(r_1,r_0)$ existe alors pgcd$(r_0,a)$ et pgcd$(a,b)$ existent et pgcd$(r_1,r_0) =$ pgcd$(r_0,a) =$ pgcd$(a,b)$.  
Montrons par récurrence qu'on peut construire une suite $(q_n,r_n)$ telle que pour tout $n \geq 1$ si $r_n \neq 0$ on a $r_{n-1} = q_{n+1} r_n + r_{n+1}$ et $r_{n+1} < r_n$, si $r_n = 0$ on a $q_{n+1} = 0$ et $r_{n+1} = 0$.  
On a déjà construit $(q_0, r_0)$ et $(q_1, r_1)$.  
Si on a déjà construit $(q_0,r_0),\dots,(q_n,r_n)$ alors on construit $(q_{n+1},r_{n+1})$ comme suit : si $r_n = 0$ alors on pose $q_{n+1} = 0$ et $r_{n+1} = 0$, sinon on effectue la division euclidienne de $r_{n-1}$ par $r_n$ : il existe un unique couple d'entiers naturels $(q_{n+1},r_{n+1})$ tel que $r_{n-1} = q_{n+1}r_n + r_{n+1}$ et $r_{n+1} < r_n$.  
En appliquant le lemme montré plus haut à l'ensemble des $r_n$ non nuls (qui est non vide car on a supposé que $r_0$ est non nul) on obtient qu'il existe $m \in \mathbb{N}$ tel que $r_m$ est non nul et pour tout $r_n$ non nul, $r_m < r_n$. $r_{m+1}$ est donc nul (car avec la construction faite plus haut si $r_{m+1}$ est non nul alors $r_{m+1} < r_m$ ce qui contredit $r_m < r_{m+1}$).  
En faisant les mêmes raisonnements que plus haut, on a que si $r_m$ existe alors $r_m =$ pgcd$(r_{m+1},r_m) =$ pgcd$(r_m,r_{m-1}) = \dots =$ pgcd$(r_1,r_0) =$ pgcd$(r_0,a) =$ pgcd$(a,b)$. Or $r_m$ existe donc pgcd$(a,b)$ existe.  

__Déf__ : Soit $n \in \mathbb{N} \setminus${$0,1$}. Soient $a_1,\dots,a_n \in \mathbb{N}$. Le plus grand commun diviseur de $a_1,\dots,a_n$, noté pgcd$(a_1,\dots,a_n)$, est l'entier $d \in \mathbb{N}$ qui vérifie $d$ divise $a_1$,..., $d$ divise $a_n$ et si $c$ divise $a_1$,..., $c$ divise $a_n$ alors $c$ divise $d$.

_Exercice_ : Montrer que cette définition est correcte.  
Pour l'existence pour $n > 2$ on pourra vérifier que pgcd(pgcd$(a_1,...,a_{n-1}),a_n$) vérifie les hypothèses de pgcd$(a_1,...,a_n)$.

Démontrons à présent une proposition bien utile.

__Prop__ : Soient $a,b \in \mathbb{N}$. Soit $c \in \mathbb{N} \setminus${$0$}. pgcd$(ca,cb) =$ $c$ pgcd$(a,b)$.

_Dém_ : Notons $d =$ pgcd$(a,b)$. $d$ divise $a$ et $d$ divise $b$ donc $cd$ divise $ca$ et $cd$ divise $cb$.
Ainsi, $cd$ divise pgcd$(ca,cb)$. $c$ divise $ca$ et $c$ divise $cb$ donc $c$ divise pgcd$(ca,cb)$. Soit $e \in \mathbb{N}$ tel que pgcd$(ca,cb) = ce$.
Soient $a',b' \in \mathbb{N}$ tels que $ca = $pgcd$(ca,cb)a'$ et $cb = $pgcd$(ca,cb)b'$.
$ca = cea'$ et $cb = ceb'$. En multipliant par $\frac{1}{c}$ on a :
$a = ea'$ et $b = eb'$ donc $e$ divise $a$ et $b$ donc $e$ divise $d = $pgcd$(a,b)$.
Ainsi pgcd$(ca,cb) = ce$ divise $cd$ or on avait $cd$ divise pgcd$(ca,cb)$ d'où l'égalité.

Définissons à présent le plus petit commun multiple de deux entiers.  

__Déf__ : Le plus petit commun multiple de $a \in \mathbb{N}$ et de $b \in \mathbb{N}$, noté ppcm$(a,b)$, est l'entier $m \in \mathbb{N}$ qui vérifie $a$ divise $m$, $b$ divise $m$ et si $a$ divise $c$ et $b$ divise $c$ alors $m$ divise $c$.  

Montrons que cette définition est correcte.  

Commençons par l'unicité :  
Si $m_1$ et $m_2$ vérifient les propriétés de ppcm de $a$ et de $b$ alors, comme $a$ divise $m_1$ et $b$ divise $m_1$ on a $m_2$ divise $m_1$ et comme $a$ divise $m_2$ et $b$ divise $m_2$ on a $m_1$ divise $m_2$.  
Si $m_1 = 0$ alors comme $m_1$ divise $m_2$ on a $m_2 = 0$. De même, si $m_2 = 0$ alors $m_1 = 0$.  
Si $m_1 \neq 0$ et $m_2 \neq 0$ alors on a $m_1 \leq m_2$ et $m_1 \geq m_2$ (car $m_1$ divise $m_2$ et $m_2$ divise $m_1$) donc on a $m_1 = m_2$.  
On a prouvé l'unicité du ppcm par disjonction de cas.  

Montrons à présent l'existence du ppcm.  
Si $a = 0$ alors $a$ divise $a$, $b$ divise $a$ et si $a$ divise $c$ et $b$ divise $c$ alors $a$ divise $c$, donc $a =$ ppcm$(a,b)$.   
Sinon :  
pgcd$(a,b)$ divise $a$ donc il existe $c \in \mathbb{N}$ tel que $a = c$ pgcd$(a,b)$.  
pgcd$(a,b)$ divise $b$ donc il existe $d \in \mathbb{N}$ tel que $b = d$ pgcd$(a,b)$.  
$cb = cd$ pgcd$(a,b) = ad$ donc $cb$ est un multiple de $b$ et est un multiple de $a$.  
Si $a$ divise $e$ et $b$ divise $e$ alors $cb$ divise $ce$ et $cb = da$ divise $de$ donc :  
$cb$ divise pgcd$(ce,de) = e$ pgcd$(c,d) = e$ car pgcd$(c,d) = 1$ car pgcd$(a,b) =$ pgcd$(c$pgcd$(a,b)$,$d$pgcd$(a,b)) =$ pgcd$(a,b)$ pgcd$(c,d)$ donc pgcd$(c,d) = 0$ ou $1$ et pgcd$(c,d) \neq 0$ car $c \neq 0$ (car $a \neq 0$).  
On a donc $cb =$ ppcm$(a,b)$.  

__Remarque__ : On a montré que ppcm$(a,b) = \frac{ab}{\text{pgcd}(a,b)}$.  

__Déf__ : Soit $n \in \mathbb{N} \setminus \{0,1\}$. Soient $a_1,\dots,a_n \in \mathbb{N}$. Le plus petit commun multiple de $a_1,\dots,a_n$, noté ppcm$(a_1,\dots,a_n)$, est l'entier $m \in \mathbb{N}$ qui vérifie $a_1$ divise $m$,$\dots$, $a_n$ divise $m$ et si $a_1$ divise $c$,$\dots$, $a_n$ divise $c$ alors $m$ divise $c$.  

_Exercice_ : Montrer que cette définition est correcte.  
Pour l'existence pour $n > 2$ on pourra vérifier que ppcm(ppcm$(a_1,...,a_{n-1}),a_n$) vérifie les hypothèses de ppcm$(a_1,...,a_n)$.  

Démontrons une proposition analogue à celle démontrée plus haut.  

__Prop__ : Soient $a,b \in \mathbb{N}$. Soit $c \in \mathbb{N} \setminus \{0\}$. ppcm$(ca,cb) =$ $c$ ppcm$(a,b)$.  

_Dém_ : ppcm$(ca,cb) = \frac{cacb}{\text{pgcd}(ca,cb)} =  \frac{cacb}{c\text{pgcd}(a,b)} = c\frac{ab}{\text{pgcd}(a,b)} =$ $c$ppcm$(a,b)$.  

## II) Lemme de Gauss et théorème d'unicité de la décomposition en facteurs premiers. ##

__Déf__ : Soit $n \in \mathbb{N} \setminus${$0,1$}. On dit que $a_1,\dots, a_n$ sont premiers entre eux si pgcd$(a_1,\dots, a_n) = 1$.

Démontrons le lemme de Gauss (mathématicien de la première moitié du XIXe siècle) puis deux autres lemmes qui en découlent.

__Lemme de Gauss__ : Si $a$ et $b$ sont premiers entre eux et si $a$ divise $bc$ alors $a$ divise $c$. 

_Dém_ : $a$ divise $ac$ et $a$ divise $bc$ donc $a$ divise pgcd$(ac,bc) =$ pgcd$(a,b)c = c$ car pgcd$(a,b) = 1$ (on a utilisé la proposition précédente et $ca = ac$ etc).

__Lemme__ : Si $a$ et $b$ sont premiers entre eux tels que $a$ divise $c$ et $b$ divise $c$ alors $ab$ divise $c$.

_Dém_ : $b$ divise $c$ donc il existe $d \in \mathbb{N}$ tel que $c = bd$. $a$ divise $c = bd$ et $a$ et $b$ sont premiers entre eux donc, avec le lemme précédent, $a$ divise $d$ donc il existe $e \in \mathbb{N}$ tel que $d = ae$ donc $c = bd = bae = abe$ donc $ab$ divise $c$.  

__Lemme__ : Soit $p$ un nombre premier. Soit $n \in \mathbb{N} \setminus${$0$}. Soient $a_1,\dots,a_n \in \mathbb{N}$. Si $p$ divise $a_1 \times \dots \times a_n$ alors $p$ divise $a_1$ ou ... ou $p$ divise $a_n$.

_Exercice_ : Démontrer ce lemme en utilisant le lemme de Gauss et le fait que si $p$ est un nombre premier et $c \in \mathbb{N}$ alors pgcd$(p,c) = 1$ ou $p$ (cette dernière affirmation se démontre aisément avec la définition de nombre premier (voir article 2)).

_Notation_ : On note min$(x_1,\dots,x_n)$ le minimum des entiers $x_1,\dots,x_n$, c'est-à-dire le plus petit d'entre eux. On note max$(x_1,\dots,x_n)$ le maximum des entiers $x_1,\dots,x_n$, c'est-à-dire le plus grand d'entre eux.  

Dans l'article 2 on avait montré l'existence de la décomposition en facteurs premiers; montrons-en à présent l'unicité.  

__Thm__ : Soient $m,n \in \mathbb{N} \setminus${$0$}. Soient $p_1 \leq \dots \leq p_m, \, q_1 \leq \dots \leq q_n$ des nombres premiers. Si $p_1 \times \dots \times p_m = q_1 \times \dots \times q_n$ alors $m = n$, $p_1 = q_1, \dots, p_m = q_m$. C'est l'unicité de la décomposition en facteurs premiers.

_Dém_ : Raisonnons par récurrence sur le maximum de $m$ et de $n$, noté max$(m,n)$ (max$(m,n) = m$ si $m \geq n$ et $n$ sinon).

Si max$(m,n) = 1$ alors on a $m = 1$ et $n = 1$ donc $m = n$ et $p_1 = q_1$.

Supposons le résultat établi pour $k \in \mathbb{N} \setminus${$0$}.  
Soient $m,n \in \mathbb{N} \setminus${$0$} tels que max$(m,n) = k+1$.  
Si $p_1 < q_1$ alors $p_1 \not \in$ {$q_1,\dots,q_n$} or $p_1$ divise $q_1 \times \dots \times q_n$ donc avec le lemme précédent $p_1$ divise $q_1$ ou ... ou $p_1$ divise $q_n$ (car $p_1$ premier) donc $p_1 = q_1$ ou ... ou $p_1 = q_n$ (car $q_1,\dots,q_n$ premiers et $p_1 \neq 1$) ce qui contredit $p_1 \not \in$ {$q_1,\dots,q_n$}.  
(En d'autres mots, $p_1 < q_1$ implique $p_1 \not \in$ {$q_1,\dots,q_n$} et $p_1 \in$ {$q_1,\dots,q_n$} proposition toujours fausse, d'où $p_1 \geq q_1$)  
Si $q_1 < p_1$ alors $q_1 \not \in$ {$p_1,\dots,p_m$} or $q_1$ divise $p_1 \times \dots \times p_m$ donc avec le lemme précédent $q_1$ divise $p_1$ ou ... ou $q_1$ divise $p_m$ (car $q_1$ premier) donc $q_1 = p_1$ ou ... ou $q_1 = p_m$ (car $p_1,\dots,p_m$ premiers et $q_1 \neq 1$) ce qui contredit $q_1 \not \in$ {$p_1,\dots,p_m$}.  
Ainsi $p_1 = q_1$. On a donc $p_2 \times \dots \times p_m = q_2 \times \dots \times q_n$ donc, comme à gauche on a $m-1$ termes et à droite $n-1$ et que max$(m-1,n-1) = $ max$(m,n) - 1 = k$, par hypothèse de récurrence $m = n$ et $p_2 = q_2$,..., $p_m = q_m$.

_Notation_ : Si $x \in \mathbb{R}$ et $n \in \mathbb{N} \setminus${$0$} on note $x^n = x \times \dots \times x \ n$ fois ($x^1 = x, x^2 = x \times x, x^3 = x \times x \times x$ etc). Si $x \in \mathbb{R}$ on note $x^0 = 1$.  
$x^n$ se prononce "$x$ puissance $n$" (et on dit souvent "$x$ au carré" plutôt que "$x$ puissance $2$" et "$x$ au cube" plutôt que "$x$ puissance $3$").  

Puisqu'on a établi l'unicité de la décomposition en facteurs premiers, on peut définir correctement la valuation $p$-adique d'un entier naturel non nul :  

__Déf__ : Soit $p$ un nombre premier. Soit $n \in \mathbb{N} \setminus \{0,1\}$. La valuation $p$-adique de $n$ est la puissance à laquelle apparaît $p$ dans la décomposition en facteurs premiers de $n$, c'est-à-dire que si $n = p_1^{a_1} \times \dots \times p_m^{a_m}$ avec $p_1, \dots, p_m$ des nombres premiers distincts (c'est-à-dire tous différents les uns des autres), alors si $p = p_i$ la valuation $p$-adique de $n$ est $a_i$ et si $p \not \in \{p_1,\dots,p_m\}$ (c'est-à-dire $p$ différent de tous les $p_i$) alors la valuation $p$-adique de $n$ est nulle (car $p^0 = 1$).  La valuation $p$-adique de $1$ est nulle. La valuation $p$-adique de $n$ est notée $v_p(n)$.  

_Exemples_ : $v_2(2) = 1$ et pour tout $p$ premier différent de $2, v_2(p) = 0$.  
$12 = 2^2 \times 3$ donc $v_2(12) = 2, v_3(12) = 1$ et pour tout $p$ premier différent de $2$ et de $3$, $v_p(12) = 0$.  

__Remarque__ : Si pour tous les nombres premiers $p$ $v_p(n) = v_p(m)$ alors $n = m$ (cf. la décomposition en facteurs premiers).  

__Prop__ : Soient $a,b \in \mathbb{N} \setminus \{0\}$. Soit $p$ premier. $v_p(ab) = v_p(a) + v_p(b)$.  

_Dém_ : Si $a = 1$ alors $v_p(a) = 0$ et on a bien $v_p(ab) = v_p(b) = v_p(a) + v_p(b)$.  
Si $b = 1$ alors $v_p(b) = 0$ et on a bien $v_p(ab) = v_p(a) = v_p(a) + v_p(b)$.  
Si $a \neq 1$ et $b \neq 1$, on les décompose en facteurs premiers :  
$a = p_1^{v_{p_1}(a)} \times \dots \times p_m^{v_{p_m}(a)}$ et $b = p_1^{v_{p_1}(b)} \times \dots \times p_m^{v_{p_m}(b)}$ (les valuations $p$-adiques peuvent être nulles parce qu'on a mis tous les facteurs premiers de $a$ et de $b$)  
$ab = p_1^{v_{p_1}(a)} \times p_1^{v_{p_1}(b)} \times \dots \times p_m^{v_{p_m}(a)} \times p_m^{v_{p_m}(b)} = p_1^{v_{p_1}(a) + v_{p_1}(b)} \times \dots \times p_m^{v_{p_m}(a) + v_{p_m}(b)}$  
donc $v_{p_1}(ab) = v_{p_1}(a) + v_{p_1}(b), \dots, v_{p_m}(ab) = v_{p_m}(a) + v_{p_m}(b)$, et pour tout $p$ premier qui n'appartient pas à $\{p_1,\dots,p_m\}$ on a : $v_p(ab) = 0 = 0 + 0 = v_p(a) + v_p(b)$.  
 
__Prop__ : Soient $a,b \in \mathbb{N} \setminus \{0\}$. $a$ divise $b$ si et seulement si pour tout nombre premier $p$ $v_p(a) \leq v_p(b)$.  

_Dém_ : Supposons que $a$ divise $b$.  
Il existe $c \in \mathbb{N} \setminus \{0\}$ tel que $b = ac$. Soit $p$ premier.  
D'après la proposition précédente, $v_p(b) = v_p(a) + v_p(c) \geq v_p(a)$ (car $v_p(c) \in \mathbb{N}$ (cf. la définition de la valuation $p$-adique) donc $v_p(c) \geq 0$).  
Supposons que pour tout nombre premier $p$ $v_p(a) \leq v_p(b)$.  
Si $a = b$ on a bien $a$ divise $b$. Sinon :  
Soient $p_1,\dots,p_m$ les nombres premiers $p$ tels que $v_p(a) < v_p(b)$ (il n'y en a qu'un nombre fini car $v_p(a) \neq 0$ ou $v_p(b) \neq 0$ que pour un nombre fini de $p$)  
$b = a \times p_1^{v_{p_1}(b) - v_{p_1}(a)} \times \dots \times p_m^{v_{p_m}(b) - v_{p_m}(a)}  
(cf. les décompositions en facteurs premiers de $a$ et de $b$)  
donc $a$ divise $b$.  

__Prop__ : Soient $x_1,\dots,x_n \in \mathbb{N}$. Soit $p$ premier. $v_p$(pgcd$(x_1,\dots,x_n)$) = min$(v_p(x_1),\dots,v_p(x_n))$.  

_Dém_ : Soit $d$ le nombre tel que pour tout $p$ premier $v_p(d) =$ min$(v_p(x_1),\dots,v_p(x_n))$ (un tel nombre existe car il n'y a qu'un nombre fini de $p$ pour lesquels $v_p(x_1) \neq 0$ et si $v_p(x_1) = 0$ alors min$(v_p(x_1),\dots,v_p(x_n)) = 0$). D'après la proposition précédente, $d$ divise $x_1,\dots, d$ divise $x_n$.  
Soit $c$ tel que $c$ divise $x_1,\dots, c$ divise $x_n$. D'après la proposition précédente, pour tout $p$ premier : $v_p(c) \leq v_p(x_1),\dots, v_p(c) \leq v_p(x_n)$ donc $v_p(c) \leq$ min$(v_p(x_1),\dots,v_p(x_n)) = v_p(d)$.  
D'après la proposition précédente, on a donc $c$ divise $d$.  
$d$ est donc le plus grand commun diviseur de $x_1,\dots,x_n$.  

__Prop__ : Soient $x_1,\dots,x_n \in \mathbb{N}$. Soit $p$ premier. $v_p$(ppcm$(x_1,\dots,x_n)$) = max$(v_p(x_1),\dots,v_p(x_n))$.  

_Dém_ : Soit $m$ le nombre tel que pour tout $p$ premier $v_p(m) =$ max$(v_p(x_1),\dots,v_p(x_n))$ (un tel nombre existe car il n'y a qu'un nombre fini de $p$ pour lesquels $v_p(x_1) \neq 0$ ou $\dots$ ou $v_p(x_n) \neq 0$ et si $v_p(x_1) = 0,\dots,v_p(x_n) = 0$ alors max$(v_p(x_1),\dots,v_p(x_n)) = 0$). D'après une proposition plus haut, $x_1$ divise $m,\dots, x_n$ divise $m$.  
Soit $c$ tel que $x_1$ divise $c,\dots, x_n$ divise $c$. D'après une proposition plus haut, pour tout $p$ premier : $v_p(x_1) \leq v_p(c),\dots, v_p(x_n) \leq v_p(c)$ donc $v_p(c) \geq$ max$(v_p(x_1),\dots,v_p(x_n)) = v_p(m)$.  
D'après une proposition plus haut, on a donc $m$ divise $c$.  
$m$ est donc le plus petit commun multiple de $x_1,\dots,x_n$.  

__Prop__ : Soient $x_1,\dots,x_n,a_1,\dots,a_n \in \mathbb{N}$. Si pgcd$(x_1,\dots,x_n) = 1$ alors pgcd$(x_1^{a_1},\dots,x_n^{a_n}) = 1$.  

_Dém_ : D'après la remarque plus haut, il suffit de montrer que pour tout nombre premier $p$, $v_p($pgcd$(x_1^{a_1},\dots,x_n^{a_n})) = 0$.  
Soit $p$ un nombre premier. D'après une proposition plus haut :  
$v_p$(pgcd$(x_1^{a_1},\dots,x_n^{a_n}))) =$ min$(v_p(x_1^{a_1}),\dots,v_p(x_n^{a_n})) =$ min$(a_1v_p(x_1),\dots,a_nv_p(x_n))$  
(cf. la définition de puissance et la proposition plus haut selon laquelle la valuation $p$-adique d'un produit est la somme des valuations $p$-adiques)  
or $0 = v_p(1) = v_p($pgcd$(x_1,\dots,x_n)) =$ min($v_p(x_1),\dots,v_p(x_n)$) donc il existe $i \in \{1,\dots,n\}$ tel que $v_p(x_i) = 0$ donc $a_iv_p(x_i) = 0$  
donc $v_p$(pgcd$(x_1^{a_1},\dots,x_n^{a_n}))) = 0$.  


## III) Triplets pythagoriciens et cas $n = 3$ et $n = 4$ du grand théorème de Fermat. ##

En géométrie, le théorème de Pythagore stipule que si $x,y,z$ sont les longueurs des côtés d'un triangle rectangle, avec $z$ la longueur de l'hypoténuse, alors $x^2 + y^2 = z^2$ (voir l'article 7. Géométrie). La réciproque du théorème de Pythagore stipule que si $x,y,z$ sont les longueurs des côtés d'un triangle et vérifient $x^2 + y^2 = z^2$ alors ce triangle est rectangle et son hypoténuse est le côté de longueur $z$. On peut se demander quels triplets d'entiers naturels non nuls $(x,y,z)$ vérifient l'équation $x^2 + y^2 = z^2$ (ce qui revient à se demander quels sont les triangles rectangles dont les longueurs des côtés sont des entiers). On appelle de tels triplets des "triplets pythagoriciens".

 _Exo_ : Résolution de l'équation de Pythagore $x^2 + y^2 = z^2$ avec $x,y,z \in \mathbb{N} \setminus${$0$}.

1) Montrer que $(x,y,z)$ est solution si et seulement si, en notant $d =$ pgcd$(x,y,z)$, $(\frac{x}{d},\frac{y}{d},\frac{z}{d})$ est solution.

2) Soit $(x,y,z)$ une solution de pgcd 1. Déterminer le reste dans la division euclidienne de $z^2$ par 4 (en considérant les différentes possibilités pour ceux de $x^2$ et $y^2$) et en déduire que $z$ est impair, $x$ ou $y$ est pair et l'autre est impair.

3) Soit $(x,y,z)$ une solution de pgcd 1. Si $x$ est pair et $y$ est impair, montrer que pgcd($\frac{z-y}{2},\frac{z+y}{2}) = 1$. En déduire, puisque $(z-y)(z+y) = z^2 - y^2 = x^2$, que $\frac{z-y}{2}$ et $\frac{z+y}{2}$ sont des carrés d'entiers, puis une expression de $x$, $y$ et $z$.

4) Donner toutes les solutions de l'équation $x^2 + y^2 = z^2$ dans $\mathbb{N} \setminus${$0$}.

Cet exercice et les suivants seront corrigés dans l'article 5 bis. Si vous bloquez sur une question n'hésitez pas à la sauter pour faire les autres questions (quitte à réessayer plus tard, souvent la nuit porte conseil).

__Remarque__ : Si $x,y,z \in \mathbb{Z} \setminus \{0\}$ vérifient $x^2 + y^2 = z^2$, en remplaçant $x$ par $-x$ ou $y$ par $-y$ ou $z$ par $-z$ on a encore $x^2 + y^2 = z^2$ et $x,y,z \in \mathbb{Z} \setminus \{0\}$. En changeant les signes qu'il faut, on se ramène à $x,y,z \in \mathbb{N} \setminus \{0\}$, et l'exercice précédent nous donne donc tous les $x,y,z \in \mathbb{Z} \setminus \{0\}$ qui vérifient $x^2 + y^2 = z^2$ en changeant des signes (explicitez ces solutions).  

Une question que l'on peut naturellement se poser est de savoir s'il existe $x,y,z \in \mathbb{N} \setminus${$0$} tels que $x^3 + y^3 = z^3$ ou $x^4 + y^4 = z^4$ etc. Pierre de Fermat (1601-1665) a énoncé la conjecture suivante (appelée grand théorème de Fermat ou dernier théorème de Fermat) : pour tout $n \geq 3$, il n'existe pas $x,y,z \in \mathbb{N} \setminus${$0$} tels que $x^n + y^n = z^n$. Andrew Wiles (1953-) l'a démontrée en 1995 grâce à des mathématiques très sophistiquées (le documentaire [Fermat's Last Theorem](http://topdocumentaryfilms.com/fermats-last-theorem/) présente l'aventure de la preuve au grand public). Les cas $n = 3$ et $n = 4$ sont faciles à montrer et font l'objet des exercices suivants. Ensuite il suffit de montrer le résultat pour $n \geq 5$ premier (prouvez-le ! ce sera corrigé dans l'article 5 bis, tout comme les exercices suivants), c'est ce qu'a fait Wiles (je dis "il suffit" mais c'est très difficile (sinon le grand théorème de Fermat n'aurait pas attendu plus de 300 ans avant d'être prouvé)).  

Pour le cas $n = 4$ on montre même qu'il n'y a pas de solution dans $\mathbb{N} \setminus${$0$} à $x^4+y^4=z^2$ (ce qui implique le cas $n = 4$ en prenant $z$ un carré d'entier).

Il suffit de montrer qu'il n'y a pas de solution dans $\mathbb{N} \setminus \{0\}$ car les exposants ($4$,$4$ et $2$) sont pairs (c'est-à-dire divisibles par $2$;  comme dans la remarque plus haut, on peut changer les signes de $x$, $y$, $z$ pour avoir des entiers positifs).  

_Exo_ : Il n'y a pas de solution dans $\mathbb{N} \setminus${$0$} à $x^4+y^4=z^2$.

1) Se ramener à $x,y,z$ de pgcd $1$.

Indication : en notant $d$ le pgcd de $x,y,z$, montrer que $\frac{x}{d}, \frac{y}{d}, \frac{z}{d^2}$ sont de pgcd $1$.

2) Vérifier que si $x,y,z$ est solution de $x^4+y^4=z^2$ et de pgcd $1$ alors $(x^2,y^2,z)$ est un triplet pythagoricien de pgcd $1$ et en déduire qu'il existe $u,v \in \mathbb{N} \setminus \{0\}$ de pgcd $1$ tels que $x^2 = 2uv, y^2 = v^2 - u^2, z = v^2 + u^2$ (quitte à échanger $x$ et $y$).

Indication : dans la preuve de l'exercice sur les triplets pythagoriciens, vous devriez avoir trouvé de tels $u,v$ mais sans avoir prouvé qu'ils sont de pgcd $1$; en revanche vous devriez avoir prouvé (avec les notations de l'exercice sur les triplets pythagoriciens) que $u^2 = \frac{z-y}{2}$, $v^2 = \frac{z+y}{2}$ et pgcd$(\frac{z-y}{2},\frac{z+y}{2}) = 1$ (dans les notations ici il faut remplacer $y$ par $y^2$), et vous devriez pouvoir en déduire que pgcd$(u,v) = 1$.  

3) Montrer que $v$ est impair et que $u$ est pair puis en déduire que $v$ est un carré d'entier et que $u$ est le produit de $2$ et d'un carré d'entier.

4) Vérifier que $(u,y,v)$ est un triplet pythagoricien de pgcd $1$ et, en utilisant les questions précédentes, en déduire qu'il existe $x',y',z' \in \mathbb{N} \setminus \{0\}$ de pgcd $1$ tels que $x'^4 + y'^4 = z'^2$ et $z' < z$. 

5) Utiliser le fait que toute partie non vide de $\mathbb{N}$ admet un plus petit élément pour conclure. 

__Prop__ : Il n'y a pas de solution dans $\mathbb{Z} \setminus${$0$} à $x^3+y^3=z^3$.

Je connais deux preuves de cette proposition; l'une n'utilise que des outils arithmétiques mais est assez fastidieuse (voir [ici](http://fermatslasttheorem.blogspot.com/2005/05/fermats-last-theorem-proof-for-n3.html) pour cette preuve) et l'autre utilise des nombres complexes; cette dernière preuve sera faite dans l'article 19 Théorie des nombres.

Clémentine Lemarié--Rieusset
