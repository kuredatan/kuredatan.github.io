---
title: "Introduction aux structures de données (corrigé)"
date: 2018-02-18
excerpt: "Exercice de programmation

En OCaml, les listes et les tableaux sont évidemment présents, et ces deux structures sont implémentées de façon différente (contrairement à Python, par exemple). (Re)programmez les primitives de ces deux structures de données : initialisation d'un objet sans données, suppression d'un élément à une position donnée (sans erreur, donc en particulier en vérifiant que l'objet contient effectivement au moins un élément !), ajout d'un élément à une position donnée, retour de la valeur Vrai (true en OCaml) d'un élément dans l'objet..."
---

## Exercice de programmation ##

En OCaml, les listes et les tableaux sont évidemment présents, et ces deux structures sont implémentées de façon différente (contrairement à Python, par exemple). (Re)programmez les primitives de ces deux structures de données : initialisation d'un objet sans données, suppression d'un élément à une position donnée (sans erreur, donc en particulier en vérifiant que l'objet contient effectivement au moins un élément !), ajout d'un élément à une position donnée, retour de la valeur 'Vrai' ("true" en OCaml) d'un élément dans l'objet s'il y est présent, sinon de la valeur 'Faux' ("false"). Ne pas utiliser les fonctions déjà présentes en OCaml...

Il y a de multiples manières, plus ou moins optimisées, d'effectuer les actions précédemment citées. Ici, la lisibilité et la compréhension ont été privilégiées, au détriment de l'efficacité et de la concision. Le moyen de vérifier si les fonctions écrites effectuent **vraiment** le but que l'on leur a fixé est soit, si on est matheux, de prouver la **correction** de la fonction, en montrant qu'elle vérifie des propriétés qui imposent que le résultat soit celui attendu; soit de __déboguer__ à la main, en testant sur des exemples **variés** et **nombreux** que la fonction retourne le bon résultat : vérifier les cas limites en particulier, par exemple, quand la liste est vide, ou quand on cherche à atteindre le dernier élément du tableau, et surtout, vérifier que la fonction puisse donner une réponse cohérente dans toutes les situations (surtout quand vous lui demandez de faire une chose incohérente, comme supprimer un élément qui n'existe pas). La première méthode "formelle" de test sera présentée dans un prochain article d'informatique.

Pour les listes :

```
liste_vide = [];;

// Suppression d'un élément à la position/indice n
let rec suppression_liste liste n = match liste with
| [] -> failwith "La liste fournie en argument a moins de n éléments."
| _ when n=0 -> queue liste
| _ -> (tete liste) :: suppression_liste (queue liste) (n-1);;

// Ajout d'un élément à la position/indice n
let rec ajout_liste liste element n = match liste with
| [] when n=0 -> [element]
| ls when n=0 -> element :: ls
| [] -> failwith "La liste fournie en argument a moins de n éléments."
| ls -> (tete ls) :: (ajout_liste (queue liste) element (n-1));;

// Cherche un élément dans la liste
let rec rechercher_liste liste element = match liste with
| [] -> false
| ls when (tete ls)=element -> true
| ls -> rechercher_liste (queue liste) element;;
```

Pour les tableaux :

```
tableau_vide = [||];;

// Suppression d'un élément à la position/indice n
let suppression_tableau tableau n =
	let len = longueur_tableau tableau in
	if (len == 0)
	then failwith "Le tableau est vide !";
	if (len <= n)
	then failwith "Le tableau a moins de n éléments.";
	let nouveau_tableau = creer_tableau tableau.(0) (len-1) in
	let idx = ref 0 in
	let i = ref 0 in
	while (!i < len) do
		if (not (!i == n))
		then
			(nouveau_tableau.(!idx) <- tableau.(!i);
			idx := !idx + 1);
		i := !i + 1;
	done;
	nouveau_tableau;;

// Ajout d'un élément à la position/indice n
let ajout_tableau tableau n element = 
	let len = longueur_tableau tableau in
	if (len + 1 < n)
	then failwith "Le tableau a moins de n éléments.";
	let nouveau_tableau = creer_tableau tableau.(0) (len+1) in
	let idx = ref 0 in
	let i = ref 0 in
	while (!i < len+1) do
		if (!i == n)
		then nouveau_tableau.(!i) <- element
		else (nouveau_tableau.(!i) <- tableau.(!idx); idx := !idx + 1);
		i := !i + 1;
	done;
	nouveau_tableau;;

// Cherche un élément dans le tableau
let rechercher_tableau tableau element =
	let len = longueur_tableau tableau in
	let i = ref 0 in
	let trouve = ref false in
	while (!i < len) do
		while (not !trouve && !i < len) do
			if (tableau.(!i) == element)
			then trouve := true;
			i := !i + 1;
		done;
		i := !i + 1;
	done;
	!trouve;;
```

## Quand utiliser une liste ? Quand utiliser un tableau ? ##

+ __Exemple 1__ : La structure à utiliser est la liste : on peut facilement ajouter des éléments à la liste sans avoir à recréer une nouvelle liste. 

+ __Exemple 2__ : La structure à utiliser est le tableau : on peut accéder directement à un élément par son indice, sans avoir à parcourir l'ensemble du tableau pour ce faire.

## Bonus ##

Une liste peut être convertie en tableau, et vice-versa. Avec vos nouvelles connaissances de programmation, vous devriez être capable de convertir une liste en tableau et inversement. Vous ne voyez pas comment ? Laissez-vous un temps de réflexion, puis jetez un coup d'oeil à la solution ci-dessous.

```
// Obtient la longueur d'une liste 
let rec longueur_liste liste = match liste with
|[]-> 0
|ls -> 1 + longueur_liste (queue ls);;

// Convertit une liste en tableau
let liste_en_tableau liste =
	let len = longueur_liste liste in
	if (len == 0)
	then [||]
	else 
		let t = creer_tableau (tete liste) len in
		let i = ref 0 in
		let rec aux liste = match liste with
			|[] -> t
			|h::q -> t.(!i) <- h; i := !i + 1; aux (queue liste)
		in aux liste;;

// Convertit un tableau en liste
let tableau_en_liste tableau = 
	let len = longueur_tableau tableau in
	let rec aux i = match i with
		| i when i=len -> []
		| i -> tableau.(i) :: aux (i+1)
	in aux 0;;
```

