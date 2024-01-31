# Les collections de vêtements et d'accessoires au sein des musées de France: tour d'horizon 

## Introduction 
Dans un objectif d'inventaire des sources matérielles sur l'histoire du vêtement et de la mode, ce projet entend proposer des pistes pour un panorama des vêtements et accessoires conservés dans les musées de France à partir de la base de données _open data_ Joconde. Ce catalogue collectif des musées de France regroupe plus de 660 000 notices d'oeuvres décrivant à partir de critères formels l'artefact concerné.  
A partir des méthodes et outils de traitement et de visualisation des données étudiées en cours, ce projet constitue plus largement un travail préparatoire et réutilisable dans le cadre d'un projet de constitution d'un corpus de sources vestimentaires pour une étude historique. 

## La base Joconde: éléments de contextualisation 
La base de données Joconde est un catalogue collectif de notices d'oeuvres, alimentée par les musées prenant part au projet. Tout musée situé en France peut y contribuer avec les notices de ses collections, dès lors qu'il est accrédité par l'appelation "Musée de France". La base de données est en _open data_, accessible sur la plateforme data.culture.gouv.fr sous licence Ouverte v2.0. <br>
[Lien d'accès au jeu de données](https://data.culture.gouv.fr/explore/dataset/base-joconde-extrait/information/?disjunctive.departement) 


## Tisser un jeu de données sur mesure: le traitement de la Base Joconde 
La réutilisation de la base Joconde pour étudier les collections vestimentaires a nécessité plusieurs étapes de préparation, de nettoyage et de retraitement des données afin de les rendre potentiellement exploitables pour réaliser des visualisations graphiques pertinentes. <br>
Cependant, la structuration du jeu de données ainsi que la nature même de la notice d'oeuvre, document source de Joconde ont constitué des obstacles importants pour notre objectif de datavisualisation. Un sprint qualité du fichier .csv a donc été réalisé afin de cartographier les principales problématiques concernant les données de la base Joconde: [Sprint qualité du fichier d'export en .csv de la Base Joconde](https://github.com/renaNant/dataviz_Nant/blob/main/BaseJoconde_SprintQualite_CSV.pdf) 

Le jeu de données est tout d'abord conséquent, que ce soit en termes de lignes ou de colonnes. La version utilisée pour ce projet (extraction du 26/01/2024) regroupe en effet 676 599 notices, pour 74 colonnes descriptives. Un fichier de description des colonnes de Joconde est d'ailleurs mis à disposition avec le jeu de données. Un premier travail de nettoyage des colonnes, afin de ne conserver que celles pertinentes pour notre projet, a alors été nécessaire. Ci-joint [l'historique des traitements OpenRefine réalisé pour cette première version de l'export](https://github.com/renaNant/dataviz_Nant/blob/main/BaseJoconde_V1_TraitementsColonnes.json). 

Comme indiqué dans le sprint qualité, le jeu de données se caractérise par une grande disparité dans la saisie des valeurs: en fonction des oeuvres, des musées et des colonnes. Cela débouche sur un fichier comportant un nombre très conséquent des valeurs vides et des valeurs uniques. Cette particularité du fichier de la base Joconde a sous-tendu l'ensemble du projet, rendant particulièrement compliqué la réalisation de visualisations significatives. 

### La constitution d'un corpus des collections de vêtements et d'accessoires par partition du corpus initial sur Open Refine
Un première partition du corpus a donc été réalisé, afin d'isoler les notices d'oeuvres décrivant des vêtements et des accessoires vestimentaires.
Le choix retenu a été de s'appuyer sur la colonne "Domaine", en raison de la présence d'une nomenclature partagée par le milieu muséal français sur les noms de domaines des oeuvres. Le mot-clé "Costume" a alors permis de restreindre les notices au sujet de notre projet: les collections vestimentaires. Ci-joint la version du fichier qui ne contient que les notices d'objets vestimentaires ou reliés au domaine vestimentaire. En effet, le champ sur le domaine de l'oeuvre étant multivalué, cette stratégie de récupération de la thématique "Vêtements" moissonne également des oeuvres qui ne sont formellement des vêtements ou des accessoires de vêtements. 
Voici le lien vers le fichier des [traitements effectués sur OpenRefine pour parvenir à la version de la Base Joconde qui ne contient que les oeuvres considérées comme relevant de la thématique "Costumes"](https://github.com/renaNant/dataviz_Nant/blob/main/BaseJoconde_Costumes_Traitements.json). 
Voici le lien de téléchargement du fichier de la [section Costumes de la base de données Joconde, fichier d'où proviennent les partitions utilisées pour les visualisation de ce projet](https://we.tl/t-u1gp2b1CfK). 

Ensuite, à partir de cette section Costumes extrait de la Base Joconde, il a été choisi de réaliser plusieurs types de partition du fichier afin d''explorer différents axes d'étude des collections vestimentaires des musées de France et de parvenir à l'objectif final de datavisualisation. 

## Panorama des collections rattachées au domaine Vêtements et Accessoires conservées dans les musées français 

En utilisant cette section Costumes de la base Joconde, explorons les principales tendances à l'oeuvre dans les collections rattachées au domaine vestimentaire et conservées en France. 

Quelle est la répartition et la proportion des oeuvres rattachées au domaine vestimentaire en fonction des régions, des départements et des villes de France? 
<iframe src='https://flo.uri.sh/visualisation/16640918/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/16640918/?utm_source=embed&utm_campaign=visualisation/16640918' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>

Ce sunburst permet de réperer la forte concentration de ce type d'objets dans certaine régions de France, dans les Hauts-de-France, en Île de France et en Auvergne. 

## Partition chronologique: les collections de vêtements et d'accessoires du XIXe siècle 
Un premier axe de visualisation a été de se focaliser sur les objets vestimentaires datés du XIXe siècle, afin de cartographier des sources pour l'histoire du vêtement à cette période. 
Afin de réaliser cette partition chronologique, un traitement important des valeurs de datation saisies dans le jeu de données a été nécessaire, face à la grande hétérogénéité des notations de dates. La représentativité chronologique de ce corpus vis-à-vis des données initiales est donc à questionner. 

<iframe width="100%" height="300px" frameborder="0" allowfullscreen allow="geolocation" src="//umap.openstreetmap.fr/fr/map/carte-des-collections-des-vetements-et-accessoires_1015858?scaleControl=true&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=false&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=none&captionBar=false&captionMenus=true"></iframe><p><a href="//umap.openstreetmap.fr/fr/map/carte-des-collections-des-vetements-et-accessoires_1015858?scaleControl=true&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=false&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=none&captionBar=false&captionMenus=true">Voir en plein écran</a></p>
_Carte des collections des vêtements et accessoires du XIXe siècle conservées en France_
Pour cette carte, voici le lien vers le [fichier utilisé](https://github.com/renaNant/dataviz_Nant/blob/main/BaseJoconde-Costumes-19e-20e.csv). 

A côté des lieux de conservation des objets, leur datation est également cruciale dans un objectif de recherche historique sur le XIXe siècle. C'est pourquoi nous avons tenté d'étudier la répartition chronologique des dates de création tout au long du siècle. 

<iframe title="Répartition chronologique des oeuvres du corpus &quot;XIXe siècle&quot; par date de création estimée" aria-label="Nuage de points" id="datawrapper-chart-Thide" src="https://datawrapper.dwcdn.net/Thide/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="720" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r=0;r<e.length;r++)if(e[r].contentWindow===a.source){var i=a.data["datawrapper-height"][t]+"px";e[r].style.height=i}}}))}();
</script>
Important: 1830 valeurs n'étaient pas renseignées pour la colonne Periode_de_creation à partir de laquelle les données sur les dates de création des oeuvres ont été extraites. Cette visualisation est donc très partielle. 
Il est nécessaire de rappeler ici que la base Joconde comporte plusieurs colonnes relatives à la datation de l'oeuvre, dont la saisie varie en fonction de plusieurs facteurs: type d'objet, pratique de saisies des musées, notation de la date en période temporelle. Le traitement important des dates rend possible les valeurs extrêmes hors du XIXe siècle visibles sur le graphique. 


## Partition géographique: focus sur les collections vestimentaires des musées parisiens 
Suite à ce premier aperçu général de la répartition sur l'ensemble du territoire français hexagonal des collections vestimentaires, il a été choisi de spécialiser l'étude à l'échelle des musées de Paris. 
D'une part, Paris abrite deux institutions dotées des plus grandes collections de mode et de textile du monde, avec le Musée des Arts Décoratifs et le Palais Galliera. De plus, à côté de deux géants, il serait intéressant d'étudier si d'autres institutions muséales parisiennes abritent également des objets vestimentaires. 

Où sont conservés les collections vestimentaires à Paris? 
_*insérer carte_


Ici, nous avons choisi de visualiser la proportion d'objets vestimentaires par type d'usage. 

<iframe title="Répartition par type d'objet des costumes et d'accessoires du costume conservés dans les musées parisiens " aria-label="Tracé de points" id="datawrapper-chart-CB5gC" src="https://datawrapper.dwcdn.net/CB5gC/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="386" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r=0;r<e.length;r++)if(e[r].contentWindow===a.source){var i=a.data["datawrapper-height"][t]+"px";e[r].style.height=i}}}))}();
</script>

Enfin, à partir de valeurs réconcilées avec Wikidata dans OpenRefine, il est possible de comparer la fréquentation des musées parisiens conservant des collections vestimentaires. 






