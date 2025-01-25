# 1 Séance 1

## 1.1 La commande SELECT:

- Syntaxe de base : SELECT * FROM table;
- Sélection de colonnes spécifiques : SELECT col1, col2 FROM table;
- Utilisation des alias : SELECT col1 AS alias1, col2 AS alias2 FROM table;

## 1.2 Filtrage des données:

- La clause WHERE : SELECT * FROM table WHERE condition;
- Opérateurs de comparaison (=, <, >, <=, >=, !=)
- Opérateurs logiques (AND, OR, NOT)

## 1.3 Tri des résultats:

- La clause ORDER BY : SELECT * FROM table ORDER BY col ASC/DESC;
- Tri par plusieurs colonnes.

## 1.4 Fonctions d'agrégation:

- COUNT(), SUM(), AVG(), MAX(), MIN().
- La clause GROUP BY : `SELECT col1, SUM(col2) FROM table GROUP BY col1;`
- La clause HAVING : `SELECT col1, SUM(col2) FROM table GROUP BY col1 HAVING SUM(col2) > 100;`
    
## 1.5 Fonctions d'agrégation avancées:

- Créer sa propre fonction d'agrégation

## 1.6 Exercice:

- **Enoncé:** Afficher le nombre de livres par auteur, en triant par ordre décroissant de nombre de livres.
- **Solution:**
    
```sql
SELECT Auteur, COUNT(*) AS NombreLivres
FROM Livres
GROUP BY Auteur 
ORDER BY NombreLivres DESC;
```