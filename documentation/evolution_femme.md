# Évolution du nombre de femmes chefs étoilés par génération

## Questionnement

Est-ce que la présence des femmes parmi les chefs étoilés a augmenté avec le temps ?  
Autrement dit, y a-t-il une progression générationnelle dans l'accès des femmes à cette reconnaissance professionnelle ?

## Données utilisées

Les données sont issues de Wikidata, à partir d'une liste de chefs français étoilés Michelin.  
Chaque chef est identifié par son QID, et pour chacun on a collecté son genre (`wdt:P21`) et sa date de naissance (`wdt:P569`).

## Méthode

- Extraction des données via une requête SPARQL.
- Regroupement des chefs par génération selon leur année de naissance (tranches de 20 ans).
- Filtrage des femmes uniquement pour bien visualiser leur évolution.
- Visualisation par histogramme.
- Test du Chi-2 sur la répartition femmes / générations.

## Graphique

(Insérer ici le graphique `nombre_femmes_par_generation.png` ou l’image exportée depuis le notebook)

## Interprétation

Le graphique montre que le nombre de femmes chefs étoilés reste très faible sur l’ensemble des générations.  
On pourrait s’attendre à une augmentation progressive au fil du temps, mais les données montrent que cette progression inexistante.

Cela reflète une inégalité persistante dans l'accès à la reconnaissance professionnelle dans le champ de la haute gastronomie.  
Cette inégalité peut s’expliquer par plusieurs facteurs :
- une moindre médiatisation historique des femmes chefs,
- des freins structurels à leur accès aux postes les plus visibles,
- un biais de sélection ou de valorisation masculine dans les institutions comme le guide Michelin.

Le test du Chi-2 confirme statistiquement que la répartition par génération n’est pas significativement différente: les femmes restent toujours sous-représentées, génération après génération.

## Conclusion

Malgré les avancées sociales et les débats publics sur l'égalité, la haute gastronomie semble encore marquée par une forte domination masculine.  
Les chefs femmes sont toujours une minorité dans les classements les plus prestigieux, et cela semble peu avoir évolué au fil des décennies.
