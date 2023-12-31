## Docker

Si vous avez déjà vu Docker, créez via docker un conteneur MySQL et importez le fichier `beer.sql` dans votre conteneur.

Si vous n'avez pas encore vu Docker, importez le fichier `beer.sql` dans votre base de données MySQL ou demandez à votre
formateur de vous aider ou de vous donner le docker-compose.

### Prérequis

- Vous devez avoir un dockerfile et un docker-compose.yml
- Vous ne devez pas utiliser de `bind mount` !
- Vous avez le droit d'utiliser un `volume`

## Etude du modèle

### Effectuez un reverse engineering du modèle

- Quelles sont les tables ?

- article 
- continent 
- couleur 
- fabricant 
- marque
- pays
- ticket
- type 
- ventes 

### Il y a des mauvaises pratiques dans ce modèle, lesquelles ?


## Exercices

Réalisez les requêtes suivantes :

### Quels sont les tickets qui comportent l’article d’ID 500, afficher le numéro de ticket uniquement ?

```mysql
    SELECT NUMERO_TICKET FROM ventes WHERE id_article = 500

```

### Afficher les tickets du 15/01/2014.

```mysql
    SELECT 'date_vente'  FROM 'ticket' WHERE date_vente='2014-01-15'
```

### Afficher les tickets émis du 15/01/2014 et le 17/01/2014.

```mysql
    SELECT 'annee' 'numero_ticket' 'date_ventes' FROM 'TICKET' WHERE date_vente  BETWEEN '2014-01-15' AND '2014-01-17'
```
### Afficher la liste des articles apparaissant à 50 et plus exemplaires sur un ticket.

```mysql
    SELECT 'numero_ticket' 'id_article' 'quantite' FROM 'vente' WHERE quantite >= 50
```
### Quelles sont les tickets émis au mois de mars 2014.

```mysql
    SELECT 'numero_ticket' 'id_article' FROM 'ticket' WHERE date_vente BETWEEN '2014-03-01' AND '2014-03-31'

```

### Quelles sont les tickets émis entre les mois de mars et avril 2014 ?

```mysql
    SELECT 'numero_ticket' FROM 'ticket' WHERE date_vente BETWEEN '2014-03-01' AND '2014-04-31'


```

### Quelles sont les tickets émis au mois de mars et juin 2014 ?

```mysql
    SELECT 'numero_ticket' FROM 'ticket' WHERE date_vente='2014-03-01' AND '2014-06-31'

```

### Afficher la liste des bières classée par couleur. (Afficher l’id et le nom)

```mysql
    SELECT 'id_article' 'nom_article' 'id_couleur' FROM article WHERE 'id_couleur' IS NOT NULL ORDER BY 'id_couleur';
```

### Afficher la liste des bières n’ayant pas de couleur. (Afficher l’id et le nom)

```mysql
    SELECT 'id_article' 'nom_article' 'id_couleur' FROM article WHERE 'id_couleur' IS NULL;


```