---
description: Avant, pendant et après les campagnes de production pour le chef de projet
---

# Production

La production du PCRS peut démarre une fois [les phases préliminaires](construction.md) effectuées.

Nous considérons les étapes suivantes dans la production d'un PCRS raster :

<figure><img src="../.gitbook/assets/Capture d’écran du 2024-11-13 18-50-50.png" alt=""><figcaption></figcaption></figure>

## Préparer ses campagnes

### Préparation des plans de vols

Les plans de vols sont généralement des livrables dû par les prestataires de vols qui organisent au mieux les vols en fonction du matériel approprié pour la campagne à conduire.

Il est parfois nécessaire d'obtenir des autorisations de survol, notamment à proximité de zones frontalières ou pour survoler des **ZICAD** (voir ci-dessous).

### Préparation des campagnes lidar

Les campagnes de roulage lidar sont également planifiées en amont, avec moins de contraintes que les vols pour les orthophotographies.

## Production sur le terrain

#### Quand voler ?

Les vols ont traditionnellement lieu au printemps, pour bénéficier d'un éclairage approprié sans que la végétation ait repris un feuillage trop important. Cela n'est pour autant pas une obligation et chaque décideur s'adaptera aux contraintes locales, notamment en matière d'obtention d'autorisation de voler.

## Réception des livrables

Tel que généralement convenu avec le titulaire du marché de production, les livrables attendus le sont au format des [geostandards](../contexte/geostandards/).

Les livrables attendus sont nombreux et divers, il ne s'agit pas que des photos de l'orthophotoplan ou du fichier gml vecteur. Certains fichiers peuvent présenter un intérêt au-delà des vues aériennes réalisées.

Tel qu'expliqué à propos de [la publication](publication.md), nous nous attachons à rendre disponibles les livrables présentant les meilleures capacités de réutilisation. Ce sont généralement les images sans compression ou les fichiers gml de la qualification vecteur.

Avant d'être utilisables, les livrables doivent être contrôlés pour s'assurer de conformité en précision et en résolution.

### Traitement des zones interdites

Les ZICAD (Zones Interdites à la Captation Aérienne de Données, selon [l'arrêté du 10 juin 2021](https://www.legifrance.gouv.fr/download/pdf?id=9NZ_5bE7riPhHKuMazUS5Cu1fmt64dDetDQxhvJZNMc=)) sont des zones pour lesquelles il n'est pas possible de proposer des prises de vues aériennes et le PCRS n'y déroge pas.

Il n'est parfois pas possible de les exclure des plans de vols dans le cadre d'un PCRS photo et des procédures particulières peuvent être mises en place avec les services desquels relèvent les installations concernées. Ils peuvent se charger de l'épuration des campagnes de prises de vue et certifier que les livrables ne comporteront pas d'informations sensibles.

### Compression raster

En matière d'imagerie raster, la possibilité est offerte de compresser les images à l'aide de différents algorithmes de la famille JPEG2000. Initialement en **GeoTiff**, format non compressé, les images peuvent être livrées sous des compression avec pertes sur lesquelles nous vous invitons à la plus grande vigilance.

Certains algorithmes peuvent être propriétaires, en outre payants et ne sont pas compatibles avec des logiciels libres tels qu'[OpenJpeg](https://www.openjpeg.org/). Ils seront pourtant nécessaires pour traiter les dalles en aval et peuvent représenter un surcoût sinon un handicap.

