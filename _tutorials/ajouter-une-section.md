---
title: "Ajouter une (sous) section"
---

## Pour ajouter une section [section] ##
1) Ajouter un dossier nommé [section] dans le dossier posts_
2) Modifier le fichier _config.yml de la façon suivante :
"
defaults:
  -
    scope:
      path:             "_posts/"
      type:             "posts"
    values:
      layout:           "post"
  -
    scope:
      path:             "_posts/actualites"
    values:
      title:            "Actualités"
      category:         actualités
  -
    scope:
      path:             "_posts/sciences"
    values:
      title:            "Sciences"
      category:         sciences
  -
[...]"
et ajouter
"
  -
    scope:
      path:             "_posts/[section]"
    values:
      title:            "[Section]"
      category:         [section]
"

Si c'est une sous-section à ajouter, ajouter :
"
  -
    scope:
      path:             "_posts/[sous-section]"
    values:
      title:            "[Sous-section]"
      category:         ["[sous-section]","[section associée]"]
"

3) Ajouter à la variable "categories" (en haut du fichier) "[section]" (idem pour une sous-section).

4) Si c'est une section, alors ajouter à la variable "sections" "[section]".

5) Si les posts de cette (sous-)section doivent être montrés dans l'ordre anti-chronologique, ajouter le nom de la section à la variable "antichrono".

6) Ajouter le titre de la (sous-)section à la variable "pagenames".

7) Si c'est une section, alors ajouter à la variable "sectionnames" le titre de la section.



