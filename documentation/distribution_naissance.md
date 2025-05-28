
# Questionnement 2 – Répartition des dates de naissance des chefs étoilés Michelin

## Question de départ

Existe-t-il une période de naissance particulièrement représentée chez les chefs français étoilés Michelin ? Cette répartition peut-elle refléter des dynamiques historiques, générationnelles ou professionnelles dans le champ de la gastronomie française ?

---

## Données utilisées

Les données ont été extraites de Wikidata à l’aide d’une requête SPARQL. Nous avons utilisé une liste de QID de chefs français étoilés Michelin, puis récupéré leur date de naissance (propriété `P569`).

Ces données ont ensuite été stockées dans un fichier CSV `wdt_donnees_chefs.csv` traité dans un notebook Jupyter pour visualiser la distribution des années de naissance.

---

## Méthode

1. **Collecte** : Requête SPARQL incluant les propriétés suivantes :
   - `wdt:P569` pour la date de naissance
   - `wdt:P19` pour le lieu de naissance
   - `wdt:P21` pour le genre
   - Filtrée via une liste manuelle de QID collectés sur Wikipédia

2. **Nettoyage et transformation** :
   - Conversion des dates de naissance en années
   - Suppression des valeurs manquantes

3. **Visualisation** :
   - Histogramme par tranches temporelles d’années (bins)

---

## Graphique à insérer

> 📊 Histogramme de la répartition des dates de naissance (à intégrer à partir du notebook `wdt_distribution_naissances_chefs.ipynb`)

---

## Interprétation

La visualisation montre une concentration marquée des naissances entre les **années 1950 et 1980**. Ce pic peut être expliqué par plusieurs facteurs :

- Le **Guide Michelin**, bien que créé en 1900, a commencé à attribuer des étoiles en 1920. Son prestige a mis du temps à s’installer.
- Dans les premières décennies, les critères d’évaluation étaient encore jeunes, peu connus, et parfois plus restrictifs.
- L’intérêt professionnel à viser une étoile est devenu plus fort à partir de l’après-guerre, ce qui coïncide avec la montée de la notoriété du guide.
- À l’inverse, les **chefs nés après les années 1980** sont naturellement moins représentés : l’obtention d’une étoile demande **du temps, de l’expérience et une certaine maturité professionnelle**.
- Peu de chefs obtiennent une étoile avant leurs 35 ou 40 ans, ce qui explique le creux sur les générations plus récentes.

---

## Conclusion

Ce graphique permet de mieux comprendre **la temporalité d’entrée dans le champ gastronomique reconnu par le guide Michelin**.  
Il met en évidence un effet générationnel significatif, à la fois lié à la montée du prestige du guide dans les décennies d’après-guerre, et à l’âge requis pour atteindre un tel niveau de reconnaissance.

