---
description: >-
  Foire aux questions pour trouver les réponses aux interrogations les plus
  fréquentes
---

# Questions les plus fréquentes

## Généralités

#### Quelles sont les différences entre PCRS et RTGE ?

Le Plan de Corps de Rue Simplifié (PCRS) est l'une des briques d'un Référentiel Topographique à Grande Échelle (RTGE).

Un RTGE présente un supplément d'objets, parfois métiers, en plus du fond de plan constitué par le PCRS. Ces objets peuvent d'ailleurs être fournis par plusieurs exploitants différents qui collaborent pour former le référentiel.

Si le PCRS raster ne peut pas être seul qualifié de RTGE, le PCRS vecteur s'en approche davantage au sens où il peut déjà contenir un certain nombre d'affleurants vectorisés en plus du corps de rue en tant que tel.

## Production du PCRS

#### Quelles sont les obligations encadrant la production du PCRS ?

Il existe une obligation d'usage du PCRS, reposant sur les gestionnaires de réseaux qui devront l'intégrer à leurs réponses aux DT à partir du 1er janvier 2026 là où il est disponible. Reportez-vous à [la description de la réglementation](../contexte/reglementation/) pour cela.

Plusieurs interrogations subsistent autour de ces obligations, notamment sur la notion de disponibilité.

Votre collectivité, suivant sa taille ou ses moyens peut elle-même lancer un tel projet ou se rapprocher d'une entité départementale ou régionale afin d'y contribuer à une maille géographique plus importante. De nombreux usages autres que l'anti-endommagement peuvent lui permettre d'atteindre un retour sur investissement rapidement.

#### Le PCRS contient-il le plan des réseaux enterrés ou aériens ?

**Non**, ce sont deux choses différentes.

Le Corps de Rue se concentre sur les éléments d'alignements : bâtiments, voiries et le mobilier attenant. Le recensement [des affleurants de réseaux](construction.md#prendre-en-compte-les-affleurants) ou de la végétation, certains éléments ponctuels de relief peut être également effectué.

Le recensement des réseaux, particulièrement conforme à [la réglementation anti-endommagement](../contexte/reglementation/#reglementation-anti-endommagement), revient à chacun de leur gestionnaire et non à l'autorité publique locale compétente en charge de la production et maintenance d'un PCRS.

#### **Quels affleurants de réseaux doivent être inclus au PCRS ?**

Le géostandard PCRS prescrit [une liste de natures d'affleurants](construction.md#prendre-en-compte-les-affleurants) obligatoires à faire figurer dans un PCRS. Il est important de s'y reporter pour construire le cahier des charges de son projet ou demander des données existantes aux gestionnaires de réseaux.

#### Où puis-je savoir si un PCRS existe sur tout ou partie de mon territoire ?

Le suivi des projets PCRS est un sujet important pour permettre aux multiples réutilisateurs d'accéder aux ressources qu'ils devront obligatoirement utiliser.

Nous publions [notre carte de suivi](https://pcrs.beta.gouv.fr/suivi-pcrs) alimentée par les porteurs de projets eux-même qui disposent des outils pour le faire en autonomie. [Des données brutes](https://www.data.gouv.fr/fr/organizations/pcrs-beta-gouv-fr/#/datasets) sont également disponibles sur data.gouv. Nous tenons à jour [une documentation complète](../suivi-des-projets/demarche.md) sur ce dispositif.

#### Où puis-je connaître les APLC de mon territoire ?

Les suivis actuels décris ci-dessus traduisent implicitement l'existence d'une APLC associée mais peuvent en ignorer quelques propriétés.

Il n'existe pas à ce jour de registre des APLC à proprement parler, ce titre n'étant pas suffisamment encadré réglementairement.

Vous pouvez utiliser [notre carte de suivi](https://pcrs.beta.gouv.fr/suivi-pcrs) ou télécharger prochainement les données brutes associées afin de prendre connaissance des informations relatives aux projets publiées par les territoires eux-mêmes dans notre workflow de suivi.

#### Combien cela coûte-t-il à produire ?

Il n'est pas possible de répondre, cela variant en fonction de choix établis pour chaque projet.

En revanche nous investiguons pour déterminer des ordres de grandeur et l'ampleur des coûts fixes.

#### Puis-je utiliser les données LidarHD de l'IGN pour construire un PCRS vecteur ?

Les données du programme LidarHD de l'IGN ont une erreur quadratique moyenne de 50 centimètres en X et Y ([source](https://geoservices.ign.fr/sites/default/files/2022-05/DT_LiDAR_HD_1-0.pdf)). La densité de points d'au moins 10 par mètre-carré n'est pas suffisante pour disposer d'un nuage de point similaire à ce qui est relevé au sol en mobile mapping.

D'après [les prescriptions](../contexte/geostandards/) du CNIG, le PCRS vecteur devant être d'une précision de 10 cm, l'utilisation de ces nuages de point **n'est pas possible** dans ce cadre.

#### Puis-je utiliser les données LidarHD de l'IGN pour construire un PCRS raster ?

Les données du programme LidarHD de l'IGN ont une erreur quadratique moyenne de 50 centimètres en X et Y et 10 centimètres en altimétrie ([source](https://geoservices.ign.fr/sites/default/files/2022-05/DT_LiDAR_HD_1-0.pdf)).

Des données LidarHD seules ne permettent pas d'obtenir une image en couleurs visibles comme celle servant à élaborer un PCRS raster. Une prise de vue aérienne sera nécessaire pour cela.

Toutefois, ces données permettent après mise à disposition sur votre territoire et utilisation des points classifiés comme étant au sol, **d’améliorer le processus d’orthorectification** par rapport à une utilisation de tout autre modèle numérique de terrain moins précis.

#### Puis-je utiliser les données de fonds de plan existants, comme le Carto 200 pour initialiser un PCRS ?

Les fonds de plan conformes au format PCRS succèdent à d'autres produits existants et il est légitime de réfléchir à les réutiliser. On pense par exemple au[ fond de plan Carto 200](https://www.atlog-logiciels.fr/Docs_Logiciels/Atlas/la_norme_v3.htm) conçu par Enedis et GRDF, maintenu par Atlog.

Historiquement, ces fonds de plan ont été conçus puis maintenus selon une culture DAO, avec des logiciels appropriés pour cela. Le PCRS étant lui conforme à une culture SIG, il faudra financer des opérations de translation vers les formats vectoriels géographiques selon des coûts qui peuvent couvrir les bénéfices de réutiliser ces ressources existantes.

D'autre part, les différents cahier des charges ne couvrent pas les mêmes natures d'objets, il faudra l'évaluer au cas par cas et produire les éléments manquants dans ce cas échéant ou compenser un manque de précision dans les positionnements.

En tout état de cause, la réponse à cette question est à priori **non**.

## Publication du PCRS

#### Mon PCRS est-il un document public ?

**Oui**, le PCRS est un document communicable et sa publication ne peut pas être différée.\
Puisqu'ils sont produits ou que leur production est portée par une administration publique, les livrables du PCRS sont des documents communicables.

Retrouvez [plus de précisions](https://pcrs.beta.gouv.fr/blog/clarification-du-caractere-ouvert-du-plan-corps-de-rue-simplifie) à propos de la réponse de l'Administratrice Générale des Données à ce sujet.

#### Mon PCRS est financé partiellement ou totalement par des acteurs privés, dois-je aussi le publier ?

**Oui**, la maîtrise d'ouvrage étant portée par une collectivité locale, les livrables achevés seront détenus par une administration publique et devront donc être publiés. Les livrables sont achevés lorsqu'ils ont été remis par le prestataire et que le contrôle qualité les a définis comme aptes à l'usage pour lequel ils sont prévus.

Voir également la section ci-dessous à propos du financement.

#### Mon PCRS est consultable en ligne, sur ma propre plateforme ou via un tiers, sans possibilité de télécharger, ai-je répondu à mes obligations ?

**Non**, en tant que document administratif communicable, le PCRS doit être publié en ligne et les livrables produits librement téléchargeables selon le principe de l'égalité de l'accès.

Par ailleurs, [diffuser n'est pas publier](questions-les-plus-frequentes.md#publication-du-pcrs). La diffusion représente des coûts plus importants que la publication en raison de la disponibilité nécessaire et la priorité doit être mise sur la publication pour une émergence large des usages.

#### Le guichet unique Construire-sans-détruire va-t-il diffuser le PCRS ?

**Non**, le rôle du guichet unique, construire-sans-détruire, est de mettre en relation les gestionnaires de réseau et les MOA/MOE de travaux à venir. Il n'a pas pour rôle de diffuser le PCRS.

D'autres services, locaux comme nationaux seront amenés à réaliser cette diffusion à différentes conditions, payante comme gratuite selon les usages.

Nous rappelons par ailleurs que la diffusion du PCRS est facultative, à [la différence](publication.md#diffuser-nest-pas-publier) de la publication abordée ci-dessus.

## Financement du PCRS

#### Mon tour de table ne comprenait que certains gestionnaires de réseaux et des acteurs supplémentaires souhaitent disposer des données, puis-je établir une convention de licence pour compléter mon financement ?

**Non**, les conventions d'octroi de licence contreviennent au principe de gratuité des documents administratifs. Dans l'immédiat, il serait alors nécessaire de proposer un avenant aux conventions déjà établies avec le tour de table d'origine et rééquilibrer les financements de chacun, ce qui n'est pas chose facile.

A moyen terme, la pertinence d'une plateforme nationale pour inclure dès le départ tous les utilisateurs réglementaires est renforcée par l'apparition de ces cas de figure.

## Vie du PCRS

#### Dois-je mettre à jour mon PCRS à chaque changement sur le terrain ?

La mise à jour du PCRS doit être régulière, le plus souvent possible, mais il n'existe aucune obligation de mise à jour à chaque changement sur le terrain.

Plusieurs méthodes sont en cours d’investigation dans la [documentation dédiée](mise-a-jour.md).

#### Le producteur du PCRS est-il responsable de dommages en cas d'obsolescence ?

L'obsolescence du fond de plan est caractérisée dès lors que le réalité du terrain n'est pas fidèlement traduite, notamment après des changements affectant sa topographie.

L'obligation faite aux utilisateurs du fond de plan est d'utiliser le meilleur fond de plan disponible sans prévoir d'obligation au producteur de le mettre à jour. En outre il incombe à l'utilisateur de mener toute investigation supplémentaire qu'il jugerait utile au regard de la précision des informations qui lui sont communiquées en réponse à une DT comme prescrit par le II. de l['article R554-23](https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000037522525) du code de l'environnement.

Il est ainsi très peu probable que le producteur du PCRS soit responsable de dommages consécutifs à une mauvaise interprétation du plan en raison de son obsolescence.

Le problème de l'obsolescence réside pour le producteur dans une dégradation sensible de son investissement initial. L'investissement raisonable et continu dans la mise à jour est un moyen de préserver la valeur globale du fond de plan ainsi produit.

#### Vais-je recevoir des DT ou DICT une fois mon PCRS réalisé ?

**Non**, les DT ou DICT sont des jalons du processus d'anti-endommagement lors de travaux aux abords des réseaux souterrains. Les documents associés à ces jalons s'échangent entre les gestionnaires de réseaux pour préparer au mieux leurs projets respectifs. Ils ne concernent pas l'autorité publique locale compétente qui aura fourni par ailleurs son PCRS à ces gestionnaires pour servir de fond de plan.
