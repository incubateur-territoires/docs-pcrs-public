---
description: Les grands principes qui guident la publication de votre projet PCRS
---

# Publication

Pour que la valeur induite par l'investissement conséquents dans les projets de PCRS puisse se réaliser pleinement, la publication est une étape importante qui doit être pensée d'après les usages que vous souhaitez voir apparaître sur votre territoire.

Cette étape est clé dans [la gouvernance des données](../contexte/gouvernance-des-donnees.md) des projets PCRS.

## Livrables et produits dérivés

Il est décisif de distinguer **les livrables** des éventuels produits dérivés que vous seriez amenés à produire en aval. Nous nous intéressons ici en particulier aux fichiers remis par le prestataire en charge de les produire :

* (Les clichés orientés non compressés pour un PCRS raster).
* Les ensembles de dalles raster non compressées (ou compressées lossless).
* (Les nuages de points obtenus par relevé Lidar)
* Les fichiers GML pour les PCRS vecteur.

Ces livrables constituent les objets les plus réutilisables dans la plus grande diversité d'usage. Ils permettent la production d'un certain nombre de **produits dérivés** en aval qui seront spécialisés pour une certaine mise en œuvre technique :

* Des pyramides de tuiles, destinées à être diffusées sur un serveur TMS, WMTS...
* Des extractions ponctuelles pour des rendus précis
* Des fichiers de géométries (shape, geopackage...) exposants certains objets du livrable GML

Ces produits dérivés peuvent être très efficaces lors de l'usage pour lequel ils sont prévus mais peuvent présenter un certain nombre de limitations. Par exemple de ne pas permettre de gérer correctement les mises à jour et obliger au téléchargement complet du PCRS concerné au lieu de la dalle ou du fichier GML opportun.

On veillera donc à conserver quoi qu'il arrive les livrables, alors que les produits dérivés peuvent être générés au besoin, selon des moyens appropriés.

## Diffuser n'est pas publier

Dans [la clarification du droit](https://pcrs.beta.gouv.fr/blog/clarification-du-caractere-ouvert-du-plan-corps-de-rue-simplifie) apportée par l'Administratrice Générale des Données début 2023, l'accent est mis sur l'obligation de publication, à la différence de la diffusion.

La différence entre les deux est sensible : **la publication** consiste à mettre à disposition de manière brute et massive alors que **la diffusion** prévoit la mise en place d'un service dont les besoins de disponibilité impliquent des coûts.

Il n'est pas possible d'exiger la mise en place d'un tel service de la part de tous les porteurs PCRS en raison des coûts et de la non satisfaction de toutes les obligations de l'accès aux documents administratifs que cela présente. C'est pourquoi ces services sont facultatifs et souvent mutualisés pour permettre des économies d'échelle. Nous ne réfutons pas par ailleurs l'utilité que peuvent avoir de tels services par rapport à une publication plus simple.

L'obligation prescrite par le droit porte sur la publication dans un format réutilisable. Nous recommandons donc **la publication des livrables** indiqués ci-dessus avant toute autre chose, via un moyen de téléchargement de masse : serveur FTP ou NAS.

## Publier ses livrables PCRS

La publication des livrables étant une obligation, elle se doit d'être faite de la manière la plus disponible et économique possible. Seule la mise à disposition des livrables permet de satisfaire complètement aux obligations du producteur du PCRS.

C'est pourquoi nous recommandons des solutions peu coûteuse et fonctionnellement simples comme via serveur FTP ou HTTP.

Nous proposons [un mécanisme de mise en valeur des productions](../suivi-des-projets/publication-des-livrables.md) en exploitant les stockage locaux dans lesquels elles pourraient se trouver dès leur livraison. Il n'est pas nécessaire de les déplacer ailleurs et la startup n'exploite pas de plateforme de stockage. Une notice complète est disponible sur la page correspondante pour s'y connecter et profiter des services proposés.
