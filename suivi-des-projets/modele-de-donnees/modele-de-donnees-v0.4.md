# Modèle de données v0.4

<mark style="color:red;">**Cette version est archivée - reportez-vous à**</mark> [<mark style="color:red;">**la version en cours**</mark>](./)

Les entités suivantes servent de support au suivi des projets et à l'annuaire des APLC.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Les versions archivées de ce modèle de données sont disponibles en pages inférieures.\
Les <mark style="background-color:green;">ajouts</mark>, <mark style="background-color:orange;">modifications</mark> ou <mark style="background-color:red;">suppressions</mark> par rapport à la précédente version.

#### Changelog

* v 0.1 : version initiale, telle que présentée le 09/12/2022
* v 0.2 : Ajout du financement propre des acteurs, subventions et livrables
* v 0.3 : Meilleure qualification des livrables, distinction publication/diffusion
* v 0.4 : Version en cours / Ajout du stockage, ajout de statuts pour l'investigation

## Entités

#### Légende des symboles

❗ Le champ est obligatoire\
🔑 Le champ constitue une clé primaire

### Projets PCRS

Inventaire des projets.

Un projet correspond à une campagne de levers, diffusés après recette.

Une campagne de mise à jour peut être entreprise sur un territoire complètement différent sans références à la production initiale.

<table><thead><tr><th width="205">Champ</th><th width="152.33333333333331">Type</th><th width="138">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>id_rojet 🔑</td><td>UUID</td><td></td><td>Identifiant interne du projet</td></tr><tr><td>nom ❗</td><td>Texte</td><td>Super PCRS</td><td>Nom du projet</td></tr><tr><td>regime ❗</td><td>l_pcrs_regime</td><td>production</td><td>Régime du projet</td></tr><tr><td>nature ❗</td><td>l_pcrs_nature</td><td>vecteur</td><td>Nature (vecteur/raster)</td></tr></tbody></table>

### Étapes des projets

Statut rencontré par l'un ou l'autre des projets. Les statuts se suivent sans se chevaucher pour un même projet, dans l'ordre de leur date de début.

<table><thead><tr><th width="206">Champ</th><th width="142">Type</th><th width="141">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>ref_projet 🔑</td><td>UUID</td><td></td><td>Référence du projet concerné</td></tr><tr><td>statut 🔑</td><td>l_pcrs_statut</td><td>produit</td><td>Statut du projet</td></tr><tr><td>dateDebut ❗</td><td>Date</td><td>2022-01-03</td><td>Date de début du statut</td></tr></tbody></table>

### Périmètres des projets

<table><thead><tr><th width="207">Champ</th><th width="105">Type</th><th width="158">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>ref_projet 🔑</td><td>UUID</td><td></td><td>Référence du projet concerné</td></tr><tr><td>territoires</td><td>Texte</td><td>commune:74010</td><td>Pointeur du territoire</td></tr></tbody></table>

Les pointeurs de territoires sont des chaînes composées d'une nature et d'un identifiant SIREN ou INSEE.

Les natures prévues sont les suivantes

* Commune : commune:_code\_insee_
* EPCI : epci:_code\_SIREN_
* Département : departement:_code\_insee_

### Livrables des projets

<table><thead><tr><th width="206.33333333333331">Champ</th><th width="171">Type</th><th width="126">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>id_livrable 🔑</td><td>UUID</td><td></td><td>Identifiant du livrable</td></tr><tr><td>ref_projet ❗</td><td>UUID</td><td></td><td>Référence du projet concerné</td></tr><tr><td>nom ❗</td><td>Texte</td><td></td><td>Nom du livrable</td></tr><tr><td>nature ❗</td><td>l_pcrs_livrable</td><td>gml</td><td>Nature du livrable</td></tr><tr><td>date_livraison</td><td>Date</td><td>2022-02-01</td><td>Date de livraison</td></tr><tr><td>licence ❗</td><td>l_pcrs_licence</td><td>ouvert_lo</td><td>Licence du livrable</td></tr><tr><td><mark style="background-color:red;">publication</mark></td><td>l_pcrs_publication</td><td>ftp</td><td>Mode de publication</td></tr><tr><td>diffusion</td><td>l_pcrs_diffusion</td><td>wms</td><td>Mode de diffusion</td></tr><tr><td><mark style="background-color:green;">stockage</mark></td><td>l_pcrs_stockage</td><td>http</td><td>Nature du stockage du livrable</td></tr><tr><td><mark style="background-color:green;">stockage_params</mark></td><td>json</td><td></td><td>Configuration pour le stockage</td></tr><tr><td><mark style="background-color:green;">stockage_public</mark> </td><td>booléen</td><td>true / false</td><td>Affichage des identifiants ou non</td></tr><tr><td><mark style="background-color:green;">stockage_telechargement</mark></td><td>booléen</td><td>true / false</td><td>Possibilité du téléchargement des fichiers ou non</td></tr><tr><td>avancement</td><td>Réel</td><td>42.12</td><td>%age de progression dans la construction du livrable</td></tr><tr><td><mark style="background-color:red;">crs</mark></td><td>Texte</td><td>EPSG:2154</td><td>Identifiant EPSG du livrable</td></tr><tr><td><mark style="background-color:red;">compression</mark></td><td>Texte</td><td></td><td>Nature de compression</td></tr></tbody></table>

Retrait des champs <mark style="background-color:red;">crs</mark> et <mark style="background-color:red;">compression</mark> qui sont des méta-données attachées au stockage.

Les livrables peuvent être utiles pour distinguer des blocs dans un projet non phasé. Il est alors commode de définir un livrable par bloc, généralement publiés mais non diffusés. La diffusion intervenant sur un livrable supplémentaire, agrégé.

#### <mark style="background-color:green;">Paramètres de stockage (stockage\_params)</mark>

HTTP

<table><thead><tr><th width="207.33333333333331">Champ</th><th width="134">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td><mark style="background-color:green;">url</mark></td><td></td><td>URL désignant une ressource de stockage</td></tr></tbody></table>

FTP

| Champ                                                 | Exemple        | Définition                     |
| ----------------------------------------------------- | -------------- | ------------------------------ |
| <mark style="background-color:green;">host</mark>     | ftp.bidule.com |                                |
| <mark style="background-color:green;">port</mark>     | 21             |                                |
| <mark style="background-color:green;">username</mark> |                | Optionnel si mode anonymous    |
| <mark style="background-color:green;">password</mark> |                | Optionnel si mode anonymous    |
| <mark style="background-color:green;">path</mark>     | path/to/data   | Optionnel, \`/\` par défaut    |
| <mark style="background-color:green;">secure</mark>   |                | true / false (false par défaut |

### Annuaire acteurs

Acteurs et leurs coordonnées

<table><thead><tr><th width="210">Champ</th><th width="143">Type</th><th width="139">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>id_acteur 🔑</td><td>UUID</td><td></td><td>Identifiant de l'acteur</td></tr><tr><td>siren❗</td><td>Texte</td><td>410201164</td><td>SIREN de l'entreprise</td></tr><tr><td>nom</td><td>Texte</td><td>RGD SMB</td><td>Nom de l'acteur</td></tr><tr><td>interlocuteur</td><td>Texte</td><td>Chef projet</td><td>Interlocuteur privilégié</td></tr><tr><td>mail</td><td>Texte</td><td></td><td>Mail de l'interlocuteur</td></tr><tr><td>telephone</td><td>Texte</td><td></td><td>Téléphone de l'interlocuteur</td></tr></tbody></table>

### Acteurs des projets

Association des acteurs et des projets et leur rôle

<table><thead><tr><th width="212.33333333333331">Champ</th><th width="144">Type</th><th width="138">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>ref_projet 🔑</td><td>UUID</td><td></td><td>Référence du projet</td></tr><tr><td>ref_acteur 🔑</td><td>UUID</td><td></td><td>Référence de l'acteur</td></tr><tr><td>role ❗</td><td>l_pcrs_role</td><td>diffuseur</td><td>Rôle de l'acteur dans le projet</td></tr><tr><td>finance_part_perc</td><td>Réel</td><td>45.2</td><td>Part de financement en pourcentage du total</td></tr><tr><td>finance_part_euro</td><td>Réel</td><td>56652.2</td><td>Part de financement en euros</td></tr></tbody></table>

#### Expression pourcentage / montant numéraire

Le pourcentage est entendu subventions comprises

### Subventions des projets

<table><thead><tr><th width="212">Champ</th><th width="147">Type</th><th width="140">Exemple</th><th>Définition</th></tr></thead><tbody><tr><td>id_subvention 🔑</td><td>UUID</td><td></td><td>Identifiant local de la ligne de subvention</td></tr><tr><td>ref_projet ❗</td><td>UUID</td><td></td><td>Référence du projet</td></tr><tr><td>nom ❗</td><td>Texte</td><td>Feder</td><td>Nom de la subvention</td></tr><tr><td>nature ❗</td><td>l_pcrs_subvention</td><td>feder</td><td>Nature de la subvention</td></tr><tr><td>montant </td><td>Réel</td><td>56454.23</td><td>Montant de la subvention</td></tr><tr><td>echeance</td><td>Date</td><td>2021-03-15</td><td>Date à laquelle la subvention expire</td></tr></tbody></table>

## Listes de valeur

### Statut des projets

l\_pcrs\_statut

<table><thead><tr><th width="258">Valeur</th><th width="126.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>investigation</td><td></td><td>Projet en préparation/investigation</td></tr><tr><td><mark style="background-color:green;">convention_signee</mark></td><td></td><td>Partenaires réunis et convention signée</td></tr><tr><td><mark style="background-color:green;">marche_public_en_cours</mark></td><td></td><td>Phase marché public en cours d'instruction</td></tr><tr><td><mark style="background-color:orange;">prod_en_cours</mark></td><td></td><td>Projet en cours de production</td></tr><tr><td><mark style="background-color:orange;">controle_en_cours</mark></td><td></td><td>Production terminée, en cours de contrôle</td></tr><tr><td><mark style="background-color:orange;">disponible</mark></td><td></td><td>Projet contrôlé et disponible</td></tr><tr><td>obsolete</td><td></td><td>Projet obsolète</td></tr></tbody></table>

### Nature PCRS

l\_pcrs\_nature

<table><thead><tr><th width="258">Valeur</th><th width="125.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>vecteur</td><td></td><td>PCRS vecteur</td></tr><tr><td>raster</td><td></td><td>PCRS raster</td></tr><tr><td>mixte</td><td></td><td>PCRS mixte (vecteur + raster)</td></tr></tbody></table>

### Rôles des acteurs

l\_pcrs\_role

<table><thead><tr><th width="258">Valeur</th><th width="131.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>aplc</td><td></td><td>Autorité Publique Locale Compétente</td></tr><tr><td>porteur</td><td></td><td>Porteur de projet non APLC</td></tr><tr><td>financeur</td><td></td><td>Financeur</td></tr><tr><td>diffuseur</td><td></td><td>Diffuseur des livrables</td></tr><tr><td>presta_vol</td><td></td><td>Prestataire de vol</td></tr><tr><td>presta_lidar</td><td></td><td>Prestataire de relevé LIDAR</td></tr><tr><td>controleur</td><td></td><td>Contrôleur des livrables</td></tr></tbody></table>

### Nature des livrables

l\_pcrs\_livrable

<table><thead><tr><th width="259">Valeur</th><th width="132.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td><mark style="background-color:orange;">image/tiff</mark></td><td>geotiff</td><td>Livrable GeoTIFF</td></tr><tr><td><mark style="background-color:orange;">image/jp2</mark></td><td>jpeg2000</td><td>Livrable Jpeg 2000</td></tr><tr><td><mark style="background-color:orange;">application/gml+xml</mark></td><td>gml</td><td>Livrable GML vecteur</td></tr></tbody></table>

### Licence des livrables

l\_pcrs\_licence

<table><thead><tr><th width="260">Valeur</th><th width="140.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>ouvert_lo</td><td></td><td>Ouvert sous licence ouverte</td></tr><tr><td>ouvert_odbl</td><td></td><td>Ouvert sous licence ODbL</td></tr><tr><td>ferme</td><td></td><td>Fermé</td></tr></tbody></table>

### <mark style="background-color:green;">Compression des livrables</mark>

<mark style="background-color:green;">l\_pcrs\_compression</mark>

<table><thead><tr><th width="260.3333333333333">Valeur</th><th width="145">Alias</th><th>Définition</th></tr></thead><tbody><tr><td><mark style="background-color:green;">none</mark></td><td></td><td>Aucune compression</td></tr><tr><td><mark style="background-color:green;">jpeg2000_lossy</mark></td><td></td><td></td></tr><tr><td><mark style="background-color:green;">geotiff_lzw</mark></td><td></td><td>Lossless sur dictionnaire</td></tr><tr><td><mark style="background-color:green;">geotiff_packbits</mark></td><td></td><td>Lossless</td></tr><tr><td><mark style="background-color:green;">geotiff_deflate</mark></td><td></td><td>Lossless LZ77 + Huffman</td></tr><tr><td><mark style="background-color:green;">geotiff_lzma</mark></td><td></td><td>Lossless LZ77 + range</td></tr><tr><td><mark style="background-color:green;">geotiff_zstd</mark></td><td></td><td>Lossless de facebook</td></tr></tbody></table>

Documentation sur les compressions :

* [Geotiff sur Mapscraping](https://mapscaping.com/geotiff-compression-techniques/)

### <mark style="background-color:green;">Stockage des livrables</mark>

<mark style="background-color:green;">l\_pcrs\_stockage</mark>

<table><thead><tr><th width="260">Valeur</th><th width="140.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>http</td><td></td><td>Stockage sur serveur HTTP via index ou csv (détection automatique)</td></tr><tr><td>ftp</td><td></td><td>Stockage sur serveur FTP(S)</td></tr><tr><td>sftp</td><td></td><td>Stockage sur serveur SFTP</td></tr></tbody></table>

### Publication des livrables (deprecated)

<mark style="background-color:red;">l\_pcrs\_publication</mark>

<table><thead><tr><th width="263.3333333333333"></th><th width="141"></th><th></th></tr></thead><tbody><tr><td><mark style="background-color:red;">ftp</mark></td><td></td><td>Accès via FTP</td></tr><tr><td><mark style="background-color:red;">cloud</mark></td><td></td><td>Accès via un service cloud (oneDrive...)</td></tr><tr><td><mark style="background-color:red;">http</mark></td><td></td><td>Accès via service HTTP(S)</td></tr><tr><td><mark style="background-color:red;">inexistante</mark></td><td></td><td>Aucun moyen d'accès en ligne</td></tr></tbody></table>

### Diffusion des livrables

l\_pcrs\_diffusion

<table><thead><tr><th width="260">Valeur</th><th width="144.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>wms</td><td></td><td>Diffusion via un service WMS</td></tr><tr><td>wmts</td><td></td><td>Diffusion via un service WMTS</td></tr><tr><td>tms</td><td></td><td>Diffusion via un service TMS</td></tr></tbody></table>

### Régime des projets

l\_pcrs\_regime

<table><thead><tr><th width="258">Valeur</th><th width="146.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>production</td><td></td><td>Production initiale</td></tr><tr><td>maj</td><td></td><td>Mise à jour</td></tr></tbody></table>

### Nature de subventions

l\_pcrs\_subvention

<table><thead><tr><th width="257">Valeur</th><th width="151.33333333333331">Alias</th><th>Définition</th></tr></thead><tbody><tr><td>feder</td><td></td><td>Financement FEDER</td></tr><tr><td>cper</td><td></td><td>Contrat Etat-Région</td></tr><tr><td>detr</td><td></td><td>Dotations de l’État aux Territoires Ruraux</td></tr></tbody></table>
