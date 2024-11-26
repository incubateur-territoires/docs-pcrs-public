---
description: >-
  Page de référence à propos des différents géostandards existants définissant
  les formats d'échange prévus
---

# Géostandards

Sur cette page vous trouverez les informations les plus importantes à propos des géostandards existants sans chercher à les paraphraser. Il est recommandé de se référer aux documents officiels, dont les liens sont données avant toute autre chose ici.

Puisqu'il existe des différences sensibles entre PCRS et anti-endommagement, plusieurs géostandards distincts existent et couvrent des périmètres différents.

## Format d'échange PCRS

[**Accéder au document officiel du format d'échange**](http://cnig.gouv.fr/IMG/documents_wordpress/2019/02/CNIG_RTGE_PCRS_v2.0_r1.pdf) sur le site du CNIG, ou localement ci-dessous.

{% file src="../../.gitbook/assets/CNIG_RTGE_PCRS_v2.0_r1.pdf" %}

La seconde version du format d'échange a été validée par le CNIG le 21 septembre 2017, lui conférant le statut de géostandard.

Les contributeurs se sont réunis pour définir un ensemble de règles auxquelles devait se conformer un fond de plan pour être qualifié de PCRS. Il est nécessaire de suivre l'ensemble de ces dispositions pour qu'un fond de plan puisse être qualifié de PCRS, ce n'est pas à la carte.

Il faut rappeler que [la réglementation](../reglementation/) ne prescrit pas quel doit être le contenu d'un tel plan, il s'agit d'un consensus des acteurs métiers auquel la réglementation se réfère. Le CNIG quant à lui opère la certification du document sur la forme, d'après un cahier des charge commun.

### Principales caractéristiques

#### Qualité

Le PCRS servant de fond de plan pour la cotation des réseaux dans le cadre de la directive anti-endommagement, la précision du positionnement des objets et la résolution des images sont deux qualités strictement encadrées.

Le géostandard indique que les objets vectoriels comme les images raster doivent être de précision 10 centimètres au niveau du corps de rue. A noter que cette précision n'est pas obligatoire lorsque l'imagerie aérienne sert de fond de plan informel aux objets d'un PCRS vecteur.\
La résolution adéquate des images raster pour l'utiliser comme fond de plan est de 5 centimètres.

Ces valeurs de qualité ne sont pas explicitement transcrites dans le cadre réglementaire.

#### Modélisation vectorielle

Au moins pour la forme vectorielle, nous disposons d'une structure permettant de décrire un certains nombre d'objets définis dans un catalogue. Ces objets sont usuellement décrits à l'aide de lignes ou de points afin de constituer un Corps de Rue Simplifié. Les choix de modélisation sont hérités de la norme INSPIRE.

Le PCRS cherchant à représenter finement les objets du Corps de Rue, ses constituants ne forment pas nécessairement un réseau topologique continu. La relation entre des points de lever et les objets linéaires, surfaciques ou même ponctuels est beaucoup plus importante.

L'amplitude temporelle du PCRS est modélisée de deux façons, à la fois sur les objets du plan comme propriété thématique, par exemple correspondant à la dernière date de lever mais aussi en tant que méta-données en ce qui concerne le cycle de vie du plan lui-même.

#### Implémentation vectorielle

Toujours pour la partie vectorielle, il a été choisi de réaliser une implémentation [GML](https://fr.wikipedia.org/wiki/Geography_Markup_Language) 3.2.1 (conforme ISO 19136) basée sur le profil Simple Feature Profile.

Des schémas XSD sont fournis afin d'en faciliter la prise en main.

Il est recommandé de placer toutes les entités GML présentes dans le PCRS à fournir dans le même fichier afin d'en faciliter les liens. Les fichiers rasters accompagnant les fichiers GML décrivant leur emprise devront se trouver dans le même répertoire que ces derniers.

### Vecteur et raster

La seconde version du format PCRS ajoute une composante raster aux solutions possibles pour produire un fond de plan conforme.

Sur un territoire donné, il est possible de produire un fond de plan raster ou vecteur ou les deux en fonction des moyens financiers et humains disponibles. Ils sont complémentaires.

<table><thead><tr><th width="136.33333333333331">Nature</th><th>Forces</th><th>Faiblesses</th></tr></thead><tbody><tr><td>Vectorielle</td><td><ul><li>Données uniformes, cataloguées</li><li>Pas de zones d'ombre</li><li>Intègre la cote Z sans besoin de MNT</li></ul></td><td><ul><li>Faibles capacité de captation à grande échelle, nécessite des campagnes roulées</li><li>Nouvelles campagnes après une évolution du catalogue</li></ul></td></tr><tr><td>Raster</td><td><ul><li>Captation à grande échelle, via des campagnes aéroportées</li><li>Capacité à augmenter l'extraction de données sans avoir à revoler</li></ul></td><td><ul><li>Une vectorisation est nécessaire pour extraire des données depuis les images</li><li>Possibles zones d'ombre</li><li>Nécessite un MNT pour l'altitude</li></ul></td></tr></tbody></table>

A l'éclairage de ce comparatif, le mode raster apparaît plus rapidement opérationnel avec une faible rupture vis à vis des pratiques existantes alors que le fond de plan vectoriel, plus ambitieux nécessite de plus lourds moyens tout en permettant les usages les plus variés.

**Bien qu'il ne s'agisse pas d'un PCRS**, illustrons la nature vecteur par cette réalisation d'un [plan topographique](https://sig.nanterre.fr/app/web/aob/?config=configs/theme/Topographie.json) sur le territoire de la ville de Nanterre.

## Autres formats d'échange

D'autres formats d'échange sont définis à proximité du PCRS et il est utile de les mentionner ici, sans prétendre en faire une description extensive. Cela ne touchant pas directement l'activité de production ou de maintenance d'un fond de plan PCRS.

### Star-DT

[**Accéder au document officiel du format d'échange**](http://cnig.gouv.fr/IMG/documents_wordpress/2019/11/CNIG_STAR-DT_v1.0.pdf) sur le site du CNIG ou localement ci-dessous

{% file src="../../.gitbook/assets/CNIG_STAR-DT_v1.0.pdf" %}

Star-DT est un géostandard construit afin de fluidifier les processus de réponse aux Déclarations de Travaux (voir la réglementation). Initialement, il s'agissait d'impressions combinant fond de plan grande échelle et projection des génératrices supérieures d'ouvrages souterrains qu'il était fastidieux de compiler dans le cadre des projets de travaux (chaque exploitant renvoyait sa réponse et le bureau d'étude devait l'assembler, avec tous les risques de dégradation de la qualité que cela comporte).

Il a été approuvé le 15 novembre 2019 et est en cours d'implémentation auprès des acteurs concernés (gestionnaires d'infrastructures, éditeurs logiciels et prestataires d'aide à la déclaration.

Il ne change pas le périmètre des informations attendues suite aux DT-DICT, il adapte ces processus aux moyens numériques disponibles.

#### Modélisation

Star-DT se veut un complément au géostandard PCRS et ne le remplace pas. Il permet la transmission de données et non de documents figés en réponse à une DT-DICT.

Il hérite de concepts d'INSPIRE, d'[IMKL](https://overheid.vlaanderen.be/help/klipimkl-formaat/imkl-23) et du géostandard PCRS. Il propose une implémentation du format de données en GML également.
