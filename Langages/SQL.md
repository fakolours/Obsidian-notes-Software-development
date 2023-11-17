Related : #langage 
Utilisé en gestion de bases de données, le langage SQL est un de ses premiers langages. Sur des bases de données complexes ou très volumineuses on aura tendances à favoriser des technologies NoSQL qui permettent d'accéder à la donnée plus rapidement.
SQL se base sur la création de tables de données. Ces tables sont bidimensionnels, une dimension pour définir le nom et type de la donnée contenu dans la case et l'autre dimension est le stockage donc contient en général un identifiant (unique) de la donnée enregistrée dans la table.
### Règles de syntaxe
Une commande de SQL ne se termine que lorsqu'elle rencontre un `;`.
Les opérateurs peuvent s'écrire en minuscule et en majuscule. Par convention, ils seront ici écrites exclusivement en majuscule.
Les colonnes peuvent contenir plusieurs types de données. Cependant, une fois le type de données affecté, il est impossible de le changer.
### Base de l'exemple
Pour l'exemple suivant on utilisera une table `table_1` qui contient les colonnes `country`,`age`,`date_of_inscription`,`size`,`name`
## Opérateurs 
### Créer une table
#### Les types de donnée les plus importants 
- Entiers : `INT`
- Chaînes de caractères de longueur fixe : `CHAR(-length-)`
- Chaînes de caractères de longueur variable : `VARCHAR(-Maxlength-)`
- Booléen : `BOOL`
- Valeur parmi une liste : `ENUM(val1,val2,val3...)`
- Fichiers binaire volumineux (image, son ...) : `BLOB`
- Date et heure (format américain) : `DATETIME`
Pour plus de détails et une liste exhaustive de tous les types : [W3School : SQL datatypes](https://www.w3schools.com/sql/sql_datatypes.asp)
### Insérer des données

### Rechercher des données
#### SELECT et FROM
```SQL
SELECT name FROM table_1;
```
Cette commande retournera toutes les données contenu dans `column_1` de `table_1`

On peut aussi demander de retourner plusieurs colonnes de la même table : 
```SQL
SELECT name,age,size FROM table_1
```
#### * (star)
```SQL
SELECT * FROM table_1;
```
Cette commande retournera toutes les données contenu de `table_1`
### Restreindre les données
#### WHERE
Cet opérateur permet d'imposer des conditions aux valeurs retournées par la commande précédente.
```SQL
SELECT column_1 FROM table_1
WHERE column_2 == 42
```
Cette commande retournera toutes les valeurs de `column_1` dont la ligne contient 42 comme valeur en `column_2`.

#### Les différents opérateurs pour appliquer des conditions
- ##### AND et OR
Cet opérateur permet d'associer des actions, notamment des conditions
```SQL
SELECT column_1 FROM table_1
WHERE (column_2 == 42 AND column_5 == "poivre")
OR column_4 == "sel"
```
Cette fois ci on retournera les valeurs de `column_1` qui valide :
	- 42 pour `column_2` et "poivre" pour `column_5` 
	- ou "sel" pour `column_4`
- ##### NOT

- ##### IN
Cet opérateur permet d'avoir une liste de valeur à laquelle une colonne peut correspondre pour être retourné.
- ##### BETWEEN
- ##### EXISTS
- ##### NULL
- ##### ALL ou ANY