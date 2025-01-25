GPT-4o - OpenAI (17.085s - 28,665 credits)

Bien sûr ! Voici un plan de cours pour enseigner le SQL avec une inclusion des jointures selon la norme SQL92. Ce cours est divisé en plusieurs sections, chaque section incluant une leçon et un exercice.

### Plan de Cours SQL

#### Section 1: Introduction au SQL

- **Objectif**: Comprendre les bases du langage SQL et sa syntaxe.
- **Contenus**:
    
    - Qu'est-ce que le SQL ?
    - Installation et configuration de SGBD (ex: MySQL, PostgreSQL).
    - Comprendre les bases de données relationnelles.
    

**Exercice**:

- Créez une base de données appelée `Ecole`.
- Solution :
    
    `1CREATE DATABASE Ecole;`
    

#### Section 2: Manipulation des données

- **Objectif**: Savoir insérer, mettre à jour et supprimer des données.
- **Contenus**:
    
    - Commandes `INSERT`, `UPDATE`, `DELETE`.
    

**Exercice**:

- Insérez un nouvel étudiant dans une table `Etudiants` avec les colonnes `ID`, `Nom`, `Age`.
- Solution :
    
    `1INSERT INTO Etudiants (ID, Nom, Age) VALUES (1, 'Alice', 22);`
    

#### Section 3: Requêtes de base

- **Objectif**: Maîtriser les requêtes de base `SELECT`.
- **Contenus**:
    
    - Utilisation de `SELECT`, `WHERE`, `ORDER BY`.
    

**Exercice**:

- Sélectionnez tous les étudiants de plus de 20 ans.
- Solution :
    
    `1SELECT * FROM Etudiants WHERE Age > 20;`
    

#### Section 4: Jointures SQL

- **Objectif**: Comprendre et appliquer les jointures pour combiner des tables.
- **Contenus**:
    
    - Introduire la norme SQL92 sur les jointures.
    - Description des types de jointures : `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL JOIN`.
    

**Exercice**:

- Combinez les tables `Etudiants` et `Cours` en utilisant une `INNER JOIN` pour afficher les étudiants inscrits dans chaque cours. Les tables sont définies comme suit :
    
    - `Etudiants (ID, Nom, Age)`
    - `Inscriptions (EtudiantID, CoursID)`
    - `Cours (CoursID, Intitule)`
    
- Solution :
    
    `1SELECT Etudiants.Nom, Cours.Intitule 2FROM Etudiants 3INNER JOIN Inscriptions ON Etudiants.ID = Inscriptions.EtudiantID 4INNER JOIN Cours ON Inscriptions.CoursID = Cours.CoursID;`
    

#### Section 5: Agrégation et groupement

- **Objectif**: Utiliser les fonctions d’agrégation et le groupement de données.
- **Contenus**:
    
    - Les fonctions `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`.
    - La clause `GROUP BY`.
    

**Exercice**:

- Comptez le nombre d’étudiants inscrits dans chaque cours.
- Solution :
    
    `1SELECT Cours.Intitule, COUNT(Etudiants.ID) as NombreEtudiants 2FROM Cours 3INNER JOIN Inscriptions ON Cours.CoursID = Inscriptions.CoursID 4INNER JOIN Etudiants ON Inscriptions.EtudiantID = Etudiants.ID 5GROUP BY Cours.Intitule;`
    

#### Section 6: Filtrage avancé

- **Objectif**: Appliquer des filtres avancés dans les requêtes.
- **Contenus**:
    
    - Utilisation de `HAVING`.
    - Les sous-requêtes.
    

**Exercice**:

- Trouvez les cours ayant plus de deux inscriptions.
- Solution :
    
    `1SELECT Cours.Intitule, COUNT(Inscriptions.EtudiantID) as NombreInscriptions 2FROM Cours 3INNER JOIN Inscriptions ON Cours.CoursID = Inscriptions.CoursID 4GROUP BY Cours.Intitule 5HAVING COUNT(Inscriptions.EtudiantID) > 2;`
    

Ce plan de cours couvre les bases nécessaires pour débuter avec SQL et progresse vers des concepts plus avancés tels que les jointures et l'agrégation, tout en se concentrant sur la pratique avec des exercices appliqués.