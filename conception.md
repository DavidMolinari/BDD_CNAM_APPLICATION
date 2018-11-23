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

```mocodo
AdresseLivraison: refAdresseLivraison, numRue, nomRue, cp, ville, pays
EST LIVREE A, 01 AdresseLivraison, 11 Livraison
Livraison: refLivraison, dateLivraison
LIVRER, 01 Commande, 11 Livraison
Commande: refCommande, dateCommande
CommandePayée, 0N Commande, 0N MethodePaiement: datePaiement
MethodePaiement: refPaiement, numCarte, dateExpiration, codeCarte



POSSEDE, 1N Client, 11 AdresseLivraison
Client: numClient, email, nom, prenom, motDePasse, sexe, tel
PASSE, 0N Client, 11 Commande
:
DetailsCommande, 1N Commande, 0N Produit: nbProduitsCommandés
Produit: refProduit, nomProduit, prixProduit, nbProduits

:
:
:
TypeProduit: refTypeProduit, nomTypeProduit
EST DE TYPE, 11 Produit, 0N TypeProduit
```

![](https://github.com/DavidMolinari/BDD_CNAM_APPLICATION/blob/master/model3.svg)

![](https://i.imgur.com/tme9lb6.png)


**Je justifie le choix de l'identifiant de la table client (numClient) au lieux de email qui peut être identifiant unique de la table par la simplicité à autoIncrémenter lors de l'insertion de chaque client**


3. Contraintes particulières (NOT NULL ; valeur > 0 ; domaines de valeurs ; ...) ;
* emailClient     |int| NOT NULL|^[0-9a-zA-Z._-]+@[0-9a-zA-Z._-]{2,}[.][a-zA-Z]{2,4}$|   |
* sexeClient     |varchar|NOT NULL   |Domain{'homme', 'femme', 'autre'}|   |
* dateNaissanceClient     |DATETIME|NOT NULL   |   < NOW() |   |

4. Liste des fonctionnalités prises en charges par votre BD (fonctions, triggers)

* Fonctionnalités simples : 
   * Lister tous les clients enrengistrés
   * Lister tous les produits ainsi que leurs types associés
   * Lister touts les clients qui ont passé une commande à une date précise
   * Récupérer les commandes qui n'ont pas encore été payées
   * Récupérer les commandes qui n'ont pas encore été livrées
   * Récupérer tous les produits commandés par un client particulier
* Fonctionnalités statistiques :
   * Récupérer le client le plus fidèle
   * Lister toutes les commandes commandées par des clients qui habitent en France
   * Lister tous les clients qui ont commandé par plusieurs moyens de paiements
* Trigger 
   * Réduire automatiquement le nombre de produit disponible à chaque commande [TRIGGER]
      * Choix commercial, sera fait sur le After insert et non le avant insert, d'un point de vu commercial : je préfère retarder la livraison d'un produit que de la perdre
   * Vérifier si le client est majeur avant de passer une commande [TRIGGER]

