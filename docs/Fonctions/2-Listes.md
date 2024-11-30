# Les listes
>[!tip] Contrairement à MkDocs, avec Obsidian on n'est pas obligé de sauter une ligne pour commencer une liste.
>  L'extension [mdx-breakless-lists](https://pypi.org/project/mdx-breakless-lists/) installée ici dans le `mkdocs.yml` et le `ci.yml` élude cette différence en ajoutant systématiquement une ligne dans le code traduit pour MkDocs par rapport à celui venant d'Obsidian.

## Liste à puces

>[!example]+ Par exemple, le code MarkDown ci-dessous :
>```markdown
>* Un élement de liste ;
>Une précision concernant cet élément...
>- Un autre élément de liste ;
>- Un second élément de cette liste ;
>    * Un élément de sous-liste ;
>    * Un autre élément de sous-liste ;
>	    * Un élément de sous-sous-liste ;
>+ Encore un autre élément de liste.
>```

>[!example]+ produira l'affichage suivant :
>* Un élement de liste ;
>Une précision concernant cet élément...
>- Un autre élément de liste ;
>- Un second élément de cette liste ;
>    * Un élément de sous-liste ;
>    * Un autre élément de sous-liste ;
>	    * Un élément de sous-sous-liste ;
>+ Encore un autre élément de liste.

>[!failure] Remarque
> Contrairement à Obsidian, dans MkDocs les changements de types de puces ne provoquent pas de saut de ligne supplémentaire.

## Liste ordonnées

>[!example]+ Par exemple, le code MarkDown ci-dessous :
>```markdown
>4. Le quatrième élément de ma liste ;  
>Une précision concernant cet élément...
>1. Le cinquième élément de ma liste ;
>    1. Le premier élément de ma sous-liste ;
>    72. Le second élément de ma sous-liste ;
>1024. Le sixième élément de ma liste.
>```

>[!example]+ produira l'affichage suivant :
>
>4. Le quatrième élément de ma liste ;  
>Une précision concernant cet élément...
>1. Le cinquième élément de ma liste ;
>    1. Le premier élément de ma sous-liste ;
>    72. Le second élément de ma sous-liste ;
>1024. Le sixième élément de ma liste.

>[!success] Préciser le début de la numérotation
>  L'extension [sane_lists](https://python-markdown.github.io/extensions/sane_lists/) installée ici dans le `mkdocs.yml` permet à MkDocs d'avoir le même comportement qu'Obsidian concernant les listes.

## Liste de taches

>[!example]+ Par exemple, le code MarkDown ci-dessous :
>```markdown
>- [ ] Une tâche de ma todo liste ;
>- [x] Une autre tâche de ma todo liste ;
>    - [x] une sous tâche de ma todo liste ;
>    - [ ] une autre sous tâche de ma todo liste ;
>- [ ] Encore une autre tâche de ma todo liste.
>```

>[!example]+ produira l'affichage suivant :
> - [ ] Une tâche de ma todo liste ;
> - [x] Une autre tâche de ma todo liste ;
>     - [x] une sous tâche de ma todo liste ;
>     - [ ] une autre sous tâche de ma todo liste ;
> - [ ] Encore une autre tâche de ma todo liste.

>[!failure] Remarque
> Contrairement à Obsidian, dans MkDocs cocher le bouton d'une tâche ne barre pas le texte de cet item et cocher le bouton d'une tâche supérieure ne raye pas toutes les tâches de sa sous-liste sans exception.
> De plus, d'autres marqueur comme `[w]` ne sont pas supportés.





