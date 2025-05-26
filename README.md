## Sujet initial

À l’origine, j’avais choisi de travailler sur les nominées au Ballons d’or de football.  
C’était un sujet qui m’intéressait beaucoup et qui semblait bien correspondre aux attentes du projet : il existe une liste claire de joueurs, beaucoup sont présents sur Wikidata, et on aurait pu imaginer différentes analyses intéressantes (par pays, par club, etc.).

Mais une fois que je me suis plongé dans les recherches, j’ai vite réalisé que la récupération de données vraiment exploitables était très compliquée. Les identifiants QID des joueurs n’étaient pas toujours simples à rassembler, certaines données que je voulais utiliser étaient manquantes ou incomplètes, et en gros, j’ai vite perdu plus de temps que prévu pour trop peu de résultats.

## Nouveau sujet choisi

J’ai donc décidé de changer de population et de partir sur quelque chose de plus stable côté Wikidata :  
→ Les chefs français étoilés Michelin.

Il existe une catégorie bien définie sur Wikipédia, et la plupart des chefs sont bien liés à Wikidata, ce qui m’a permis d’avancer de façon plus concrète dans le projet.

## Limites rencontrées

Même avec ce nouveau sujet, j’ai rapidement compris que la plupart des propriétés intéressantes (établissements, mentor, organisations, distinctions…) sont rarement renseignées.  
Les chefs sont bien présents, mais leurs relations avec d’autres entités sont souvent absentes ou très parcellaires.

Du coup, j’ai dû adapter mes analyses:
- Je me suis concentré sur les informations disponibles en masse, comme le genre, la date de naissance, et le lieu de naissance.
- J’ai fait une analyses bivariées (genre × génération) avec test du Chi-2.
- Malheureusement, je n’ai pas pu faire d’analyse de réseau, car il n’y avait pas assez de relations exploitables pour construire un graphe cohérent.

## Remarque finale

Même si le sujet ne s’est pas prêté à toutes les dimensions du projet comme je l’espérais au départ, le travail sur la récupération de données, les requêtes SPARQL et les notebooks m’a permis d’apprendre beaucoup.  
Et je pense que j’ai réussi à respecter l’essentiel des consignes, tout en adaptant mon projet aux limites concrètes des données disponibles.

