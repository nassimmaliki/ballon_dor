
# Répartition des chefs étoilés par genre

## 1. Contexte

Ce questionnement s’intéresse à la répartition des chefs étoilés Michelin selon leur genre, en s’appuyant sur les données disponibles sur Wikidata.  
Il s’agit d’un sujet particulièrement pertinent dans le cadre d’une réflexion prosopographique, car il met en lumière les dynamiques d’inégalités et les rapports de domination symbolique dans le champ de la haute gastronomie.

L’objectif est d’évaluer si des disparités importantes existent dans l’accès à cette reconnaissance professionnelle, et d’en proposer une lecture sociologique.

---

## 2. Méthodologie

Nous avons extrait les données grâce à une requête SPARQL portant sur une population d’un peu plus de 200 chefs français étoilés, identifiés à partir de la catégorie Wikipédia : [Catégorie:Chef français étoilé Michelin](https://fr.wikipedia.org/wiki/Cat%C3%A9gorie:Chef_fran%C3%A7ais_%C3%A9toil%C3%A9_Michelin).

Les identifiants Wikidata (QIDs) ont été récupérés, puis une requête SPARQL a permis de collecter les propriétés suivantes : nom, date de naissance, lieu de naissance, et genre (`wdt:P21`).  
Les résultats ont été exportés en CSV, puis analysés dans un notebook Jupyter (`wdt_repartition_genre_chefs.ipynb`).

La visualisation a été réalisée sous forme de diagramme à barres, avec Matplotlib, montrant le nombre total d’hommes et de femmes dans l’échantillon.

---

## 3. Résultat visuel

Le graphique généré montre une très forte domination des hommes parmi les chefs étoilés référencés dans Wikidata. Les femmes représentent une minorité extrêmement réduite de cette population.

*(Insérer ici le graphique depuis le notebook si tu fais une version HTML)*

---

## 4. Interprétation

Les données montrent une inégalité flagrante : la profession de chef étoilé reste largement masculine.  
Cette observation ne peut pas être simplement imputée à des choix individuels : elle reflète une structure sociale profondément marquée par des mécanismes d’exclusion symbolique et institutionnelle.

Plusieurs facteurs peuvent expliquer cette répartition inégalitaire :

- **Accès plus difficile aux postes à visibilité** pour les femmes dans les cuisines professionnelles, souvent très hiérarchisées et marquées par une culture masculine.
- **Biais historiques** dans la médiatisation et la valorisation des carrières : les figures de chefs promues dans les médias sont très majoritairement masculines.
- **Effets d’habitus et de reproduction sociale** : le champ gastronomique reproduit des normes de genre traditionnelles, valorisant le chef homme comme figure d’autorité.

---

## 5. Limites et prolongements

- Les données proviennent de Wikidata, qui n’est pas une base exhaustive. Certaines femmes peuvent être sous-représentées.
- Le genre est une donnée relativement bien renseignée mais reste parfois absente pour quelques individus.
- Cette première analyse univariée pourrait être enrichie par une **analyse croisée** avec les générations (voir deuxième questionnement), pour vérifier s’il y a une évolution récente de la répartition hommes/femmes.

---

## 6. Conclusion

La répartition genrée des chefs étoilés offre un aperçu clair des rapports de pouvoir dans le champ gastronomique.  
Cette inégalité observée est cohérente avec les analyses de Pierre Bourdieu sur la reproduction sociale et les mécanismes de distinction.

Ce premier questionnement pose ainsi une base solide pour explorer plus largement les structures d’exclusion à l’œuvre dans cette population.

---
