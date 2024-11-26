---
description: Accéder aux données produites par le workflow de suivi du PCRS
---

# Données brutes

Conformément à notre démarche de suivi portée par la donnée, les données brutes sont librement restituées via une API.

## Licence

Les données restituées le sont sous le régime de la [Licence Ouverte Etalab 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence/).

Parmi les obligations qu'elle prescrit, il est nécessaire de mentionner le producteur des données concernées pour tout usage :

> Données ANCT - PCRS.beta.gouv.fr et porteurs de projets locaux

### Données complémentaires

Parmi les données que nous réutilisons, certaines sont produites par l'IGN et transformées par l'Etalab, notamment pour les contours administratifs.

Elles sont disponibles sous licence ouverte Etalab 2.0 à l'adresse : [http://etalab-datasets.geo.data.gouv.fr/contours-administratifs/](http://etalab-datasets.geo.data.gouv.fr/contours-administratifs/)

## API de restitution

Les données sont restituées selon une teneur proche de celle du modèle de données proposé, à quelques adaptations près nécessaire au mode d'échange.

Certains champs répondent à des listes de valeurs fermées dont la définition est disponible dans le [modèle de données](modele-de-donnees/) en vigueur. Utilisez la colonne Origine dans les tables de structure ci-dessous pour vous y rendre.

Nos fichiers suivent le format CSV [RFC 4180](https://datatracker.ietf.org/doc/html/rfc4180).

Nos données géographiques sont restituées selon [la projection WGS84](https://epsg.io/4326).

### Projets

Le fichier contient la liste des projets assortis de leur calendrier selon la structure suivante.

#### Appel

HTTP GET [https://pcrs.beta.gouv.fr/data/projets.csv](https://pcrs.beta.gouv.fr/data/projets.csv)

La colonne _geometries_ est obtenue en ajoutant un paramètre includesWkt=1

HTTP GET https://pcrs.beta.gouv.fr/data/projets.csv?includesWkt=1

#### Structure

<table><thead><tr><th width="249">Champ</th><th width="209.33333333333331">Origine</th><th>Commentaire</th></tr></thead><tbody><tr><td>id_projet</td><td>projets.idProjet</td><td>UUID du projet</td></tr><tr><td>nom</td><td>projets.nom</td><td>Nom du projet</td></tr><tr><td>regime</td><td>projets.regime</td><td>Régime du projet</td></tr><tr><td>nature</td><td>projets.nature</td><td>Nature du projet</td></tr><tr><td>budget</td><td>projets.budget</td><td>Budget complet du projet en €TTC</td></tr><tr><td>statut</td><td>status.statut</td><td>Statut courant</td></tr><tr><td>investigation_date</td><td>statuts.date_debut</td><td>Date de début d'investigation</td></tr><tr><td>convention_signee_date</td><td>statuts.date_debut</td><td>Date de signature de la convention</td></tr><tr><td>marche_public_en_cours_date</td><td>statuts.date_debut</td><td>Date d'ouverture du marché public</td></tr><tr><td>prod_en_cours_date</td><td>statuts.date_debut</td><td>Date de début de production</td></tr><tr><td>controle_en_cours_date</td><td>statuts.date_debut</td><td>Date du contrôle</td></tr><tr><td>realise_date</td><td>statuts.date_debut</td><td>Date de livraison</td></tr><tr><td>disponible_date</td><td>statuts.date_debut</td><td>Date de publication</td></tr><tr><td>obsolete_date</td><td>statuts.date_debut</td><td>Date d'obsolescence</td></tr><tr><td>geometrie</td><td>Agrégation des périmètres</td><td>WKT d'un multipolygone entourant le projet - <a href="https://epsg.io/4326">WGS84</a></td></tr></tbody></table>

### Territoires

Il s'agit de l'association entre les projets et les différentes entités administratives qu'ils couvrent, identifiées par leur nature et leur identifiant INSEE (communes, départements) ou SIRET (EPCI).

#### Appel

HTTP GET [https://pcrs.beta.gouv.fr/data/territoires.csv](https://pcrs.beta.gouv.fr/data/territoires.csv)

Structure

<table><thead><tr><th width="189">Champ</th><th width="203">Origine</th><th>Commentaire</th></tr></thead><tbody><tr><td>ref_projet</td><td>projets.idProjet</td><td>Identifiant du projet</td></tr><tr><td>nature_territoire</td><td>projets.perimetres[][0]</td><td>Nature du territoires (departement, commune, epci)</td></tr><tr><td>reference</td><td>projets.perimetres[][1]</td><td>Référence du territoire (INSEE ou SIRET)</td></tr></tbody></table>

### Livrables

Les livrables correspondent aux productions de chaque projet

#### Appel

HTTP GET [https://pcrs.beta.gouv.fr/data/livrables.csv](https://pcrs.beta.gouv.fr/data/livrables.csv)

#### Structure

<table><thead><tr><th width="235.33333333333331">Champ</th><th width="206">Origine</th><th>Commentaire</th></tr></thead><tbody><tr><td>ref_projet</td><td>livrables.refProjet</td><td>UUID du projet</td></tr><tr><td>nom_projet</td><td>projets.nom</td><td>nom du projet</td></tr><tr><td>nom</td><td>livrables.nom</td><td>nom du livrable</td></tr><tr><td>nature</td><td>livrables.nature</td><td>nature du livrable</td></tr><tr><td>date_livraison</td><td>livrables.date_livraison</td><td>Date de livraison du livrable</td></tr><tr><td>licence</td><td>livrables.licence</td><td>Licence du livrable</td></tr><tr><td>diffusion</td><td>livrables.diffusion</td><td>Mode de diffusion du livrable</td></tr><tr><td>diffusion_url</td><td>livrables.diffusion_url</td><td>URL vers un descripteur du service de diffusion</td></tr><tr><td>diffusion_layer</td><td>livrables.diffusion_layer</td><td>Nom de la couche du service de diffusion</td></tr><tr><td>stockage</td><td>livrables.stockage</td><td>Technologie de stockage du livrable</td></tr><tr><td>stockage_public</td><td>livrables.stockage_public</td><td>Publicité des informations de connexion</td></tr><tr><td>avancement</td><td>livrables.avancement</td><td>Avancement de la production</td></tr><tr><td>recouvr_lat</td><td>livrables.recouvr_lat</td><td>Recouvrement latéral des clichés du livrable</td></tr><tr><td>recouvr_lon</td><td>livrables.recouvr_lon</td><td>Recouvrement longitudinal des clichés du livrable</td></tr><tr><td>focale</td><td>livrables.focale</td><td>Valeur de la focale utilisée</td></tr><tr><td>cout</td><td>livrables.cout</td><td>Coût complet de production du livrable</td></tr><tr><td>publication</td><td>déprécié</td><td>Déprécié</td></tr><tr><td>crs</td><td>déprécié</td><td>Déprécié</td></tr><tr><td>compression</td><td>déprécié</td><td>Déprécié</td></tr></tbody></table>

### Tours de table

Le tour de table correspond à l'association des acteurs et des projets. Ils sont munis d'un rôle.

Nous y trouvons les données de financement.

#### Appel

HTTP GET [https://pcrs.beta.gouv.fr/data/tours-de-table.csv](https://pcrs.beta.gouv.fr/data/tours-de-table.csv)

#### Structure

<table><thead><tr><th width="239.33333333333331">Champ</th><th width="234">Origine</th><th>Commentaire</th></tr></thead><tbody><tr><td>ref_projet</td><td>acteurs_projets.refProjet</td><td>UUID du projet</td></tr><tr><td>nom_projet</td><td>projets.nom</td><td>Nom du projet</td></tr><tr><td>nom_acteur</td><td>acteurs.nom</td><td>Nom de l'acteur</td></tr><tr><td>siren_acteur</td><td>acteurs.siren</td><td>SIREN de l'acteur</td></tr><tr><td>interlocuteur</td><td>acteurs.interlocuteur</td><td>Interlocuteur auprès de l'acteur</td></tr><tr><td>mail</td><td>acteurs.mail</td><td>Mail pour contacter l'acteur</td></tr><tr><td>telephone</td><td>acteurs.telephone</td><td>Téléphone pour contacter l'acteur</td></tr><tr><td>role</td><td>acteurs_projets.role</td><td>Rôle de l'acteur dans le projet</td></tr><tr><td>finance_part_perc</td><td>acteurs_projet.finance_part_perc</td><td>Part de financement de l'acteur dans le projet</td></tr><tr><td>finance_part_euro</td><td>acteurs_projets.finance_part_euro</td><td>Montant de financement de l'acteur dans le projet</td></tr></tbody></table>

### Subventions

Les subventions sont des financements particuliers, exprimés selon leur nature.

#### Appel

HTTP GET [https://pcrs.beta.gouv.fr/data/subventions.csv](https://pcrs.beta.gouv.fr/data/subventions.csv)

#### Structure

<table><thead><tr><th width="240.33333333333331">Champ</th><th width="241">Origine</th><th>Commentaire</th></tr></thead><tbody><tr><td>ref_projet</td><td>subventions.refProjet</td><td>UUID du projet</td></tr><tr><td>nom_projet</td><td>projets.nom</td><td>Nom du projet</td></tr><tr><td>nom</td><td>subventions.nom</td><td>Nom de la subvention</td></tr><tr><td>nature</td><td>subventions.nature</td><td>Nature de la subvention</td></tr><tr><td>montant</td><td>subventions.montant</td><td>Montant de la subvention</td></tr><tr><td>echeance</td><td>subventions.echeance</td><td>Échéance de la subvention</td></tr></tbody></table>

### Dernières éditions

La liste des dernières opérations effectuées sur les projets connus du suivi.

Chaque projet n'y apparaît qu'une fois, ainsi seule la dernière opérations effectuée sur chacun n'est visible.

#### Appel

HTTP GET [https://pcrs.beta.gouv.fr/data/changes.csv](https://pcrs.beta.gouv.fr/data/changes.csv)

#### Structure

| Champ        | Origine          | Commentaire                                |
| ------------ | ---------------- | ------------------------------------------ |
| ref\_projet  | projets.idProjet | Identifiant du projet                      |
| nom\_projet  | projets.nom      | Nom du projet                              |
| action       |                  | Action effectuées (create, update, delete) |
| update\_date |                  | Date de l'action                           |

## Entités du géostandard

Notre API ne les restitue pas directement, il est pour autant possible de reconstituer les entités prescrites par [le géostandard PCRS](../contexte/geostandards/) dédiée au suivi.

Ces entités sont largement complétées lorsque le porteur de projet [met à disposition](publication-des-livrables.md) un stockage public que nous pouvons inspécter pour les déterminer à partir de l'étude des livrables.

Nous en rappelons les structures ci-dessous, les URL d'appel sont à venir très prochainement.

#### Initiatives

Conforme à la classe InitiativePCRS (§B.3.1 du géostandard)

Cette entité n'est pour l'instant pas restituée par notre API.

<table><thead><tr><th width="182">Champ</th><th width="234.33333333333331">Origine</th><th>Commentaires</th></tr></thead><tbody><tr><td>description</td><td>projets.nom</td><td>Nom du projet</td></tr><tr><td>gestionnaire</td><td>acteurs.nom</td><td>Nom de l'acteur muni du rôle APLC ou porteur</td></tr><tr><td>partenaires</td><td>acteurs.nom</td><td>Liste des noms des acteurs autres que l'APLC ou porteur</td></tr><tr><td>geometrie</td><td>Agrégation des périmètres</td><td>Objet GM_MultiSurface représentant l'emprise du projet</td></tr></tbody></table>

#### Emprises disponibilité PCRS

Appel : HTTP GET [https://pcrs.beta.gouv.fr/data/stockages/livrables.geojson](https://pcrs.beta.gouv.fr/data/stockages/livrables.geojson)

L'emprise livrable est équivalent à l'entité EmpriseDisponibilitePCRS (§B.3.2 du géostandard). Les <mark style="background-color:purple;">champs surlignés</mark> sont des extensions remplies par l'étude des livrables.

Les géométries restituées sont constituées par l'agrégation des emprises d'un ensemble de dalles raster, pouvant donner une impression de crénelage sur son périmètre. Les dalles raster prises en compte sont celles qui ont été correctement analysées par [nos solutions d'indexation](publication-des-livrables.md) des stockages associés aux livrables concernés. Les dalles vides ou corrompues ne seront pas intégrées au résultat.

<table><thead><tr><th width="188">Champ</th><th width="184.33333333333331">Type</th><th>Commentaires</th></tr></thead><tbody><tr><td>geometrie</td><td>Polygon</td><td>L'emprise géographique du livrable - <a href="https://epsg.io/4326">WGS84</a></td></tr><tr><td>initiative</td><td>UUID</td><td>Identifiant du projet PCRS auquel correspond le livrable</td></tr><tr><td>dateActualite</td><td>date</td><td>Date de début du statut en cours (calendrier)</td></tr><tr><td>calendrier</td><td>Texte</td><td>Code statut correspondant à l'état de disponibilité du livrable</td></tr><tr><td><mark style="background-color:purple;">format</mark></td><td>l_pcrs_livrable</td><td>Mime des fichiers</td></tr><tr><td><mark style="background-color:purple;">compression</mark></td><td>l_pcrs_compression</td><td>Compression des fichiers</td></tr><tr><td><mark style="background-color:purple;">epsg</mark></td><td>Texte</td><td>EPSG du livrable</td></tr><tr><td><mark style="background-color:purple;">taille</mark></td><td>Texte</td><td>Taille de livrable en pixels</td></tr><tr><td><mark style="background-color:purple;">recouvrLat</mark></td><td>Flottant</td><td>Recouvrement latéral des clichés du livrable</td></tr><tr><td><mark style="background-color:purple;">recouvrLon</mark></td><td>Flottant</td><td>Recouvrement longitudinal des clichés du livrable</td></tr><tr><td><mark style="background-color:purple;">focale</mark></td><td>Entier</td><td>Distance focale (pour les PVA)</td></tr><tr><td><mark style="background-color:purple;">licence</mark></td><td>l_pcrs_licence</td><td>Licence du livrable concerné</td></tr><tr><td><mark style="background-color:purple;">subventions</mark></td><td>l_pcrs_subvention []</td><td>Liste des natures de subventions ayant contribué au financement du projet concerné</td></tr><tr><td><mark style="background-color:purple;">acteurs</mark></td><td>Texte</td><td>Liste des acteurs participants au projet concerné</td></tr><tr><td><mark style="background-color:purple;">diffusionUrl</mark></td><td>Texte</td><td>URL vers le service de diffusion du livrable concerné</td></tr><tr><td><mark style="background-color:purple;">diffusionLayer</mark></td><td>Texte</td><td>Nom de la couche dans le service de diffusion</td></tr></tbody></table>

Pour traduire les statuts en valeurs de la CalendrierPCRSType, utiliser la correspondance suivante

| Statut PCRS               | CalendrierPCRSType |
| ------------------------- | ------------------ |
| investigation             | 03                 |
| convention\_signee        | 03                 |
| marche\_public\_en\_cours | 03                 |
| prod\_en\_cours           | 02                 |
| controle\_en\_cours       | 02                 |
| realise                   | 01                 |
| disponible                | 01                 |
| obsolete                  | 01                 |

#### Emprise dalle raster

Appel : HTTP GET [https://pcrs.beta.gouv.fr/data/stockages/dalles.geojson](https://pcrs.beta.gouv.fr/data/stockages/dalles.geojson)

Pour chaque dalle raster, on produit une géométrie correspondant à son enveloppe (une boite de 200m x 200m environ). Elles sont conformes à la classe RasterPCRS (§B.3.38 du géostandard). Les <mark style="background-color:purple;">champs surlignés</mark> sont des extensions remplies par l'étude des livrables.

Elles sont munie des attributs suivants :

<table data-header-hidden><thead><tr><th width="308.3333333333333">Champ</th><th width="181">Type</th><th>Commentaires</th></tr></thead><tbody><tr><td>geometrie</td><td>Polygon</td><td>L'emprise géographique de la dalle - <a href="https://epsg.io/4326">WGS84</a></td></tr><tr><td>dateAcquisition</td><td>date</td><td>Date du vol correspondant à la dalle</td></tr><tr><td>dateRecette</td><td>date</td><td>Date d'intégration dans le PCRS. <strong>A laisser vide</strong></td></tr><tr><td>descriptionElementsQualite</td><td>Texte</td><td>Description des éléments de qualité de l'image. <strong>A laisser vide</strong></td></tr><tr><td>idPCRS</td><td>UUID</td><td>Identifiant du projet PCRS concerné</td></tr><tr><td>nomImage</td><td>Texte</td><td>Nom de la dalle</td></tr><tr><td>précisionplanimétriqueCorpsdeRue</td><td>CategoriePrecisionPCRSType</td><td>Niveau de précision de l'image au niveau du corps de rue. <strong>A laisser vide</strong></td></tr><tr><td>precisionplanimetriqueZonesNaturelles</td><td>CategoriePrecisionPCRSType</td><td>Niveau de précision de l'image au niveau des zones naturelles. <strong>A laisser vide</strong></td></tr><tr><td>resolution</td><td>Entier</td><td>Taille en cm du côté d'un pixel</td></tr><tr><td><mark style="background-color:purple;">typeImage</mark></td><td>l_pcrs_livrable</td><td>Mime du fichier (Jpeg2000, geotiff...)</td></tr><tr><td>producteur</td><td>Texte</td><td>Nom du producteur de l'image. <strong>A laisser vide</strong></td></tr><tr><td><mark style="background-color:purple;">licence</mark></td><td>l_pcrs_licence</td><td>Licence du fichier image</td></tr><tr><td><mark style="background-color:purple;">tailleFichier</mark></td><td>Texte</td><td>Taille de l'image en pixels</td></tr><tr><td><mark style="background-color:purple;">tailleImage</mark></td><td></td><td></td></tr><tr><td><mark style="background-color:purple;">compression</mark></td><td>l_pcrs_compression</td><td>Mode de compression</td></tr><tr><td><mark style="background-color:purple;">epsg</mark></td><td>Texte</td><td>EPSG du fichier</td></tr><tr><td><mark style="background-color:purple;">bandes</mark></td><td>Json</td><td>Bandes qualifiant les pixels de l'image, voir ci-dessous</td></tr><tr><td><mark style="background-color:purple;">open</mark></td><td>Booléen</td><td>Booléen indiquant l'accessibilité du fichier avec des pilotes ouverts ou non</td></tr><tr><td><mark style="background-color:purple;">focale</mark></td><td>Entier</td><td>Distance focale (pour les PVA)</td></tr></tbody></table>

### Méthode

La reconstitution des entités ci-dessus passe par la réutilisation des colonnes correspondantes des exports en utilisant les colonnes Origine.

Bien qu'il s'agisse à l'origine de classes GML, nous prenons le parti de références par les clés primaires en variante. Il sera aisé d'adapter le processus de production selon la mise en oeuvre choisie.

## Propositions d'évolutions

Ces API ainsi que le modèle de données associé ne sont pas parfaits et peuvent évoluer. N'hésitez pas à formuler vos demandes sur [notre dépôt GitHub](https://github.com/openpcrs/pcrs.beta.gouv.fr) ou [les canaux de contact](https://pcrs.beta.gouv.fr/#contact) habituels.
