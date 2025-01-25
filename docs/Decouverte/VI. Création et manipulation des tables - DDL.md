VI. Création et manipulation des tables (2 séances)

### 6.1. La commande CREATE TABLE:
    
- Définir les colonnes et leurs types de données.
- Définir les clés primaires et étrangères.
- Définir les contraintes d'intégrité des données.
    
### 6.2. La commande ALTER TABLE:
    
- Modifier les colonnes d'une table (ajouter, supprimer, modifier).
- Modifier les contraintes d'une table.
    
### 6.3. La commande DROP TABLE:
    
- Supprimer une table.
    

### 6.4. Exercice:

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