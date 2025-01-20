---
description: Notre outil de mise en valeur des stockages locaux
---

# Publication des livrables

[La publication](../les-projets-pcrs/publication.md#diffuser-nest-pas-publier) est une obligation centrale des porteurs de projet locaux de PCRS. Les livrables étant pourtant de taille conséquente et les outils peu nombreux pour ce faire, nous avons décidé de mettre en place le nécessaire pour rendre accessible ce qui est habituellement stockés sur des serveurs locaux.

[Un atelier](../ateliers-et-webinaires/publication-et-diffusion-12-octobre-2023.md) a notamment eu lieu pour annoncer cette disponibilité et recueillir les impressions des porteurs de projet.

## Préalables

L'outil que nous proposons permet la mise en relation d'utilisateurs avec les lieux habituels de stockage des livrables PCRS.

Ces fichiers doivent en premier lieu se trouver sur un serveur HTTP(S), FTP(S) ou SFTP mis en place par le porteur de projet avant de pouvoir le déclarer dans [le suivi des projets](edition-des-donnees.md).

### Disposer d'un serveur en ligne

Le service déployé par notre équipe ne prévoit pas une récupération des fichiers pour les placer en ligne. Il assure la présentation de contenus présents sur des serveurs existants. Votre territoire doit donc se munir d'un tel serveur d'après les protocoles supportés avant de le déclarer comme indiqué dans les étapes suivantes.

* Serveur HTTP(S) : accès à la liste des fichiers via les index produits par le serveur (les index devant porter la mention `Index of`).
* Serveur FTTP(S) : accès via le protocole FTP, éventuellement sécurisé
* Serveur SFTP : accès via le protocole SFTP et un couple login/mot de passe. L'authentification par clé publique n'est pas supportée.

La notice disponible au bas de cette page indique sur quelles architectures nous avons éprouvé nos solutions

### Choisir un compte utilisateur limité

L'accès au serveur existant peut se faire au moyen d'identifiants qui sont publics ou privés. Il sera par ailleurs possible de permettre le téléchargement des fichiers sans révéler les identifiants.

En tout état de cause, il convient de n'utiliser que des comptes destinés à l'accès public et donc muni d'autorisations limitées adaptées à ce cadre. Il serait par exemple inutile de fournir l'accès en écriture aux répertoires cibles et en revanche très utile de limiter l'accès à ces comptes à la sous-arborescence uniquement.

## Déclarer un stockage

La déclaration d'un stockage se fait dans la définition d'un livrable, à disposition du porteur de projet uniquement.

Il est recommandé de se reporter à [la documentation dédiée](edition-des-donnees.md) au formulaire de suivi à destination des porteurs de projets habilités.

## Accéder aux métadonnées des livrables

L'accès aux métadonnées et à l'éventuel téléchargement des fichiers présents sur le serveur déclaré se réalise sur la page projet accessible au public.

Il s'agit de la vue la plus complète possible à propos d'un projet donné. Elle est accessible depuis la carte de suivi, en utilisant les boutons appropriés dans le panneau de gauche après avoir sélectionné le projet concerné. Les dalles prises en compte sont celles qui ont été correctement analysées par notre solution d'indexation. Les dalles vides ou corrompues ne seront pas visibles dans le résultat, ce qui pourra occasionner des trous jusqu'à ce que le problème soit résolu.

Les détails de cette vue sont expliqués dans la documentation ci-dessous.

Dans le cas où vous chercheriez [des données brutes](donnees-brutes.md#entites-du-geostandard), notre API permet également d'accéder à cette connaissance en masse.

Nous restituons notamment les géométries des emprises de chaque livrable. Elles correspondent à l'agrégation des surfaces des dalles qui les constituent. Voir l'exemple ci-dessous :

<figure><img src="../.gitbook/assets/Capture d’écran du 2024-06-24 17-39-55.png" alt=""><figcaption></figcaption></figure>

{% file src="../.gitbook/assets/notice_stockage (3).pdf" %}

