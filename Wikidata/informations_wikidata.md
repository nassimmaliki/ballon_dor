Pour réaliser ce projet, j’ai d’abord eu besoin d’identifier les chefs français étoilés dans Wikidata, en partant d’une liste extraite de Wikipédia.

Pour cela, j’ai utilisé OpenRefine, un outil qui permet de faire correspondre automatiquement des noms avec leurs identifiants Wikidata, appelés QID.

Une fois les QIDs récupérés, j’ai utilisé le Wikidata Query Service pour écrire des requêtes SPARQL. Ces commandes m’ont permis de collecter les informations disponibles sur chacun des chefs.

Données extraites via SPARQL, voici les principales propriétés que j’ai récupérées pour chaque chef :
- Date de naissance:  wdt:P569
- Lieu de naissance:  wdt:P19
- Genre:  wdt:P21

Ces données ont ensuite été exportées en format CSV pour être utilisées dans mes notebooks Jupyter.
