# Les titres 

D'une manière générale, comme ci-dessous pour les titres jusqu'au niveau 6, tous les marqueurs MarkDown de formatage disponibles dans Obsidian sont remplacés par leurs balises HTML correspondantes.

>[!example]+ Par exemple, le code MarkDown suivant, saisi dans Obsidian :
>```markdown
># Titre de niveau 1
>## Titre de niveau 2
>### Titre de niveau 3
>#### Titre de niveau 4
>##### Titre de niveau 5
>###### Titre de niveau 6
>####### Il n'y a pas de titre de niveau 7
>```

>[!example]+ est converti en HTML par MkDocs ainsi :
>```html
><h1>Titre de niveau 1</h1>
><h2>Titre de niveau 2</h2>
><h3>Titre de niveau 3</h3>
><h4>Titre de niveau 4</h4>
><h5>Titre de niveau 5</h5>
><h6>Titre de niveau 6</h6>
><h6># Il n'y a pas de titre de niveau 7</h6>
>```

>[!example]+ Ce qui affiche sur le site Web généré par MkDocs :
>
>![[Titres_MkDocs.png]]

>[!example]+ Alors que l'interprétation du même code dans Obsidian produit l'affichage :
>
>![[Titres_Obsidian.png]] 

>[!warning] Remarque :
>Le MarkDown d'Obsidian étant différent de celui de MkDocs on remarquera souvent de telles variations.
>
>Celle observée ici n'est cependant pas gênante car elle se produit sur un élément qu'on ne devrait pas et plus rencontrer puisque qu'il n'existe effectivement pas de titre de niveau 7 en HTML.
>
>Pour des différences plus significatives, on ~~cherchera~~ trouvera des solutions de contournement...

