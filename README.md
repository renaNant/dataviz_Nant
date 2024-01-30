# Les collections de vêtements et d'accessoires au sein des musées de France: tour d'horizon 

## Introduction 
Dans un objectif d'inventaire des sources matérielles sur l'histoire du vêtement et de la mode, ce projet entend proposer des pistes pour un panorama des vêtements et accessoires conservés dans les musées de France à partir de la base de données _open data_ Joconde. Ce catalogue collectif des musées de France regroupe plus de 660 000 notices d'oeuvres décrivant à partir de critères formels l'artefact concerné.  
A partir des méthodes et outils de traitement et de visualisation des données étudiées en cours, ce projet constitue plus largement un travail préparatoire et réutilisable dans le cadre d'un projet de constitution d'un corpus de sources vestimentaires pour une étude historique. 

## La base Joconde: éléments de contextualisation 
La base de données Joconde est un catalogue collectif de notices d'oeuvres, alimentée par les musées prenant part au projet. Tout musée situé en France peut y contribuer avec les notices de ses collections, dès lors qu'il est accrédité par l'appelation "Musée de France". La base de données est en _open data_, accessible sur la plateforme data.culture.gouv.fr sous licence Ouverte v2.0. <br>
Lien d'accès au jeu de données: https://data.culture.gouv.fr/explore/dataset/base-joconde-extrait/information/?disjunctive.departement 


## Tisser un jeu de données sur mesure: le traitement de la Base Joconde 
La réutilisation de la base Joconde pour étudier les collections vestimentaires a nécessité plusieurs étapes de préparation, de nettoyage et de retraitement des données afin de les rendre potentiellement exploitables pour réaliser des visualisations graphiques pertinentes. <br>
Cependant, la structuration du jeu de données ainsi que la nature même de la notice d'oeuvre, document source de Joconde ont constitué des obstacles importants pour notre objectif de datavisualisation. 
Le jeu de données est tout d'abord conséquent, que ce soit en termes de lignes ou de colonnes. La version utilisée pour ce projet (extraction du 26/01/2024) regroupe en effet 676 599 notices, pour 74 colonnes descriptives. Un fichier de description des colonnes de Joconde est d'ailleurs mis à disposition avec le jeu de données. Un premier travail de nettoyage des colonnes, afin de ne conserver que celles pertinentes pour notre projet, a alors été nécessaire.
De façon connexe, le jeu de données se démarque également par une grande disparité dans la saisie en fonction des oeuvres, des musées et des colonnes, débouchant sur un fichier comportant un nombre très conséquent des valeurs vides et des valeurs uniques. Cette particularité de Joconde a sous-tendu l'ensemble du projet, rendant particulièrement compliqué la réalisation de visualisations significatives. 

### La constitution d'un corpus des collections de vêtements et d'accessoires par partition du corpus initial sur Open Refine
Un première partition du corpus a donc été réalisé, afin d'isoler les notices d'oeuvres décrivant des vêtements et des accessoires vestimentaires.
Le choix retenu a été de s'appuyer sur la colonne "Domaine", en raison de la présence d'une nomenclature partagée par le milieu muséal français sur les noms de domaines des oeuvres. Le mot-clé "Costume" a alors permis de restreindre les notices au sujet de notre projet: les collections vestimentaires. <br>
Ensuite, à partir de ce fichier source, il a été choisi de réaliser plusieurs types de partition afin d''explorer différents axes d'étude des collections vestimentaires des musées de France et de parvenir à l'objectif final de datavisualisation. 

## Partition chronologique: les collections de vêtements et d'accessoires du XIXe siècle 
Un premier axe de visualisation a été de se focaliser sur les objets vestimentaires datés du XIXe siècle, afin de cartographier des sources pour l'histoire du vêtement à cette période. 

<iframe width="100%" height="300px" frameborder="0" allowfullscreen allow="geolocation" src="//umap.openstreetmap.fr/fr/map/carte-des-collections-des-vetements-et-accessoires_1015858?scaleControl=true&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=false&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=none&captionBar=false&captionMenus=true"></iframe><p><a href="//umap.openstreetmap.fr/fr/map/carte-des-collections-des-vetements-et-accessoires_1015858?scaleControl=true&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=false&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=none&captionBar=false&captionMenus=true">Voir en plein écran</a></p>

_Carte des collections des vêtements et accessoires du XIXe siècle conservées en France_

## Partition géographique: focus sur les musées parisiens 




