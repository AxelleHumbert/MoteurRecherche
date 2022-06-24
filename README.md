### Sujet 2 : moteur de recherche d'images d'animaux

L'objectif de ce mini-projet est d'implémenter un moteur de recherche d'images par similarité sur une banque d'images d'animaux. On utilisera la base de données [Animal Image Dataset](https://www.kaggle.com/ashishsaxena2209/animal-image-datasetdog-cat-and-panda).

Étapes :
1. calculer des caractéristiques d'images sur les images
2. implémenter une recherche d'image par la méthode des plus proches voisins
3. comparer les performances de différentes caractéristiques
4. *bonus, si vous avez le temps* : calculer les scores de [précision et de rappel](https://fr.wikipedia.org/wiki/Pr%C3%A9cision_et_rappel)


### Rendu : Résultats

  La détection des chats est très efficace quand on compare les images avec un canny. La détection des pandas arrive à un taux acceptable (±60%) quand on ajuste les thresholds du canny (en les augmentants) au détriment de la détection des chats (mais elle reste tous a fais acceptable ±60%). Cependant, la détection des chiens est médiocre montant jusqu'à ± 20% quelque soit les settings. cf : *calixte_test.ipynb*. A noté un échantillon de 150 images à comparer avec 9 images prend 6.0 secondes.

  A l'inverse quand on fait juste une comparaison en grey_scale on trouve un résultat complètement inverse où la détection de chiens est extrêmement efficace (±95%, cf : MaximeHogTest.ipynb), mais la détéction de chat est on existante (0%). Enfin on atteint une détection des pandas au alentours de ±40%. A noté un échantillon de 150 images à comparer avec 50 image prend 5 minutes.
  
  Une solution intéressante pour avoir de meilleurs resultat serait d'ajouter un 3ème algorithme de modification d'image sur lequel on ajouterait une comparaison par Hog. On pourrait ensuite comparer les 3 résultats obtenue pour avoir un taux de vrai positif plus élevé. Cependant nous n'avons pas trouver une technique pour laquel un comparaison d'hog donnerais des résultats pertinant pour les chiens et pour les chats simultanéments. De plus, cela risque de probablement impacter énormément les perfomence même si la comparaison est faite sur une image.
