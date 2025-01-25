V. Gestion des transactions (2 séances)

### 5.1. Introduction aux transactions:

- Concept de transactions et leurs propriétés ACID.
- Gestion des transactions avec BEGIN TRANSACTION, COMMIT et ROLLBACK.

### 5.2. Isolation des transactions:

- Niveaux d'isolation des transactions et leurs implications.
- Exemples de problèmes d'isolation des transactions et solutions.


### 5.3. Exercice:

- **Enoncé:** Créer une transaction qui augmente le nombre d'exemplaires d'un livre et enregistre l'emprunt de ce livre par un utilisateur. Annuler la transaction si l'une des opérations échoue.
- **Solution:**
    
```sql
BEGIN TRANSACTION; 
UPDATE Livres SET Quantité = Quantité + 1 WHERE ID = 123; 
INSERT INTO Emprunts (LivreID, Emprunteur, DateEmprunt) VALUES (123, 'John Doe', DATE('now'));
COMMIT TRANSACTION;
```