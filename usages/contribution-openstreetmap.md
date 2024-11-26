---
description: >-
  Utilisation des vues aériennes et de certaines données vecteur pour la
  contribution à OSM
---

# Contribution OpenStreetMap

## Contexte

La contribution au projet OpenStreetMap peut consister à vectoriser des objets depuis des vues aériennes, entre bien d'autres moyens d'obtenir des données, en particulier depuis le terrain.

Les vues aériennes, comme les plans vecteurs servent depuis de nombreuses années à cela, à différentes échelles et toujours en suivant l'évolution des meilleures qualités d'imagerie disponibles. Cela a été le cas des [images de Bing Maps](https://blog.openstreetmap.org/2010/11/30/microsoft-imagery-details/) en 2010 ou de [la BDOrtho pour l'IGN](https://www.openstreetmap.fr/bdortho/) en 2016 ou même de [vues aériennes 5cm](https://www.openstreetmap.fr/convention-dechange-de-donnees-entre-enedis-et-openstreetmap-france/) fournies par Enedis en 2021.

Il semble logique que les images produites par les projets PCRS puissent alimenter ces moyens de contribution de manière similaire. Cela suppose que les ressources aient été publiées selon une licence compatible avec cette activité, idéalement la licence ouverte et qu'une infrastructure de diffusion adaptée soit en place.

Les données vecteurs peuvent aussi présenter un intérêt en pouvant être plus facilement importées directement sans avoir à être redessinée. On pense par exemple aux contours de bâtiments ou de voirie.\
Ces données vectorielles peuvent non seulement être importées ou bien servir de référence à un contrôle qualité comme de nombreuses autres données ouvertes.

## Utilisateurs

Les contributeurs OpenStreetMap accèdent actuellement aux vues aériennes des PCRS raster dans la plupart des solutions d'édition du projet en ajoutant l'URL WMTS des services de l'IGN et en choisissant la ressource PCRS.LAMB93.

```
https://wxs.ign.fr/ortho/geoportail/wmts?SERVICE=WMTS&VERSION=1.0.0&REQUEST=GetCapabilities
```

Cette contribution consiste bien souvent à vectoriser des vues aériennes, dériver des objets OSM de ces vues aériennes pour les ajouter dans la base de données. Cette vectorisation est d'autant plus facile que la résolution des images est fine. La précision du calage de ces ressources est intéressante sans constituer toutefois un intérêt de tout premier plan : la précision des contribution OSM est plus faible et ce projet ne prévoit pas de certification d'aucune sorte de cette précision.

**En WGS84**, la disponibilité des niveaux de zoom 22 & 23 est également déterminante pour bénéficier d'une qualité raster suffisante pour le PCRS, sans pour autant empêcher la contribution à OSM avec le niveau 21 qui offre déjà une haute résolution (7.5 cm/pixel).

**En Lambert 93**, le zoom 21 suffit pour obtenir une résolution de 4.9 cm/pixels.

Le détail des pyramides WGS84 et Lambert 93 est disponible dans [la documentation du service](https://geoservices.ign.fr/documentation/services/api-et-services-ogc/images-tuilees-wmts-ogc#1592) IGN.

Il n'existe pour l'instant pas d'usage concret des données vectorielles du fait de leur relative absence de publication pour l'instant, bien que des PCRS vecteurs soient déjà largement produits.

## Cadre spatio-temporel

L'usage d'imagerie raster est dominant et ce depuis la mise à disposition du service WMTS sur le Géoportail IGN.\
Ces imageries pourront également être reprises au gré des possibilités de téléchargement et de service via d'autres moyens.

La disponibilité de ces imageries est asservie aux projets en cours et à leur diffusion sous des licences adaptées, une surface couverte en croissance donc.

Concernant les données vectorielles, leur disponibilité et utilisabilité dans des mécanismes d'import ou de contrôle qualité sont conditionnées par les solutions existantes d'exploitation du [format GML](../contexte/geostandards/#implementation).

## Aller plus loin

### Intervention au SOTM France 2023

[Replay vidéo disponible](https://peertube.openstreetmap.fr/w/iUvqRk6w4T8tqfVk7J3gFY).

{% file src="../.gitbook/assets/20230609_prez_osm.pdf" %}

### Intervention au SOTM France 2024

[Replay vidéo disponible](http://peertube.openstreetmap.fr/w/xryYzTDDesnPKWgkqdntKF)

{% file src="../.gitbook/assets/20240629_prez_osm.pdf" %}
