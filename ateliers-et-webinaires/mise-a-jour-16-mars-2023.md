# Mise à jour - 16 mars 2023

## Séance à distance, de 10h à 12h

Plus de 60 participants.

[**Le replay**](https://nextcloud.datactivist.coop/s/XTELtCyfR8MWzPx) est disponible en ligne : \
**Le support** est disponible au bas du présent compte-rendu.

**Les discussions continuent** [**sur le forum**](https://forum.pcrs.beta.gouv.fr/)

## Avancées de la startup d’État

#### **Rappel des obligations liées à l’ouverture et la réutilisation des données**

[La nature communicable](https://pcrs.beta.gouv.fr/blog/clarification-du-caractere-ouvert-du-plan-corps-de-rue-simplifie) du PCRS a été clarifiée par l'AGD début février.

* Les obligations touchent la publication des données afin d’en permettre l’exploitation et la possibilité de récupérer des livrables brutes.
* Les obligations concernent tous les livrables achevés (les données brutes)

#### **La Start-up va travailler sur l’établissement d’un socle technique pour récupérer les livrables.**

* Le socle technique viendra faciliter la mise à disposition des livrables.
* Rappel : la Start-up n’a pas vocation à héberger des données

#### **Cadre de financement national**

Nous travaillons sur l’établissement d’un cadre national de financement pour sécuriser le cours des projets en cours et à venir.\
**Objectif :** Accueillir le plus grand nombre de gestionnaires de réseaux pour abonder un fonds national :

* Maîtrise d’ouvrage qui doit rester au niveau local
* Faciliter le montage des dossiers
* La structure viendra s’adosser au projet pour définir la part des contributions privées.

**Une concertation** sera menée dans les prochaines semaines.\
**Le calendrier prévisionnel** est le suivant :

* Fin du semestre : élaboration du scénario final
* Fin de l’année : mise en œuvre

**Pistes de travail** sur les modalités juridiques : avenant (_un participant indique dans le fil de discussion que l’avenant ne sera pas possible)._

**Des discussions pourraient être envisagées avec les fédérations** qui représentent les acteurs locaux (AMF, FNCCR…)

**Financements différenciés** selon la nature des projets (mixte, raster…)

* 4 gestionnaires de réseaux sollicités à ce jour (GRDF, Enedis, Orange, Suez), l’objectif étant d’en solliciter une vingtaine.
* Les financements couvriront la production et la mise à jour (et le fonctionnement pourrait être une piste).
* Une étude d’impact sera réalisée sur les conventions.

**Remontée des données**

Proposition par la startup d’un outil qui permet de faire des remontées de suivi

* Formulaire en cours de création
* Chaque territoire aura un accès spécifique pour ses projets via un lien

**Modèle de données**\
[La version 0.3](../suivi-des-projets/modele-de-donnees/) du modèle de données a été publiée le 14 mars.

Vérifier l’interopérabilité avec le schéma PCRS, notamment en ce qui concerne les champ suivants : _Initiative PCRS, Emprise échange PCRS, emprise disponibilité PCRS_

**Archivage des emprises**\
Question relative sur le rôle de l’INERIS (Grand Nancy) dans l’archivage des emprises.\
\=> La startup pourrait solliciter l’INERIS sur ce point.

**FCTVA**

Le fonds de compensation pour la taxe sur la valeur ajoutée peut-il financer les mises à jour ?\
\
**Autorisations de vol**

Difficulté pour obtenir des autorisations de vol (notamment auprès des préfectures).

## Ateliers en séance

### Atelier 1

#### Mise à jour différentielle ou complète ?

Pour a mise à jour différentielle :

* Réduire les coûts par rapport à une mise à jour complète
* Pour tenir compte des rythmes d'évolutions qui sont différents en rural et urbain
* Mise à jour différentielle plus adaptée pour le PCRS Vecteur : Plans de Recollement
* Temps de travail plus réduit pour le contrôle
* Permet de lisser dans le temps : coûts, contrôles, mise à disposition..
* Mise à jour en continue attendue par les partenaires (privés notamment)
* Pour donner une autre utilité à cette donnée suite a des besoins connexes comme la GEMAPI, la gestion du matériel urbain, la signalisation horizontales, les espaces verts....

Pour la mise à jour complète :

* Homogénéisation de la données (supprime l'effet patchwork)
* Garder une homogénéité visuelle sur l'ensemble du territoire
* Pertinent pour PCRS image car exhaustif sur le territoire
* Nos territoires évoluent beaucoup ==> Difficile d'identifier tous les secteurs à mettre à jour

#### Quels sont les déclencheurs ?

Déclencheurs de mise à jour différentielle :

* Les informations transmises par les aménageurs qui devraient être signataires des conventions
* Utilisation actuelle des plans topographiques et de récolement localisés puis contrôle graphique pour transformation (outil spécifique 1Spatial).
* L'envergure et les types de travaux. Un changement conséquent du territoire (projet ou extension de ZA, réseaux ..). Retour des communes
* Via un outil de consultation en ligne qui offre la possibilité de créer une punaise sur les voies ou les zones à mettre à jour

Déclencheurs de mise à jour complète :

* 3 à 4 ans pour avoir une actualisation complète et uniforme du territoire
* Les besoins de la mise à jour PCRS raster se font tout les 2 ans. En partenariat avec la région.
* Le délai d'une mise à jour totale peut-être prolongé si des mises à jour différentielles ont été mises en place (passer à 5/6 ans)

#### Quels sont les modes de financement ?

Financement d'une mise à jour différentielle :

* Un financement par les aménageurs dans le cadre de leur travaux qui produisent un récolement conforme au PCRS , complété par un financement des partenaires du projet PCRS pour intégrer les MAJ dans la base de données PCRS
* Les besoins de la mise à jour PCRS vecteur est financé seul.
* Application clé de répartition unique pour acquisition initiale, fonctionnement et màj + participation minimale pour gestionnaire avec peu de km de réseau
* Les aménageurs pourraient avoir une quote part fixes sans lien avec les emprises réellement impactées complexes à calculer

Financement d'une mise à jour complète :

* Principe de financement identique à la phase d'initialisation. Les coûts seront inférieurs (certaines données de base MNT/MNS ne seront pas à produire au moins pour la première mise à jour
* Si on repart sur de l'orthophotographie, coût proche de la première acquisition si on attend trop. Mais pour la MAJ, si pas de Feder chaque collectivité sera plus impactée
* Tour de table

### Atelier 2

Quelles solutions avez-vous retenu pour identifier les travaux impactants ?

* Basé sur nos propres observations lors des levés MMS (réalisés en régie), mais aussi sur la base des demandes de plans des collègues en charge de travaux sur les réseaux BT ou EP, et enfin, nous prévoyons la mise en place d'un outil collaboratif en ligne pour pointer les secteurs nécessitant une màj.
* Remontées partenaires (collectivités, exploitants de réseaux) + détection automatique de changement (routes de la BD Topo + bâtiments du PCI) entre plusieurs millésimes
* Expérimentation via les infos du Guichet unique + SOGELINK pour essayer de voir si permet de disposer d'alertes sur besoins de mises à jour (GéoVendée, Morbihan Energies et Territoire d'énergie Mayenne) Problème d'accès aux données. Lien entre GU et PCRS ?
* Analyse images satellites (prospective)
* Tenue d'un Copil annuel pour identification des zones qui ont été sujet à modification
* Conventionnement avec les communes, le département, la région qui ont la compétence voirie pour faire remonter les zones de travaux -> mutualisation des recollements
* DICT
* Parmi les informations que nous pouvons récupérer (emprise des travaux du site INERIS, ou remonté des données des acteurs déclarant les travaux), la difficulté est de distinguer les travaux : 1 quand le PCRS n'est pas modifié (travaux réseaux avec réfection de la chaussée à l'identique) et 2. quand le PCRS est modifié (travaux d'aménagement) et dans ce cas, qui est le responsable qui va récupérer le plan de récolement
* Coordination des collectivités à l’échelle départementale au travers d'un portail web
* Analyse imagerie satellitaire (réflexion) + remontée secteur d'extension de réseaux par les partenaires + analyse des DT/DICT.

## Prochaines étapes

* Poursuite des discussions avec deux instances du CNIG, 22 mars et 4 avril prochains
* Atelier suivant à planifier fin avril sur le contrôle qualité des livrables rasters et vecteur.

{% file src="../.gitbook/assets/atelier_2023-03-16.pdf" %}
