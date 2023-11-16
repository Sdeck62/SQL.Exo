## 10 Listez pour chaque ticket la quantité totale d’articles vendus. (Classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, SUM(QUANTITE) AS quantite_totale
FROM VENTES
GROUP BY NUMERO_TICKET
ORDER BY quantite_totale DESC;


```

## 11 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. (Classer par quantité décroissante)

```mysql
    SELECT numero_ticket, SUM(quantite) AS quantite_totale
    FROM ventes
    GROUP BY numero_ticket
    HAVING SUM 'quantite_totale' > 500
    ORDER BY quantite_totale DESC;
```

## 12 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. On exclura du total, les ventes ayant une quantité inférieure à 50 (classer par quantité décroissante)

```mysql
    SELECT numero_ticket, SUM(quantite) AS quantite_totale
    FROM ventes
    GROUP BY numero_ticket
    HAVING SUM 'quantite_totale' > 500
    EXCEPT
    HAVING SUM 'quantite_totale' < 50
    ORDER BY quantite_totale DESC;

```

## 13 Listez les bières de type ‘Trappiste’. (id, nom de la bière, volume et titrage)

```mysql
    SELECT id_article nom_article volume titrage nom_type
    FROM article
             JOIN type ON beer.type = nom.id;
    

```

## 14 Listez les marques de bières du continent ‘Afrique’

```mysql
    SELECT id_continent nom_continent id_article
    FROM beer.continent; 
    JOIN beer.
    

```

## 15 Lister les bières du continent ‘Afrique’

```mysql
```

## 16. Lister les tickets (année, numéro de ticket, montant total payé). En sachant que le prix de vente est égal au prix d’achat augmenté de 15%.

```mysql

```

## 17  Donner le C.A. par année.

```mysql
```

## 18. Lister les quantités vendues de chaque article pour l’année 2016.

```mysql

```

## 19. Lister les quantités vendues de chaque article pour les années 2014, 2015, 2016.

```mysql

```

