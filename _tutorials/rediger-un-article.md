---
title: Rédiger un article
categories: ""
---

## Ne pas supprimer ce post             ##

Les brouillons doivent avoir nécessairement pour nom de fichier "[titre].md" (/!\ 'titre' ne doit pas comporter de date !)

Pour les "véritables" posts, le titre doit nécessairement être "AAAA-MM-DD-titre.md" avec AAAA l'année, MM le mois, DD le jour, et les fichiers doivent se trouver dans le dossier "_posts/[hierarchie/du/post]", et commencer par :

"
---
title: Example [obligatoire]
date: AAAA-MM-DD [obligatoire : ne doit pas être une date dans le futur, sinon l'article ne sera pas publié]
excerpt: [entête de l'article]
image: [chemin vers l'image à afficher en début d'article, commençant par "/images/"]
---
"

## Petit guide des choses utiles        ##

Pour visualiser les éléments suivants, cliquer sur l'icône "Raw". Si vous avez un peu de mal avec Markdown, vous pouvez écrire votre post là-dedans : http://markdownlivepreview.com/ et visualiser le résultat directement.

Pour une liste des choses possibles : 
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
ou
https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf

J'écris ici seulement l'essentiel : /!\ Ne pas utiliser de crochets à part pour les liens (préférer les parenthèses) /!\

* Faire une liste : à la place de flèches, utiliser *, - ou +. Attention, pour que les listes s'affichent correctement :

<p>
- Item 1<br>
- Item 2<br>
</p>

* Pas de possibilité pour souligner.

* Mettre en gras mot : **mot**

* Mettre en italique mot : *mot*

* Ajouter une image : mettre l'image dans le dossier "images" et écrire:

![Texte alternatif invisible](/images/[chemin-vers-l'image/nom de l'image].[extension])

* Faire un tableau : voir les liens précédents ou https://www.tablesgenerator.com/markdown_tables, https://help.github.com/articles/organizing-information-with-tables/

Exemple : 

| A | B |A ou B|
|---|---|------|
| 0 | 0 |  0   |
| 0 | 1 |  1   |
| 1 | 0 |  1   |
| 1 | 1 |  1   |

(mettre AU MOINS 3 tirets pour séparer titre des colonnes et contenu, sinon le layout hurle)

Pour prévenir les erreurs d'affichage : mettre les tableaux au même endroit, si possible, et mettre au moins 5 lignes entre le début de l'article et le premier tableau (heuristique plus ou moins fiable)

* Ajouter un document PDF : mettre le document dans le dossier "assets/" et écrire
[PDF]({{ site.surl }}/assets/[nom du document].pdf)

* Ajouter une adresse URL vers un post du blog : (le manque d'espace entre les crochets et les parenthèses est important)
Ecrire : [Je suis un lien URL]({{ siteurl }}{% post_url [sous-dossier/AAAA-MM-DD-title] %}) 
(ne modifier que les parties entre crochets : 'sous-dossier' est le sous-dossier du dossier '_posts' qui contient le post. Ne pas marquer l'extension ".md")

* Ajouter une adresse URL : (le manque d'espace entre les crochets et les parenthèses est important)
Ecrire : [Je suis un lien URL](http://www.reflechir.fr)

* Ajouter un passage en LaTeX : 
La syntaxe est un peu différente de LaTeX, voir ici : http://www.gastonsanchez.com/visually-enforced/opinion/2014/02/16/Mathjax-with-jekyll/

