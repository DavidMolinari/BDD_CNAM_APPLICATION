|NOM            |FORMAT|REGLE CALCUL|CI|CATEGORIE|
|---            |---|---|---|---|
|emailClient    |int| NOT NULL|^[0-9a-zA-Z._-]+@[0-9a-zA-Z._-]{2,}[.][a-zA-Z]{2,4}$|   |
|prenomClient   |varchar|NOT NULL   |   |   |
|nomClient      |varchar|NOT NULL   |   |   |
|passwordClient |password|NOT NULL   |   |   |
|sexeClient     |varchar|NOT NULL   |Domain{'homme', 'femme', 'autre'}|   |
|dateNaissanceClient     |DATETIME|NOT NULL   |   < NOW() |   |
|rueClient      |varchar|NOT NULL   |   |   |
|telClient      |varchar|NOT NULL   |   |   |
|dateInscription|DATETIME|NOT NULL   | < NOW() > dateNaissanceClient|   |
|numRueClient   |varchar|NOT NULL   |   |   |
|cpClient       |varchar|NOT NULL   |   |   |
|villeClient    |varchar|NOT NULL   |   |   |
|paysClient     |varchar|NOT NULL   |   |   |
|refProduit     |int|NOT NULL   |   |   |
|nomProduit     |varchar|NOT NULL   |   |   |
|refTypeProduit |int|NOT NULL   |   |   |
|prixProduitHT    |float|NOT NULL   |  > 0.0|   |
|prixProduitTTC    |float|NOT NULL   |  > 0.0 |   |
|nomTypeProduit |varchar|NOT NULL   |   |   |
|nbProduitsDispo|int|NOT NULL   |   |   |
|numCommande    |int|NOT NULL   |   |   |
|dateCommande   |DATETIME|NOT NULL   |   |   |
|prixTotalHT    |float|NOT NULL   |   |   |
|prixTotalTTC    |float|NOT NULL   |   |   |
|nbProduitsComandés|int|NOT NULL   |   |   |
|dateLivraison |DATETIME|NOT NULL   |   |   |
|numCarte     |varchar|NOT NULL   |   |   |
|dateExpirationCarte|DATETIME|NOT NULL   |   |   |
|codeCarte      |varchar|NOT NULL   |   max{3} chars|   |
|refPaiementMethode|int|NOT NULL   |   |   |

1. Dictionnaire des données ;

 
```
Client
* numClient
* Nom
* Prénom
* Email
* motDePasse
* Sexe
* Tel
* rue
* numRue
* cp
* ville
* pays
```
```
PRODUIT
* refProduit
* nomProduit
* typeProduit
* prixProduit
```

```
TYPE_PRODUIT
* refTypeProduit
* nomTypeProduit
```

```
STOCK
* refProduit
* nbProduitsDispo
```

```
COMMANDE
* numCommande
* dateCommande
* numClient
```

```
DETAILS_COMMANDE
numCommande
refProduit
nbProduitsComandés
```

```
LIVRAISON
numCommande
dateLivraison

```



```
PANIER ???

```

```
METHODE_PAIEMENT
referenceMethodePaiement
refClient
numCarte
dateExpiration
codeCarte

```


``` 
COMMANDE_LIVREE
numCommande
dateLivraison
```

``` 
FOURRETOUT
prixTVA
```


2. Modèle Entité Association (MEA) et schéma relationnel ;




3. Contraintes particulières (NOT NULL ; valeur > 0 ; domaines de valeurs ; ...) ;
4. Liste des fonctionnalités prises en charges par votre BD (fonctions, triggers)
