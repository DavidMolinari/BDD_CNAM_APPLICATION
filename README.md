# FELINE


## Cahier des charges 

- Nom de l'entreprise : FELINE

- Nom du projet : FELINE

- Personne à contacter dans l'entreprise : JEAN FELINE

- Adresse : 4 rue meow@Toulon

- Tel : 06 44 44 44 44

- email : meow@feline.ew


## Présentation de l'entreprise 

FELINE©, une boutique en ligne qui s'occupe de vendre des goodies en lien avec les chats, des jouets, des stickers, des cahiers, des stylos, etc.
Créée en 2018 suite à l'achat d'un box aléatoire lors d'une vente aux encheres, JEAN FELINE se retrouva avec des miliers de goodies de chats et il décide par la suite d'ouvrir une petite boutique pour vendre tous ces articles. Le succès fût plutôt sympathique, alors il se lance dans la fabrication, la production de ces goodies et dans le bût d'étendre sa petite boutique il il crée son site de e-commerce mais ça se transforme vite en catastrophe à cause de son manque de conaissances et de tous les vautours qui lui demandent 140.000€ pour l'application.
Il propose donc à un étudiant fan de chat de faire l'application pour lui, en échange de goodies à vie.

Quelques chiffres : 

    - 120k de chiffre d'affaire
    - 1 employé
    
Principaux concurrents : 
    
    - Amazon
    
    
## Analyse de l'éxistant pour le site internet : 
![](https://www.blog.spoongraphics.co.uk/wp-content/uploads/2008/06/2.jpg)

Jean FELINE se sent très gêné à l'idée de dévoiler l'éxistant, nous avons donc décidé de flouter l'éxistant pour éviter toute gêne

- Solution utilisée actuellement : Site web basique avec un formulaire de contact par email pour toute commande, gestion des stock, des prix, des références produits sur des classeurs papiers avec un employé en dépression.
- Statistiques actuelles : Traffic mensuel à +/- 5k 



## Message SMS du client :

   ![https://sayingimages.com/wp-content/uploads/i-needs-help-help-meme.jpg](https://sayingimages.com/wp-content/uploads/i-needs-help-help-meme.jpg)    
    
```text
 Je suis débordé, j'ai une gestion de mes commandes sur papier avec plusieurs classeurs et je n'arrive pas à recruter de personnes pour s'occuper de toute cette paperasse, malgrè tous les bonbons et gateaux que je fournis à chaque entretient.
    Je vends des goodies sur mon site web  : goodiesdechats.shopsitegratuit.com et à chaque commande, je reçois un email me notifiant qu'un client veut acheter cet objet.
    Mes concurrents n'ont rien à faire de leur côté, ils n'ont qu'à remplir leur stock alors que je passe des heures à faire le tri, noter, classer et je ne m'en sors plus alors HELP, HELP, HELP 
 ```


### Les objectifs de l'application :

Améliorer le trafic, proposer de l'instantané aux clients, améliorer notre gestion de données




### Les cibles : 

Les fans de chats dépensent sans compter.


### PERSONAS 
  
   ![](http://www.iconninja.com/files/837/326/356/user-young-male-avatar-person-man-icon.png)
   
    - Sam, étudiant en droit
      - Informations de base :
          - Age : 20 ans
          - Situation familiale : Célibataire, sans enfant
          - Centres d'interêt : Réseaux sociaux, jeux vidéos, pizza, chats
          - vit en France dans une zone résidentielle
          - Traits de caractère : Accent du sud
          - Relation aux chats : 10/10 => Addicted
          - Il porte des adidas Vegan parce que c'est à la mode
      - Objectifs :
          - Augmenter ses likes sur Instagram
          - Augmenter ses relations sur LinkedIn
          - Soigner son image numérique au maximum et se faire connaître dans le milieu des courses automobiles
          - Trouver une copine sur Meetic
          - Découverte de la boutique :
            -publicité sur le boncoin
      - FREINS
        - Dépensier


   ![](http://bb-bau.com/images/avatar.png)
   
    - Virginie, manager dans une start-up
      - Informations de base :
        - Age : 28 ans
        - Situation familiale : Célibataire, sans enfant
        - Centres d'interêt : Réseaux sociaux, Design, Relations sociales
        - Vit en France dans une collocation
        - Traits de caractère : Inquiète du regard des gens
        - Relation à la technologie : 9/10 Très accroc
        - Aime la mode, prendre ses plats en photos
      - Objectifs :
        - Devenir une influenceuse sur Instagram
        - Soigner son image numérique au maximum 
        - Trouver un compagnon sur AdopteUnMec
      - Découverte du projet :
        - Trailer en publicité sur Instagram
      - FREINS
        - Trop sensible
        - Fragile






## Objectifs quantitatifs
osef
## Périmètres du projet 
osef


## Besoins spécifiques du client

    - Je veux avoir une liste complète de tous mes clients, les informations personnelles qu'ils ont décidé d'entrer (RGPD) pour pouvoir les lister, les trier, en extraire des profils pour d'éventuelles promotions ( % de réduction sur des chaussures pour femmes [a+ les non binaires] )
        - Je veux avoir une trace et un archivage complet de toutes les commandes daté
        - Je veux que la plus part des actions soient automatisées, que le client n'ait pas à attendre avant que sa commande ne soit traitée
        - Je veux avoir la liste complète de tous mes produits, triés par types, par prix, etc
        - Je veux avoir la liste des transactions effectuées
        - Je veux avoir la liste de tous les produits achetés



## Proposition des solutions techniques :

- MYSQL VS POSTGRE
    transactional DDL (no fucked up, stuck in the middle migration)
    Json / Array Type (indexed ==> faster than mongo for certain workflow)
    powerfull indexing story
    powerfull explain (let you debug why it's slower)
    Boolean data type (not a Tiny INT)
    Text data type in PG (not like varchar(255) /o\ ) and real utf8 support (hello utf8mb4 and other related index issue /o)
    Recursive Queries or window query :)
    Generate_table \o/
    Helping , smart , open community

- serveur Apache VS NGINX
    perf
   

//TODO pourquoi avoir choisi les deux
## Contraintes techniques et diverses

- Techno facile à prendre en main pour maintenabilité future par d'autres développeurs
- Laps de temps très court avant livraison


## Les livrables :
- Code source de l'application complète sur un repository en ligne
- Application web prête pour y faire des tests car le client ne sait pas ouvrir un terminal



