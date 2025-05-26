# Requête SPARQL — Chefs étoilés avec région de naissance

Cette requête permet d'extraire depuis Wikidata les informations suivantes pour une liste de chefs français étoilés Michelin :

- Leur identifiant Wikidata
- Leur nom (`?chefLabel`)
- Leur date de naissance (`?birthDate`)
- Leur lieu de naissance (`?birthPlaceLabel`)
- Leur **région de naissance** (`?regionLabel`), extraite via `wdt:P131`
- Leur genre (`?genderLabel`)

Elle est conçue pour être utilisée dans le cadre d'une analyse bivariée (par exemple : **région de naissance × génération**).

---

```sparql
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT DISTINCT ?chef ?chefLabel ?birthDate ?birthPlaceLabel ?regionLabel ?genderLabel WHERE {
  VALUES ?chef {
    wd:Q16269549 wd:Q53775759 wd:Q2896218 wd:Q3089575 wd:Q3104895
    wd:Q3120033 wd:Q3134001 wd:Q3147054 wd:Q3191483 wd:Q3196277
    wd:Q3203461 wd:Q3264485 wd:Q3265884 wd:Q3270245 wd:Q3281732
    wd:Q3317311 wd:Q3343924 wd:Q3345148 wd:Q3346850 wd:Q3360384
    wd:Q3373603 wd:Q3384902 wd:Q3413726 wd:Q3424200 wd:Q3440396
    wd:Q3453434 wd:Q3460840 wd:Q3471575 wd:Q3499589 wd:Q3528715
    wd:Q3551015 wd:Q3553743 wd:Q3569706 wd:Q3572219 wd:Q3588981
    wd:Q3627162 wd:Q3667380 wd:Q3677720 wd:Q3691562 wd:Q3693382
    wd:Q3699265 wd:Q3711804 wd:Q3716193 wd:Q3725702 wd:Q3750976
    wd:Q3780154 wd:Q3798786 wd:Q3807744 wd:Q3822066 wd:Q3859757
    wd:Q3860087 wd:Q3861217 wd:Q3867994 wd:Q3875946 wd:Q3900010
    wd:Q3957747 wd:Q3969871 wd:Q4026828 wd:Q4148841 wd:Q4238120
    wd:Q4276304 wd:Q4303114 wd:Q4323561 wd:Q4342172 wd:Q4359981
    wd:Q4375023 wd:Q4380240 wd:Q4421437 wd:Q4437018 wd:Q4483794
    wd:Q4552705 wd:Q4552965 wd:Q4567732 wd:Q4569463 wd:Q4572608
    wd:Q4573911 wd:Q4576632 wd:Q4619644 wd:Q4623968 wd:Q4640563
    wd:Q4669640 wd:Q4671781 wd:Q4696342 wd:Q4709182 wd:Q4717022
    wd:Q4751394 wd:Q4759893 wd:Q4772307 wd:Q4774532 wd:Q4782375
    wd:Q4786186 wd:Q4788614 wd:Q4790537 wd:Q4792503 wd:Q4794220
  }

  OPTIONAL { ?chef wdt:P569 ?birthDate. }
  OPTIONAL { ?chef wdt:P19 ?birthPlace. }
  OPTIONAL {
    ?birthPlace wdt:P131 ?region .
    ?region rdfs:label ?regionLabel .
    FILTER(LANG(?regionLabel) = "fr")
  }
  OPTIONAL { ?chef wdt:P21 ?gender. }

  SERVICE wikibase:label { bd:serviceParam wikibase:language "fr". }
}
```
