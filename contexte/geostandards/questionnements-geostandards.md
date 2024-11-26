---
description: Recensement des questions posées sur le standard actuels
---

# Questionnements geostandards

Ces questionnements pourront donner lieu à des contributions lors de futures réflexions sur l'avenir du géostandard.

## Méta-données des projets

Ces questionnements touchent particulièrement l'équivalence entre les classes ud géostandard et notre [modèle de données](../../suivi-des-projets/modele-de-donnees/) décrivant les projets.

### Production des entités InitiativePCRS, EmpriseDisponibilitePCRS

La production des entités descriptives pose quelques problèmes de normalisation.

Dans InitiativePCRS, les acteurs sont énumérés dans une liste de chaînes de texte, sans pouvoir leur associer différents attributs. Cela mériterait d'être le cas, ne serait-ce que pour indiquer leur rôle et leur SIRET. Le champ description devrait être complété par un nom de l'initiative.

Nous comprenons que l'esprit de la classe EmpriseDisponibilitePCRS est de distinguer l'ambition de l'initiative et ce qui est effectivement disponible à une date donnée. Il faudrait alors pouvoir documenter des livrables et leur associer un avancement. La disponibilité étant l'agrégation de ces emprises.\
Il semblerait que la classe EmpriseEchangePCRS puisse quant à elle représenter de tels livrables sans que ce soit tout à fait clair.

Nous proposons par ailleurs [des extensions](../../suivi-des-projets/donnees-brutes.md) à ces entités basées sur le scanner des livrables.

## PCRS Vecteur

### Usages du XSD

Différentes questions surgissent à propos des pratiques autour du XSD décrivant le format GML.

#### Documentation

Des incohérences sont remarquées entre la documentation PDF et le XSD en lui-même :

* Dans la classe PilierRegulierPCRS, les champ longueur\_mm/largeur\_mm sont appelés longueur/largeur dans le XSD

#### Décrire des affleurants

Il serait possible de décrire les affleurants de plusieurs manières : en imbriquant la représentation géométrique ou en la liant avec un attribut xlink:href sans que nous puissions dire quelles sont les conditions qui permettent de préférer l'une ou l'autre.

#### Initialiser une base de données

Comment initialiser une base de données sur cette base ? Voir [la discussion](https://forum.pcrs.beta.gouv.fr/t/production-de-pcrs-vectoriels/123) sur le forum.

## PCRS Raster

La modélisation du PCRS raster est minimale dans le géostandard actuel.

### Projections des livrables

Le géostandard indique dans son §B.1.4 un ensemble de projections et systèmes de coordonnées prévus au décret 2000-1276 sans pour autant fixer une projection particulière pour les livrables raster.

Ce choix laissé au porteurs de projets ne défini pas exactement quelles seront les propriétés des livrables finaux. Nous cherchons à en savoir plus sur l'ampleur exacte de ces choix et la diversité des pratiques existantes.
