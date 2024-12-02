# Cours SQL : Plan Complet pour Débutants

**Objectif:** Maîtriser les bases du langage SQL et ses applications dans la gestion de bases de données relationnelles.

**Public:** Étudiants débutants en informatique ou en gestion des données.

**Durée:** 15 séances (adaptable)

**Matériel:**

- Ordinateur avec un logiciel de gestion de base de données (ex: PostgreSQL, MySQL, SQLite)
- Base de données d'exemple (fournie ou à créer)
- Un éditeur de texte ou un IDE compatible SQL

**Plan du cours:**

**I. Introduction au SQL (2 séances)**

- **1.1. Qu'est-ce que le SQL?**
    
    - Définition du langage SQL et ses applications.
    - Histoire et évolution du SQL.
    - Différents types de SGBD (relationnels, NoSQL)
    
- **1.2. Structure des bases de données relationnelles:**
    
    - Concept de tables, colonnes, lignes et clés.
    - Relations entre les tables et clés étrangères.
    - Introduction au langage DDL (Data Definition Language).
    
- **1.3. Introduction au langage DML (Data Manipulation Language)**
    
    - Opérations de base: SELECT, INSERT, UPDATE, DELETE.
    - Syntaxe de base des requêtes SQL.
    

**Exercice:**

- **Enoncé:** Créer une base de données "Bibliothèque" avec une table "Livres" contenant les colonnes: ID, Titre, Auteur, Année.
- **Solution:**

```sql
CREATE DATABASE Bibliotheque; 
USE Bibliotheque;

CREATE TABLE Livres ( 
	ID INT PRIMARY KEY, 
	Titre VARCHAR(255), 
	Auteur VARCHAR(255),
	Année INT
);

```
    

**II. Requêtes de sélection (3 séances)**

- **2.1. La commande SELECT:**
    
    - Syntaxe de base : SELECT * FROM table;
    - Sélection de colonnes spécifiques : SELECT col1, col2 FROM table;
    - Utilisation des alias : SELECT col1 AS alias1, col2 AS alias2 FROM table;
    
- **2.2. Filtrage des données:**
    
    - La clause WHERE : SELECT * FROM table WHERE condition;
    - Opérateurs de comparaison (=, <, >, <=, >=, !=)
    - Opérateurs logiques (AND, OR, NOT)
    
- **2.3. Tri des résultats:**
    
    - La clause ORDER BY : SELECT * FROM table ORDER BY col ASC/DESC;
    - Tri par plusieurs colonnes.
    
- **2.4. Fonctions d'agrégation:**
    
    - COUNT(), SUM(), AVG(), MAX(), MIN().
    - La clause GROUP BY : SELECT col1, SUM(col2) FROM table GROUP BY col1;
    - La clause HAVING : SELECT col1, SUM(col2) FROM table GROUP BY col1 HAVING SUM(col2) > 100;
    

**Exercice:**

- **Enoncé:** Afficher le nombre de livres par auteur, en triant par ordre décroissant de nombre de livres.
- **Solution:**
    
```sql
SELECT Auteur, COUNT(*) AS NombreLivres
FROM Livres
GROUP BY Auteur 
ORDER BY NombreLivres DESC;
```
    

**III. Jointures (3 séances)**

- **3.1. Introduction aux jointures:**
    
    - Différents types de jointures : INNER JOIN, LEFT JOIN, RIGHT JOIN.
    - Jointures multiples.
    
- **3.2. Jointures avec la clause WHERE:**
    
    - Comparaison entre JOIN et WHERE pour réaliser des jointures.
    - Exemples d'utilisation avec différentes tables.
    
- **3.3. Jointures avec des conditions complexes:**
    
    - Combinaison de plusieurs conditions dans la clause ON.
    - Utilisation des opérateurs logiques dans la clause ON.
    

**Exercice:**

- **Enoncé:** Créer une table "Emprunts" avec les colonnes: ID, LivreID, Emprunteur, DateEmprunt, DateRetour. Puis, afficher le titre du livre, le nom de l'emprunteur et la date d'emprunt pour chaque emprunt.
- **Solution:**
    
```sql
CREATE TABLE Emprunts ( 
    ID INT PRIMARY KEY, 
    LivreID INT, 
    Emprunteur VARCHAR(255), 
    DateEmprunt DATE, 
    DateRetour DATE, 
	FOREIGN KEY (LivreID) REFERENCES Livres(ID) 
);

SELECT L.Titre, E.Emprunteur, E.DateEmprunt 
FROM Livres L 
INNER JOIN Emprunts E ON L.ID = E.LivreID;
```
    

**IV. Opérations sur les données (3 séances)**

- **4.1. Insertion de données:**
    
    - La commande INSERT INTO table VALUES(...);
    - Insertion de données avec des valeurs par défaut.
    - Insertion de données à partir d'une autre table.
    
- **4.2. Mise à jour de données:**
    
    - La commande UPDATE table SET col1 = val1 WHERE condition;
    - Mise à jour de plusieurs colonnes à la fois.
    - Mise à jour conditionnelle.
    
- **4.3. Suppression de données:**
    
    - La commande DELETE FROM table WHERE condition;
    - Suppression de toutes les données d'une table.
    - Suppression de données avec des jointures.
    

**Exercice:**

- **Enoncé:** Mettre à jour le titre du livre "Le Petit Prince" en "Le Petit Prince (Nouvelle édition)". Supprimer ensuite les emprunts des livres dont la date de retour est dépassée.
- **Solution:**
    
```sql
UPDATE Livres SET Titre = 'Le Petit Prince (Nouvelle édition)' WHERE Titre = 'Le Petit Prince'; 
DELETE FROM Emprunts WHERE DateRetour < DATE('now');
```
    

**V. Gestion des transactions (2 séances)**

- **5.1. Introduction aux transactions:**
    
    - Concept de transactions et leurs propriétés ACID.
    - Gestion des transactions avec BEGIN TRANSACTION, COMMIT et ROLLBACK.
    
- **5.2. Isolation des transactions:**
    
    - Niveaux d'isolation des transactions et leurs implications.
    - Exemples de problèmes d'isolation des transactions et solutions.
    

**Exercice:**

- **Enoncé:** Créer une transaction qui augmente le nombre d'exemplaires d'un livre et enregistre l'emprunt de ce livre par un utilisateur. Annuler la transaction si l'une des opérations échoue.
- **Solution:**
    
```sql
BEGIN TRANSACTION; 
UPDATE Livres SET Quantité = Quantité + 1 WHERE ID = 123; 
INSERT INTO Emprunts (LivreID, Emprunteur, DateEmprunt) VALUES (123, 'John Doe', DATE('now'));
COMMIT TRANSACTION;
```
    

**VI. Création et manipulation des tables (2 séances)**

- **6.1. La commande CREATE TABLE:**
    
    - Définir les colonnes et leurs types de données.
    - Définir les clés primaires et étrangères.
    - Définir les contraintes d'intégrité des données.
    
- **6.2. La commande ALTER TABLE:**
    
    - Modifier les colonnes d'une table (ajouter, supprimer, modifier).
    - Modifier les contraintes d'une table.
    
- **6.3. La commande DROP TABLE:**
    
    - Supprimer une table.
    

**Exercice:**

- **Enoncé:** Créer une table "Genres" avec les colonnes ID et Nom. Ajouter ensuite une colonne "GenreID" à la table "Livres" et créer une clé étrangère vers la table "Genres".
- **Solution:**
    
```sql
CREATE TABLE Genres ( 
	ID INT PRIMARY KEY, 
	Nom VARCHAR(255) 
);

ALTER TABLE Livres ADD GenreID INT; 
ALTER TABLE Livres ADD FOREIGN KEY (GenreID) REFERENCES Genres(ID);
```
    

**VII. Indexation (1 séance)**

- **7.1. Qu'est-ce qu'un index ?**
    
    - Définition et avantages des index.
    - Différents types d'index (unique, composite).
    
- **7.2. Création d'index:**
    
    - La commande CREATE INDEX;
    - Utilisation des index pour améliorer les performances des requêtes.
    
- **7.3. Suppression d'index:**
    
    - La commande DROP INDEX;
    

**Exercice:**

- **Enoncé:** Créer un index sur la colonne "Auteur" de la table "Livres".
- **Solution:**
    
```sql
CREATE INDEX idx_auteur ON Livres (Auteur);
```
    

**VIII. Sécurité et permissions (1 séance)**

- **8.1. Introduction à la sécurité des bases de données.**
    
    - Différents niveaux de sécurité (utilisateur, table, colonne).
    - Contrôle d'accès basé sur les rôles.
    
- **8.2. Gestion des utilisateurs et des permissions:**
    
    - La commande CREATE USER;
    - La commande GRANT;
    - La commande REVOKE;
    

**Exercice:**

- **Enoncé:** Créer un utilisateur "bibliothecaire" avec le mot de passe "password". Accorder à cet utilisateur le droit de lire, écrire et supprimer des données dans la table "Livres".
- **Solution:**
    
```sql
CREATE USER bibliothecaire WITH PASSWORD 'password'; 
GRANT SELECT, INSERT, UPDATE, DELETE ON Livres TO bibliothecaire;`
```    

**Notes:**

- Ce plan est une suggestion et peut être adapté en fonction du niveau des étudiants et du temps disponible.
- Les exercices peuvent être modifiés pour mieux répondre aux besoins et aux connaissances des étudiants.
- Il est important de fournir des exemples concrets et des cas d'utilisation réels pour rendre l'apprentissage plus pertinent.
- Encouragez les étudiants à pratiquer et à expérimenter le langage SQL.
- N'hésitez pas à utiliser des outils de visualisation de données pour illustrer les concepts de SQL.

**Conseils pour la pédagogie:**

- Commencez par des exemples simples et progressifs.
- Utilisez des images et des schémas pour illustrer les concepts.
- Donnez des exercices pratiques à vos étudiants et corrigez-les en groupe.
- Encouragez la participation des étudiants et répondez à leurs questions.
- Fournissez des ressources complémentaires (livres, sites web, vidéos) pour approfondir l'apprentissage.