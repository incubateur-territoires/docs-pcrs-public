---
description: Modèle de données en construction - v0.1 du 09/12/2022
---

# Modèle de données v0.1

<mark style="color:red;">**Cette version est archivée - reportez-vous à**</mark> [<mark style="color:red;">**la version en cours**</mark>](./)

Les entités suivantes servent de support aux propositions d'uniformisation du suivi des projets et à la construction d'un annuaire des APLC dans le cadre de notre feuille de route.

Ce modèle est en cours de construction et évoluera régulièrement au gré des retours et propositions reçues dans le cadre de nos travaux. N'hésitez pas [à nous contacter](https://pcrs.beta.gouv.fr/#contact) pour échanger à son propos.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

## Entités

### Projets PCRS

Inventaire des projets.

Un projet correspond à une campagne de levers, diffusés après recette.

Une campagne de mise à jour peut être entreprise sur un territoire complètement différent sans référence à la production initiale.

<table><thead><tr><th width="205">Champ</th><th width="152.33333333333331">Type</th><th width="138">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>idProjet</td><td>UUID</td><td></td><td>Identifiant interne du projet</td></tr><tr><td>nom</td><td>Texte</td><td>Super PCRS</td><td>Nom du projet</td></tr><tr><td>regime</td><td>l_pcrs_regime</td><td>production</td><td>Régime du projet</td></tr><tr><td>nature</td><td>l_pcrs_nature</td><td>vecteur</td><td>Nature (vecteur/raster)</td></tr><tr><td>licence</td><td>l_pcrs_licence</td><td>ouvert_lo</td><td>Disponibilité du livrable</td></tr><tr><td>diffusion</td><td>l_pcrs_diffusion</td><td>flux</td><td>Diffusion du livrable</td></tr><tr><td>livrable</td><td>l_pcrs_livrable</td><td>gml</td><td>Nature du livrable</td></tr></tbody></table>

### Étapes des projets

Statut rencontrés par l'un ou l'autre des projets. Les statuts se suivent sans se chevaucher pour un même projet, dans l'ordre de leur date de début.

<table><thead><tr><th width="206">Champ</th><th width="142">Type</th><th width="141">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>refProjet</td><td>UUID</td><td></td><td>Référence du projet concerné</td></tr><tr><td>statut</td><td>l_pcrs_statut</td><td>vecteur</td><td>Statut du projet</td></tr><tr><td>date_debut</td><td>Date</td><td>2022-01-03</td><td>Date de début du statut</td></tr></tbody></table>

### Périmètres des projets

Nous serons prochainement amenés à préciser d'avantage le formalisme du champ territoires ci-dessous.

<table><thead><tr><th width="207">Champ</th><th width="141">Type</th><th width="140">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>refProjet</td><td>UUID</td><td></td><td>Référence du projet concerné</td></tr><tr><td>territoires</td><td>Texte</td><td></td><td>Liste des territoires, séparés par ,</td></tr></tbody></table>

### Annuaire acteurs

Acteurs et leurs coordonnées. Un acteur représente toute personne morale, y compris l'APLC, impliquée dans un ou plus projets.

<table><thead><tr><th width="210">Champ</th><th width="143">Type</th><th width="139">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>idActeur</td><td>UUID</td><td></td><td>Identifiant de l'acteur</td></tr><tr><td>siren</td><td>Texte</td><td></td><td>SIREN de l'entreprise</td></tr><tr><td>nom</td><td>Texte</td><td></td><td>Nom de l'acteur</td></tr><tr><td>interlocuteur</td><td>Texte</td><td></td><td>Interlocuteur privilégié</td></tr><tr><td>mail</td><td>Texte</td><td></td><td>Mail de l'interlocuteur</td></tr><tr><td>telephone</td><td>Texte</td><td></td><td>Téléphone de l'interlocuteur</td></tr></tbody></table>

### Acteurs des projets

Association des acteurs et des projets et leur rôle. Un même acteur peut disposer de différents rôle suivant le projet dans lequel il intervient.

<table><thead><tr><th width="212.33333333333331">Champ</th><th width="144">Type</th><th width="138">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>refProjet</td><td>UUID</td><td></td><td>Référence du projet</td></tr><tr><td>refActeur</td><td>UUID</td><td></td><td>Référence de l'acteur</td></tr><tr><td>role</td><td>l_pcrs_role</td><td>diffuseur</td><td>Rôle de l'acteur dans le projet</td></tr></tbody></table>

## Listes de valeur

### Statut des projets

l\_pcrs\_statut

<table><thead><tr><th width="258">Valeur</th><th width="126.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>investigation</td><td></td><td>Projet en préparation/investigation</td></tr><tr><td>production</td><td></td><td>Projet financé en cours de production</td></tr><tr><td>produit</td><td></td><td>Projet produit en cours de recette</td></tr><tr><td>livre</td><td></td><td>Projet livré</td></tr><tr><td>obsolete</td><td></td><td>Projet obsolète</td></tr></tbody></table>

### Nature PCRS

l\_pcrs\_nature

<table><thead><tr><th width="258">Valeur</th><th width="125.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>vecteur</td><td></td><td>PCRS vecteur</td></tr><tr><td>raster</td><td></td><td>PCRS raster</td></tr><tr><td>mixte</td><td></td><td>PCRS mixte (vecteur + raster)</td></tr></tbody></table>

### Rôles des acteurs

l\_pcrs\_role

<table><thead><tr><th width="258">Valeur</th><th width="131.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>aplc</td><td></td><td>Autorité Publique Locale Compétente</td></tr><tr><td>financeur</td><td></td><td>Financeur</td></tr><tr><td>diffuseur</td><td></td><td>Diffuseur des livrables</td></tr><tr><td>presta_vol</td><td></td><td>Prestataire de vol</td></tr><tr><td>presta_lidar</td><td></td><td>Prestataire de relevé LIDAR</td></tr><tr><td>controleur</td><td></td><td>Contrôleur des livrables</td></tr></tbody></table>

### Nature des livrables

l\_pcrs\_livrable

<table><thead><tr><th width="259">Valeur</th><th width="132.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>geotiff</td><td></td><td>Livrable GeoTIFF</td></tr><tr><td>gml</td><td></td><td>Livrable GML vecteur</td></tr></tbody></table>

### Licence des livrables

l\_pcrs\_licence

<table><thead><tr><th width="260">Valeur</th><th width="140.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>ouvert_lo</td><td></td><td>Ouvert sous licence ouverte</td></tr><tr><td>ouvert_odbl</td><td></td><td>Ouvert sous licence ODbL</td></tr><tr><td>ferme</td><td></td><td>Fermé</td></tr></tbody></table>

### Diffusion des livrables

l\_pcrs\_diffusion

<table><thead><tr><th width="260">Valeur</th><th width="144.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>telechargement</td><td></td><td>Téléchargement massif</td></tr><tr><td>flux</td><td></td><td>Accès via un serveur/flux</td></tr></tbody></table>

### Régime des projets

l\_pcrs\_regime

<table><thead><tr><th width="258">Valeur</th><th width="146.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>production</td><td></td><td>Production initiale</td></tr><tr><td>maj</td><td></td><td>Mise à jour</td></tr></tbody></table>
