## SPARQLBook - Import des données sur les chefs français étoilés Michelin

Ce fichier documente la requête SPARQL utilisée pour enrichir une population de chefs français étoilés à partir de leurs identifiants Wikidata (QIDs). Les données sont récupérées automatiquement depuis Wikidata pour être utilisées dans les analyses du projet.

---

### Objectif de la requête

Pour chaque chef dans notre liste, on souhaite récupérer :
- Le nom (label)
- La date de naissance
- Le lieu de naissance
- Le genre (sexe)
- Les distinctions reçues, notamment les étoiles Michelin

---

### Requête SPARQL
```sparql
SELECT DISTINCT ?chef ?chefLabel ?birthDate ?birthPlaceLabel ?genderLabel ?awardLabel WHERE {
  VALUES ?chef {
    wd:Q16269549 wd:Q53775759 wd:Q2896218 wd:Q3089575 wd:Q3104895  # ... etc.
  }

  OPTIONAL { ?chef wdt:P569 ?birthDate. }               # Date de naissance
  OPTIONAL { ?chef wdt:P19 ?birthPlace. }               # Lieu de naissance
  OPTIONAL { ?chef wdt:P21 ?gender. }                   # Genre (homme / femme)
  OPTIONAL {
    ?chef wdt:P166 ?award.                              # Distinction reçue
    ?award rdfs:label ?awardLabel.
    FILTER(CONTAINS(LCASE(STR(?awardLabel)), "michelin"))   # On filtre les distinctions contenant "michelin"
    FILTER(LANG(?awardLabel) = "fr")                        # En langue française
  }

  SERVICE wikibase:label { bd:serviceParam wikibase:language "fr". }
}
```

---

### Détail ligne par ligne
- `VALUES ?chef {...}` : liste des QIDs de la population (extraite d'un CSV)
- `OPTIONAL` : permet d'obtenir l'information quand elle est disponible
- `P569` : date de naissance
- `P19` : lieu de naissance
- `P21` : genre
- `P166` + filtre : distinction contenant "Michelin"
- `SERVICE wikibase:label` : affiche les labels humains (ex : nom, lieu) en français

---

### Fichier source de la population
Les QIDs utilisés dans `VALUES ?chef` proviennent du fichier CSV :
```
Wikidata/chefs_francais_etoiles_michelin.csv
```

Ils peuvent être copiés automatiquement dans la requête via un script Python.

---

### Format de sortie recommandé
Une fois exécutée sur [query.wikidata.org](https://query.wikidata.org), exporter les résultats en :
- CSV pour les analyses Jupyter
- JSON-LD si création d'une base RDF

---

### Prochaine étape
Utiliser ces données comme entrée dans un notebook Jupyter pour analyser, par exemple :
- La distribution des dates de naissance
- La répartition géographique
- Le genre des chefs ayant reçu des distinctions
