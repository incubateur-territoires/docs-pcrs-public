# Mise à jour - 6 février 2025

**200** participants, séance tenue en ligne de 10h à 13h

[Le replay de l'atelier](https://tube.numerique.gouv.fr/w/nxFYNxy1miVuqDmiwXmMU6) est disponible en ligne

## Introduction

## 1ère partie - Détecter les zones à mettre à jour

### L'exploitation des données du guichet unique

Par Amélie Dogon, [GéoVendée](http://www.geovendee.fr/accueil), Ingrid Brugioni et François-Patrick Marquet, [Territoire d’Énergie Mayenne](https://www.territoire-energie53.fr/)

{% file src="../.gitbook/assets/1_20250602_GEOVENDEE-TE53.pdf" %}

### Les évolutions réglementaires et techniques du guichet unique

Par Christophe Pécoult, [DGPR](https://www.ecologie.gouv.fr/direction-generale-prevention-risques-dgpr) et Eric Tarnaud, [INERIS](https://www.ineris.fr/fr)



{% file src="../.gitbook/assets/2_pcrs_dgpr_ineris.pdf" %}

### La détection des mises à jour des PCRS vecteur

Par Guillaume Gratusse, [SIEDS](https://www.sieds.fr/)

{% file src="../.gitbook/assets/3_Présentation SIEDS.pdf" %}

Questions ayant reçu des réponses après la séance :

#### La méthode de roulage Lidar ne coûte-t-elle pas plus cher que la mise à jour elle-même ?

Cela est très difficile à dire. Tout dépend de la méthode choisie pour cette mise à jour (toutes ayant leurs contraintes et leurs avantages) et la quantité. Si l'on part du principe que l'on connaît précisément les zones à mettre à jour, il est certain que cette étape comparative est inutile et c'est pour cela que nous restons en veille sur le travail effectué sur les DT/DICT par d'autres territoires. La connaissance précise des zones à modifier reste la solution à privilégier mais cette méthode pourrait nous permettre de rattraper le retard pris sur la mise à jour d'autant plus que les informations ajoutées aux CERFA ne le seront qu'à partir de 2025. De notre côté, nous en saurons plus sur notre poursuite ou non dans cette expérimentation d'ici quelques mois.

#### Commentaire en séance : "La méthode proposée est intéressante mais il faut s'assurer que les nouveaux nuages et orthovoiries soient exactement calés parfaitement, les GCP utilisés peuvent changer entre temps et modifier le calage tout en restant dans la classe de précision"

La précision du lidar (et donc des orthovoiries) que l'on demande doit être inférieure à 5cm. De plus, la méthode présentée reste une aide à la décision, cela permet d'établir une carte de chaleur par rapport au changement d'élévation de l'orthovoirie mails l'œil humain reste ensuite obligatoire pour la sélection finale des zones à mettre à jour. L'intelligence artificielle seule ne fait pas encore tout le travail.

#### Qu'en est-il du stockage des données ?&#x20;

Nous ne stockons et diffusons en direct que le PCRS vecteur sur une base postgres (quelques Go). Le lidar (3To) et l'imagerie (4To) issus du mobile mapping le sont par le prestataire (pour 2 400 km), le PCRS image par l'IGN.

#### Quel coût pour une acquisition de ce type au km linéaire ? Combien coûte le lever au km linéaire avant détection ?&#x20;

Nous ne communiquons pas le coût au kilomètre car le faible linéaire ne rend pas celui-ci forcément représentatif.

Le coût global de l'expérimentation est compris entre 5000 et 6000 euros (pour les 17 km de roulage et les 6,5 km de vectorisation). Il est composé d'une partie Acquisition, d'une partie détection et d'une partie vectorisation.

### La détection des mises à jour via l'intelligence artificielle

Par Johann Fradet, [GIP ATGeRi / PIGMA](https://gipatgeri.fr/)

{% file src="../.gitbook/assets/4_20250206_Webinaire_PIGMA.pdf" %}

Questions ayant reçu des réponses après la séance :

#### Quelles sont la surface totale et le linéaire de voirie des 47 zones à mettre à jour dans la présentation ?

La surface totale des nouvelles zones mises à jour, détectées grâce à l'IA à partir des images satellites, est de 1,39 km².

Pour le linéaire de voirie impacté, nous ne raisonnons pas en termes de linéaire de voirie sur un PCRS raster, mais en termes de surface mise à jour.

### La méthodologie développée par le CRAIG

Par Antoine Coignet, [CRAIG](https://www.craig.fr/)



{% file src="../.gitbook/assets/5_PRESENTATION_WEBINAIRE_Antoine COIGNET.pdf" %}

## 2ème partie - Coûts et leviers d'optimisation

### Les coûts associés à la mise à jour différentielle des PCRS raster

Par Sébastien Gaillac, [CRAIG](https://www.craig.fr/)



{% file src="../.gitbook/assets/6_CRAIG Mise-a-Jour-du-PCRS-Couts-associes.pdf" %}

### Le mix technologique Ortho HR / PCRS et satellite à l'IGN

Par Anna Cristofol et Guillaume Valtat, [IGN](https://www.ign.fr/)



{% file src="../.gitbook/assets/7_Presentation IGN_mixte_techno_comite_PCRS.pdf" %}

### La mise à jour mutualisée à l'échelle régionale

Par Johann Fradet, [GIP ATGeRi / PIGMA](https://gipatgeri.fr/)



{% file src="../.gitbook/assets/8_20250206_Webinaire_PIGMA.pdf" %}

### Les gestionnaires de réseaux, quel rôle dans le financement de la mise à jour ?

Par Pierre Nguyen Trong, [GRDF](https://www.grdf.fr/)



{% file src="../.gitbook/assets/8_2025-02-06 prez GRDF .pdf" %}
