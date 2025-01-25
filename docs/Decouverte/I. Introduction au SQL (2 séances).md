---
number headings: auto, first-level 1, max 6, 1.1
---
# 1 Séances
## 1.1 Qu'est-ce que le SQL?
    
- Définition du langage SQL et ses applications.
- Histoire et évolution du SQL.
- Différents types de SGBD (relationnels, NoSQL)
- Les 4 sous-langage du SQL
	- DQL : langage de requête de données.
	- DML : langage de manipulation des données
	- DDL : langage de définition des données
	- DCL : langage de contrôle des données
    
## 1.2 Structure des bases de données relationnelles:
    
- Concept de tables, colonnes, lignes et clés.
- Relations entre les tables et clés étrangères.
- Introduction au langage DDL (Data Definition Language).
    
## 1.3 Introduction au langage DML (Data Manipulation Language)
    
    - Opérations de base: SELECT, INSERT, UPDATE, DELETE.
    - Syntaxe de base des requêtes SQL.
    
## 1.4 Les Types de données
- String
- Date
- Entier
- Reel
- AutoIncrement

## 1.5 Exercice:

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