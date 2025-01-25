III. Jointures (3 séances)

### 3.1. Introduction aux jointures:

- Différents types de jointures : INNER JOIN, LEFT JOIN, RIGHT JOIN.
- Jointures multiples.

### 3.2. Jointures avec la clause WHERE:

- Comparaison entre JOIN et WHERE pour réaliser des jointures.
- Exemples d'utilisation avec différentes tables.

### 3.3. Jointures avec des conditions complexes:

- Combinaison de plusieurs conditions dans la clause ON.
- Utilisation des opérateurs logiques dans la clause ON.

3.4. UNION / UNION ALL

### 3.5. Exercices

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