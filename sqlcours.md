## creer une base de donné
syntaxe:CREATE DATABASE databasename;

## afficher les db
syntaxe:SHOW DATABASES;

## supprimer une db
syntaxe:DROP DATABASE databasename;

### creer une table
** syntaxe et exemple
CREATE TABLE user(
    id INTEGER AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    age INTEGER,
    password_user VARCHAR(255)
),
255:nombre maximale de caractère

## creer une table à partir diune autre 
syntaxe:CREATE TABLE tesTable AS SELECT name ,age FROM user;
cette table contient les meme proprietes et les memes contenus.
//- CREATE TABLE usercopie1 AS
--  SELECT * FROM user;:cree une nouvelle table avec toutes les propriétés de l'ancienne.

## ajouter dans la db
INSERT INTO user (name,age,password_user)
VALUES ("jean","22","djjlsl54");
## supprimer les elements d'une table
TRUNCATE TABLE user;
 
 ## ajouter une colonne à une table
 ALTER TABLE user ADD email VARCHAR(255);
 ## supprimer une colonne d'une table
 ALTER TABLE user
DROP COLUMN email;

## modifier le type(propriété) une colonne
ALTER TABLE user
MODIFY COLUMN email TEXT;
## ajouter une colonne birht
--  ALTER TABLE user ADD DateOfBirth DATE;

ALTER TABLE user
ADD updated_at TIMESTAMP;

ALTER TABLE user
ADD created_at TIMESTAMP;

  ALTER TABLE user DROP DateOfBirth DATE;

###### contraintes MySql
Les contraintes SQL sont utilisées pour spécifier des règles pour les données d'une table.

Les contraintes sont utilisées pour limiter le type de données pouvant être placées dans une table. Cela garantit l'exactitude et la fiabilité des données de la table. En cas de violation entre la contrainte et l'action sur les données, l'action est abandonnée.

Les contraintes peuvent être au niveau des colonnes ou au niveau des tables. Les contraintes au niveau des colonnes s'appliquent à une colonne, et les contraintes au niveau des tables s'appliquent à l'ensemble de la table.

Les contraintes suivantes sont couramment utilisées dans SQL :

*  NOT NULL- Garantit qu'une colonne ne peut pas avoir de valeur NULL
*  UNIQUE- Garantit que toutes les valeurs d'une colonne sont différentes
*  PRIMARY KEY- Une combinaison de a NOT NULLet de UNIQUE. Identifie de manière unique chaque ligne d'un tableau
*  FOREIGN KEY - Empêche les actions qui détruiraient les liens entre les tables
*  CHECK- Garantit que les valeurs d'une colonne satisfont une condition spécifique
*  DEFAULT- Définit une valeur par défaut pour une colonne si aucune valeur n'est spécifiée
*  CREATE INDEX- Utilisé pour créer et récupérer des données de la base de données très rapidement

*****UNIQUE PEUT ETRE sur plusieurs tables et primary key doit etre sur un seul element.

## afficher les propriétés des tables 
DESCRIBE user;
## ajout d'une primary key
ALTER TABLE Persons
ADD PRIMARY KEY (ID);

ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);

## spprimer key
ALTER TABLE Persons
DROP PRIMARY KEY;

ALTER TABLE Persons
DROP CONSTRAINT PK_Person;

## Foreign keyal  declencheur
primary key :parent
foreign key : enfant
ALTER TABLE user


## SELECT
SELECT est utilisée pour sélectionner des données dans une base de données.

### les operateurs
Operator	Description	Example
=	Equal	
>	Greater than	
<	Less than	
>=	Greater than or equal	
<=	Less than or equal	
<>	Not equal. Note: In some versions of SQL this operator may be written as !=	
BETWEEN	Between a certain range	
LIKE	Search for a pattern	
IN	To specify multiple possible values for a column

### suppression d'enregistrements
DELETE FROM table_name WHERE condition;

### mise à jour d'enregistrements
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

      ### paticulier
      DELETE FROM lesson3 WHERE nom like  '%chrisbi';

### limit
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
specifier le nbre d'enregistrement à envoyer. 


#### fonction
min() et max()
SELECT * 
FROM lesson3
WHERE age =(SELECT MIN(age) FROM lesson3 LIMIT 1);
SELECT * 
FROM lesson3
WHERE age =(SELECT MAX(age) FROM lesson3 LIMIT 1);


### valeur moyenne
SELECT AVG(age)
FROM lesson3
WHERE condition;


### somme
SELECT SUM(age)
FROM lesson3;