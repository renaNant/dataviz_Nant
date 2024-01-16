''''sparql

#ID des peintures de Van Gogh
SELECT ?painting
WHERE {
?painting wdt:P170 wd:Q5582.}

#avec les labels et les images en grid 
SELECT *
WHERE {
?painting wdt:P170 wd:Q5582 .
?painting wdt:P18 ?paintingImage .
SERVICE wikibase:label 
{bd:serviceParam wikibase:language "en"}
}

#avec les lieux de conservation et leurs coordonnées géo pour afficher sur une carte 
SELECT ?paintingLabel ?paintingImage ?locationLabel ?coordinate
WHERE {
?painting wdt:P170 wd:Q5582 .
OPTIONAL {
?painting wdt:P18 ?paintingImage .
?painting wdt:P195 ?location.
?location wdt:P625 ?coordinate.
}
SERVICE wikibase:label 
{bd:serviceParam wikibase:language "en"}
}

#compter le nombre de Van gogh dans chaque collection/lieux de conservation et les afficher par ordre décroissant
#Ici n'affiche pas les ?location et ?locationLabel associé à chaque ?count 
SELECT ?location ?locationLabel ?count WHERE {
  {
    SELECT (COUNT(?painting) AS ?count) WHERE {
       ?painting wdt:P170 wd:Q5582. 
       ?painting wdt:P195 ?location.
    } GROUP BY ?location
  } . 
  SERVICE wikibase:label {
    bd:serviceParam wikibase:language "eng" .
  }
}
ORDER BY DESC(?count) ?location
