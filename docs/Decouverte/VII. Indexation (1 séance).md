VII. Indexation (1 séance)

### 7.1. Qu'est-ce qu'un index ?

- Définition et avantages des index.
- Différents types d'index (unique, composite).

### 7.2. Création d'index:

- La commande CREATE INDEX;
- Utilisation des index pour améliorer les performances des requêtes.

### 7.3. Suppression d'index:

- La commande DROP INDEX;
    

### 7.4. Exercice:

- **Enoncé:** Créer un index sur la colonne "Auteur" de la table "Livres".
- **Solution:**
    
```sql
CREATE INDEX idx_auteur ON Livres (Auteur);
```