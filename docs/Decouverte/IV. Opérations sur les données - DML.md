IV. Opérations sur les données (3 séances)

### 4.1. Insertion de données:

- La commande INSERT INTO table VALUES(...);
- Insertion de données avec des valeurs par défaut.
- Insertion de données à partir d'une autre table.

### 4.2. Mise à jour de données:

- La commande UPDATE table SET col1 = val1 WHERE condition;
- Mise à jour de plusieurs colonnes à la fois.
- Mise à jour conditionnelle.

### 4.3. Suppression de données:

- La commande DELETE FROM table WHERE condition;
- Suppression de toutes les données d'une table.
- Suppression de données avec des jointures.


### 4.4. Exercice:

- **Enoncé:** Mettre à jour le titre du livre "Le Petit Prince" en "Le Petit Prince (Nouvelle édition)". Supprimer ensuite les emprunts des livres dont la date de retour est dépassée.
- **Solution:**
    
```sql
UPDATE Livres SET Titre = 'Le Petit Prince (Nouvelle édition)' WHERE Titre = 'Le Petit Prince';

DELETE FROM Emprunts WHERE DateRetour < DATE('now');
```