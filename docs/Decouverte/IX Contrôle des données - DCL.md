IX Sécurité et permissions - Facultatif (1 séance)

### 9.1. Introduction à la sécurité des bases de données.
    
- Différents niveaux de sécurité (utilisateur, table, colonne).
- Contrôle d'accès basé sur les rôles.

### 9.2. Gestion des utilisateurs et des permissions:

- La commande CREATE USER;
- La commande GRANT;
- La commande REVOKE;
    

### 9.3. Exercice:

- **Enoncé:** Créer un utilisateur "bibliothecaire" avec le mot de passe "password". Accorder à cet utilisateur le droit de lire, écrire et supprimer des données dans la table "Livres".
- **Solution:**
    
```sql
CREATE USER bibliothecaire WITH PASSWORD 'password'; 
GRANT SELECT, INSERT, UPDATE, DELETE ON Livres TO bibliothecaire;`
```