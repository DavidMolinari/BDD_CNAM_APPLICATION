# NLP => Natural Language Processing
## Recherche d'informations
cons : recherche avec %meh%
- temps
- pertinence
- recherche booleennes









* Index Inversé
* **Mesure TF** => Le poids d'un terme dans un document
* **Mesure Idf** => Quantifier le contenu informatif d'un terme / la rareté / Le pouvoir discriminant 
* Combiner les deux tf-idf weighting : tf * idf => (1+ log10(tf)) * log10(N/df)
* SCORE ( ZE FORMULE ) = pour tous les termes dans le doc je fais la somme des tf.idf
* Et la formule de merde finale pour chacun des termes dans le doc


--


The Vector Space Model ( VSM )


* Collection C de documents
* Indexation : Tokenization => linguistic moduules => Indexation
* Index inversé positionnel [ Matrice des termes distincts => Num Document [ Postion ] ]
* **Mesure TF** => Le poids d'un terme dans un document
* **Mesure Idf** => Quantifier le contenu informatif d'un terme / la rareté / Le pouvoir discriminant 
* **W = tf * idf => (1+ log10(tf)) * log10(N/df)**
* Chaque doc est representé par un vecteur Di € R
* en 2D ( 2 termes, soit (U)=2)
* Recherche et ranking des documents répondant à une requête q selon le modèle vectorial
* pour chaque doc Di € C

![](https://i.imgur.com/xKU4XVk.png)


En pratique 

![](https://i.imgur.com/gbMNxwU.png)



* Taille de l'index :
  * 10% des données brûtes si index non positionnel 
  * 30-50% des données brûtes si index positionnel 
  * Encore + si gestion de synonymes, traduction, etc.
