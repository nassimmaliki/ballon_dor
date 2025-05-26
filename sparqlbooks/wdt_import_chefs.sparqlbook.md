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
  wd:Q16269549
  wd:Q53775759
  wd:Q2896218
  wd:Q3089575
  wd:Q3104895
  wd:Q2894669
  wd:Q2897473
  wd:Q105396989
  wd:Q3167322
  wd:Q587303
  wd:Q19630088
  wd:Q1063664
  wd:Q33103496
  wd:Q3350809
  wd:Q33112838
  wd:Q2896437
  wd:Q3369238
  wd:Q1296999
  wd:Q2918264
  wd:Q8159
  wd:Q15457336
  wd:Q16629641
  wd:Q2918534
  wd:Q1569825
  wd:Q287962
  wd:Q3309122
  wd:Q125688805
  wd:Q3368895
  wd:Q96276426
  wd:Q3219110
  wd:Q2829655
  wd:Q21427050
  wd:Q2965167
  wd:Q33108705
  wd:Q3379637
  wd:Q33112500
  wd:Q73366776
  wd:Q27959694
  wd:Q2966171
  wd:Q2847577
  wd:Q112244796
  wd:Q19629366
  wd:Q64534061
  wd:Q68596060
  wd:Q3571745
  wd:Q97291168
  wd:Q5428149
  wd:Q33200389
  wd:Q2863099
  wd:Q16679907
  wd:Q187901
  wd:Q2833639
  wd:Q2829776
  wd:Q64224878
  wd:Q5562044
  wd:Q3379815
  wd:Q83274731
  wd:Q64349001
  wd:Q68710483
  wd:Q110986116
  wd:Q43629496
  wd:Q125619863
  wd:Q3022687
  wd:Q24940343
  wd:Q3591143
  wd:Q2244569
  wd:Q96056272
  wd:Q20089599
  wd:Q2833695
  wd:Q58356358
  wd:Q3379903
  wd:Q3167157
  wd:Q125868085
  wd:Q3106276
  wd:Q737600
  wd:Q23461501
  wd:Q16678379
  wd:Q2966590
  wd:Q1892624
  wd:Q73157420
  wd:Q3369513
  wd:Q16645490
  wd:Q16268039
  wd:Q133934101
  wd:Q3168545
  wd:Q665234
  wd:Q5927413
  wd:Q980463
  wd:Q96283384
  wd:Q63892372
  wd:Q2863148
  wd:Q3169948
  wd:Q2895868
  wd:Q3121912
  wd:Q2144729
  wd:Q109037512
  wd:Q33102743
  wd:Q3159298
  wd:Q16640679
  wd:Q3380200
  wd:Q124809833
  wd:Q33104183
  wd:Q2965417
  wd:Q3009030
  wd:Q822576
  wd:Q3173521
  wd:Q17486075
  wd:Q2896199
  wd:Q29652447
  wd:Q90132085
  wd:Q63967443
  wd:Q3455759
  wd:Q18547785
  wd:Q3018370
  wd:Q1557548
  wd:Q2895874
  wd:Q33101925
  wd:Q80787823
  wd:Q23926374
  wd:Q1805539
  wd:Q70755363
  wd:Q16034380
  wd:Q94939047
  wd:Q83633336
  wd:Q16645268
  wd:Q2926911
  wd:Q363889
  wd:Q60178747
  wd:Q6687923
  wd:Q2898404
  wd:Q26506507
  wd:Q16195729
  wd:Q68659404
  wd:Q2748495
  wd:Q3123653
  wd:Q33112404
  wd:Q81520484
  wd:Q59622849
  wd:Q15992373
  wd:Q446097
  wd:Q6120800
  wd:Q580118
  wd:Q1396289
  wd:Q23771753
  wd:Q3160368
  wd:Q8334411
  wd:Q33103692
  wd:Q3167241
  wd:Q120416143
  wd:Q1338393
  wd:Q110779163
  wd:Q2272017
  wd:Q1367752
  wd:Q19958558
  wd:Q62197078
  wd:Q2912099
  wd:Q3310761
  wd:Q12131824
  wd:Q4705701
  wd:Q2895081
  wd:Q2918056
  wd:Q15715745
  wd:Q105064021
  wd:Q33120818
  wd:Q81199891
  wd:Q87011903
  wd:Q3310824
  wd:Q2904615
  wd:Q2776768
  wd:Q23926141
  wd:Q2965638
  wd:Q20685695
  wd:Q2965669
  wd:Q3559859
  wd:Q3573984
  wd:Q117616165
  wd:Q87009020
  wd:Q16637394
  wd:Q85432458
  wd:Q532069
  wd:Q1225410
  wd:Q3298892
  wd:Q3124363
  wd:Q120176361
  wd:Q82755582
  wd:Q3169814
  wd:Q2377244
  wd:Q3507196
  wd:Q15613735
  wd:Q20666487
}

  OPTIONAL { ?chef wdt:P569 ?birthDate. }               # Date de naissance
  OPTIONAL { ?chef wdt:P19 ?birthPlace. }               # Lieu de naissance
  OPTIONAL { ?chef wdt:P21 ?gender. }                   # Genre (homme / femme)
  OPTIONAL {
    ?chef wdt:P166 ?award.                                # Distinction reçue
    ?award rdfs:label ?awardLabel.
    FILTER(CONTAINS(LCASE(STR(?awardLabel)), "michelin")) # On filtre les distinctions contenant "michelin"
    FILTER(LANG(?awardLabel) = "fr")                      # En langue française
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
