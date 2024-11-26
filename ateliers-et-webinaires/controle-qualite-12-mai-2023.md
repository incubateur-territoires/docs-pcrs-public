# Contrôle qualité - 12 mai 2023

## Séance à distance, de 10h à 12h

Plus de **100** participants

Le replay est disponible en ligne : [https://bbb-dinum-scalelite.visio.education.fr/presentation/37efb2e0bd71bae71412b30d926721fe687d6133-1683877561616/meeting.mp4](https://bbb-dinum-scalelite.visio.education.fr/presentation/37efb2e0bd71bae71412b30d926721fe687d6133-1683877561616/meeting.mp4)

Le support de présentation de la matinée est [disponible ici.](https://nextcloud.datactivist.coop/s/XsGoXPxPY7dBs7y)

## Avancées de la startup d’État

La base de données se complète jour après jour grâce au travail de Rosaine Buannic qui contacte tous les porteurs de projet les uns après les autres.

Les données de suivi sont visibles sur[ la carte de suivi](https://pcrs.beta.gouv.fr/suivi-pcrs) dont nous annoncions la disponibilité sur [notre blog](https://pcrs.beta.gouv.fr/blog/suivre-les-projets-de-pcrs-une-necessite).

Comme annoncé dès le début de notre initiative, les données brutes issues du travail de la startup d'Etat PCRS ont été [publiées en open data sur data.gouv.fr](https://www.data.gouv.fr/fr/organizations/pcrs-beta-gouv-fr/#/datasets).

Un formulaire pour faire remonter les données de suivi est en cours de mise en service. Tous les porteurs de projet pourront alimenter en autonomie la base de données de suivi. Un lien de connexion sera envoyé très prochainement.

## Présentation du contrôle qualité des rasters par le CRAIG

Le support de présentation [est visible ici](https://nextcloud.datactivist.coop/s/GMQF4DFiYRT6Rp8)

## Présentation du validateur des données vecteur par l'IGN

[Le lien pour accéder au validateur est ici](https://demo-validator.ign.fr)

## Ateliers collaboratifs

### Le contrôle qualité des raster

**Seulement certains contrôles sont réalisés**

* Certains contrôles ont été réalisés par le prestataire (flous sur la base aérienne, programmation des prises de vues en fonction des conditions météo etc)
* Contrôle manuel aucun script pas de contrôle de flou car ni outils ni temps, pas de contrôle métadonnées image ni de la compression
* Certains contrôles sont réalisés en interne, d'autres par les entreprises retenues
* Pas de contrôle sur le taux de compression, uniquement un contrôle visuel sur le dévers Le flou a été volontairement laissé sur la base aérienne
* pas de contrôle de dévers ni compression

#### Réalisation de contrôles qui ne sont pas dans la fiche de recommandation du CNIG

* Analyse des angles d'inclinaison fort pour détection de flous
* Contrôle des dévers à partir du plan de vol réel
* Analyse des dates de vol (étalement)
* Respect du floutage des ZICAD
* La densité des semis de points LiDAR qui servent au MNT d'orthorectification
* Le rapprochement du graphe de mosaïquage avec le graphe théorique de Voronoï afin de s'assurer de l'utilisation des bonnes images
* Analyse statistique et visuelle de la radiométrie
* Contrôle de l'orthophoto par rapport à nos données topographiques vectoriels RTGE, PCRS
* Flash lumineux et aberration rouge/vert/bleu

#### Coût, ETP et financement

Selon les contrôles demandés les prestations de contrôle qualité varient aujourd'hui entre 10K€ et 19K€.

Le nombre d'ETP, lorsque les contrôles sont réalisés en interne, varie entre 1 et 2 ETP (avec d'autres missions en parallèle).

Dans la plupart des cas le financement du contrôle qualité est intégré au projet d'acquisition des points.

### Le contrôle qualité des vecteur

#### Comment sont réalisés les contrôles sur les PCRS vecteur?

* Avec une solution propriétaire, logiciel geoPCRS (Ciril Group), basé sur la version pdf du géostandard qui est différent sur certains points du xsd annexé à ce même géostandard.
*   Contrôle des livrables PCRS Vecteur au format DWG, GML et GDB via un contrôleur/validateur FME

    Les fichiers doivent être conforme à la norme V2 est donc comporter tout les champs
*   Réception des données MMS (laser, image, trajectographie et calage), ortho-voirie et PCRS au format SHAPEFILE puis conversion DWG et GML en interne

    Contrôle automatique (FME) des formats/noms de fichiers, des formats/noms des champs, des codes/alias des champs, de la cohérence entre les objets saisis

    Contrôle sur le terrain de la classe de précision avec un levé topographique par sondage des points de calage du MMS et des objets vecteur du PCRS

    Contrôle visuel au bureau avec comparaison à d'autres données pour la couverture de la zone commandée (MMS, ortho-voirie et PCRS), la cohérence MMS/orthovoirie/PCRS et de l'exhaustivité/classification des objets PCRS
* Contrôle réalisé en interne et par échantillonnage en contrôle externe prestataire
* Réalisation du PCRS à partir de notre RTGE Référentiel Topographique Grande Échelle via un script FME
*   Données reçues en SHP, DWG et GML.

    Marché de contrôle (précision du nuage de points, structure des fichiers, précision topologique, exhaustivité sur échantillonnage, précision attributaire et sémantique).

    Utilisation d'un plugin de contrôle et export GML (cofinancé par des collectivités bretonnes et Pays de Loire) : utilisé pour contrôler les données avant de les intégrer à la base Postgres PCRS
* Livraison des données topographiques au format DWG. Développement d'une application AutoCAD en interne qui correspond à un contrôleur de charte PCRS. Une fois le DWG validé une transformation est réalisée via FME en base de données interne. Finalement, création du GML via l'extension du PCRS de FME donc vérification à plusieurs niveaux.
*   Contrôle géométrique et sémantique d'un échantillon lors de l'acquisition initiale.&#x20;

    Contrôle géométrique et sémantique de l'intégralité des levers livrés.

    Contrôle exhaustivité comprise&#x20;

    Contrôle terrain réalisé et outils simples  FME et Excel pour mise en évidence du contrôle de la géométrie et outils d'aides au contrôle de la sémantique sur notre outil Topstation développés en interne (les attributs)

    Précision : pas de demande de GML aux prestataires (les cabinets de géomètres n'ont pas investis dans la compétence GML et GML PCRS sauf les très gros cabinets), les GML PCRS sont générés en interne.

**Une validation en croisant avec des données de référence**

* Contrôle des éventuels décalages avec une orthophoto 5cm produite par la Métropole
* Utilisation des référentiels locaux.
* Avec l'ortho PCRS Image selon le levé
* Contrôle à partir d'orthophotographie, d'ortho-voirie, vue immersive, de données vecteur issues d'autres bases de données de la collectivité avec un comparateur automatique (FME) permettant d'avoir des alertes sur les zones avec écarts entre données vecteur
* Exhaustivité et types d'objets : Comparaison avec OrthophotoPCRS, avec l'ortho-voirie issue du LIDAR, avec les images Streetview récentes.
*   Pour le contrôle de la précision de position, croisement des données en faisant un pré-contrôle avec l'ortho hiver 5cm + contrôle GPS terrain centimétrique en utilisant ensuite la jointure par le plus proche dans QGIS afin de pouvoir comparer les données PCRS et les données GPS.

    Pour le contrôle de l'exhaustivité des emprises, utilisation du linéaire de référence fournit au prestataire identifiant les zones à produire en PCRS pour identifier les omissions et les éxcédents.

    Pour le contrôle de l'exhaustivité des objets, croisement des données par échantillonnage avec  :  des plans topographiques existants (Métropole ou GRDF) + ortho 5cm + streetview +  données brutes images360 + croisement avec d'éventuelles données des gestionnaires de réseaux (exemple : poteaux éclairage public)

    Pour la contrôle de la précision thématique, utilisation soit des données topographiques si elles existent + vérification streetview si nécessaire + données brutes images360.

    Pour le contrôle de la cohérence  topologique, croisement des données avec des données topographiques afin de vérifier la continuité. Pour la cohérence conceptuelle, utilisation des images 360, ortho 5cm, XSD, etc et toute donnée utile.

    Pour le contrôle de la qualité temporelle et donc identifier les secteurs potentiellement obsolètes, croisement des données de la date levée avec la date de fin de travaux de notre base référençant l'intégralité des travaux réalisés sur le territoire depuis 2011. Pour faire cette comparaison de dates,utilisation notamment des expressions QGIS.

#### D'autres vérifications

* Contrôle de précision via un prestataire externe qui prend des points GPS sur le terrain et vérifie la classe de précision
* Avant le contrôle interne (via outil FME), vérification de l'exhaustivité pour l'utilisation ultérieure, en interne et pour la mise à jour du PCRS
* Vérifications basées sur la norme ISO 19157 qui est la norme de référence pour la qualité d'une donnée géographique.
* Lors de la stéréopréparation, prise de points doubles sur les points de calage du prestataire de façon homogène sur chaque bloc (\~4 zones par bloc)  avec une comparaison immédiate sur le terrain afin de garantir la précision des points GPS avec les soucis ionosphériques actuels

#### Coût, ETP et financement

* Une prestation pour le contrôle qualité vecteur peut monter jusqu'à 40K€
* &#x20;Le coût est souvent intégré à la plateforme de diffusion du PCRS vecteur.
* Pour une métropole : ETP Chef de projet 90% + stagiaire la moitié de l'année + 0,5 ETP pour l'intégration des données + 3-4 journées par an réalisées par 2-3 géomètres pour le contrôle GPS terrain
* Le financement est exclusivement à la charge des collectivités (selon les témoignages apportés lors de l'atelier)

