# Les admonitions

> [!note]
>  Le plugin [mkdocs-callouts](https://pypi.org/project/mkdocs-callouts/) permet de convertir les [callouts](https://help.obsidian.md/How+to/Use+callouts) d'Obsidian en [admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/) de MkDocs.
> 
> Il faut l'installer dans le fichier `ci.yml` :
> `- run: pip install mkdocs-callouts`
> 
> Puis déclarer dans le fichier `mkdocs.yml` :
> ```yaml
> markdown_extensions:
>  - nl2br
>  - admonition
>  - pymdownx.details
>  - pymdownx.superfences
>
>plugins:
>  - search
>  - callouts
>```
>

>[!warning | left] 
>Il faut utiliser les valeurs par défaut  `note`, `abstract`, `info`, `tip`, `success`, `question`, `warning`, `failure`, `danger`, `bug`, `example`, `quote`, **mais pas leurs alias !**

>[!bug | right]
> Avec ce code `[!bug | right]` cet avertissement s'aligne à droite dans MkDocs,
> et la précédente à gauche avec le code `[!warning | left]`,
> mais ce n'est pas le cas dans Obsidian...

>[!abstract]
>`[!abstract]` 
> Pour un résumé, un sommaire, un développement trop long à lire...

>[!example]+
>`[!example]+`
> Ici un exemple d'avertissement repliable déplié par défaut et ci-dessous des avertissements dépliables tous repliés par défaut...

>[!danger]- 
>`[!danger]-`
> **Toto** est dans la place !
>_Ceci est une mise en garde, on vous avait prévenu !!_

> [!tip]- Pour définir un titre ==personnalisé== :
> `[!tip]- Pour définir un titre ==personnalisé== :` 
> Il suffit de l'écrire en markdown après le `[!tip]-` que l'on utilise pour une astuce, un indice, une note importante...

> [!question]- Est-ce que les avertissements peuvent s'imbriquer ?
> `[!question]- Est-ce que les avertissements peuvent s'imbriquer ?`
> > [!success] Oui, c'est le cas dans Obsidian.
> > `[!success] Oui, c'est le cas dans Obsidian.`
> > > [!failure] Mais le rendu ne fonctionne pas dans MkDocs.
> > > `[!failure] Mais le rendu ne fonctionne pas dans MkDocs.`
> > > > [!quote]
> > > > `[!quote]`
> > > > "_Si vous avez besoin de quelque chose, appelez-moi.
> > > >  Je vous dirai comment vous en passer._"
> > > > Coluche






