# Accueil

Ce site est un exemple simple de publication sur le Web, avec MkDocs et le thème Material, de notes écrites dans Obsidian et hébergées sur GitHub. Il montre quelques solutions permettant plus ou moins la transition de la syntaxe d'Obsidian vers celle de MkDocs.

Ce site est adossé à un [tutoriel (en construction)](https://ericecmorlaix.github.io/adn-Tutoriel_Obsidian/) qui présente la prise en main et quelques fonctionnalités d'Obisidian.

![[undraw_informed_decision_p2lh.svg]]

## Degemer Mat !

Le texte en MarkDown de la page `index.md` du dossier `/docs` devient la page d'accueil en HTML que vous voyez ici.

Les dossiers présents dans `/docs` apparaissent comme sections principales de la barre de navigation. De même pour le titre de niveau 1 `# Accueil` écrit au début du fichier `index.md`.

Chaque note, `fichier.md` écrit en MarkDown, devient une nouvelle page du site dans leur section respective. Le noms de ces fichiers sont visible dans la barre d'URL. Les titres et sous-titres de la table des matières apparaissent dans des sous-sections d'un menu secondaire.

> En l'absence de titre de niveau 1 au début d'une note, c'est le nom du fichier qui apparaitra en tête de la sous-section.

Il est donc préférable dans Obsidian d'attribuer aux dossiers et fichiers des noms significatifs, sans caractère accentué ni espace et, de même que pour les titres et sous-titres, le mieux est de les choisir courts. 

> Ce nommage automatique peut-être modifié en définissant manuellement la rubrique `nav` dans le fichier `mkdocs.yml`, ce qui devient cependant vite fastidieux...
