# Le Corps de Texte

Par défaut, contrairement à MkDocs, le mode aperçu d'Obsidian prend en compte chaque retour à la ligne, ce qui, somme toute, est un comportement assez naturel. Cependant, comme MkDocs, il remplace les espaces laissés en trop par une seule espace :
>[!example]+ Par exemple, le code MarkDown ci-dessous :
>```markdown
>Ce texte                s'affiche           avec des retours à la ligne,  
>dans un seul            et                  même paragraphe,  
>mais les espaces      laissés en trop         sont supprimés...
>
>Pour former des paragraphes séparés, il faut laisser une ligne vide entre eux.
>
>On peut obtenir du _texte_ avec *simple emphase* rendu en *italique*,
>  du __texte__ avec **forte emphase** rendu en **Gras**,
>   du **_Texte_** à la fois en **gras** et en *italique*,
>    du `code source` rendu en caractères `monospaces`,
>     du ~~texte barré~~  rendu avec une ligne en travers du texte.     
>      On peut aussi ==surligné==.
>```

>[!example]+ produira l'affichage suivant :
>Ce texte                s'affiche           avec des retours à la ligne,  
>dans un seul            et                  même paragraphe,  
>mais les espaces      laissés en trop         sont supprimés...  
>
>Pour former des paragraphes séparés, il faut laisser une ligne vide entre eux.
>
>On peut obtenir du _texte_ avec *simple emphase* rendu en *italique*,
> du __texte__ avec **forte emphase** rendu en **Gras**,
>  du **_Texte_** à la fois en **gras** et en *italique*,
>   du `code source` rendu en caractères `monospaces`,
>    du ~~texte barré~~  rendu avec une ligne en travers du texte.     
>     On peut aussi ==surligné==.

>[!tip] L'extension [nl2br](https://python-markdown.github.io/extensions/nl2br/) (New-Line-to-Break) installée ici dans le `mkdocs.yml` permet à MkDocs d'avoir le même comportement qu'Obsidian concernant les retours à la ligne simple.

>[!question]- Obsidian peut-il avoir le même comportement que MkDocs quant aux retours à la ligne simple ?
> **Oui**,  en activant les **"sauts de lignes stricts"** dans les options de l'éditeur d'Obsidian, alors les sauts de ligne simple ne provoqueront pas de retours à la ligne dans le paragraphe sauf si on ajoute deux espaces à la fin d'une ligne avant de faire un retour à la ligne.
> Et dans ce cas il faudra désactiver l'extension [nl2br](https://python-markdown.github.io/extensions/nl2br/) dans le `mkdocs.yml` pour que MkDocs retrouve son comportement de base.

>[!note]  MkDocs avec Material offre davantage de [formatage de texte ](https://squidfunk.github.io/mkdocs-material/reference/formatting) mais il ne sont pas compatible avec Obsidian.



