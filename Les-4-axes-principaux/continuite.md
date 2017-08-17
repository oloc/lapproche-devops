# De la continuité

Dans cette représentation du DevOps, j'utilise les termes de _continuous integration_ et de _continuous delivery_ mais sans les définir explicitement. De plus, vous avez sans doute entendu parlé de _continous deployment_. Nous aborderons dans ce chapitre ces trois notions traduites respectivement par intégration continue, livraison continue et déploiement continu.

## Continu
L'adjectif "continu" vient de la traduction de _continuous_ qui n'a pas exactement le même sens qu'en Français. L'idée sous-jacente est que les tâches induites sont automatisées et que le développeur peut continuer de travailler/développer sans se préoccuper du précédent résultat. Le terme vient de cette seconde partie de la définition.

Pour préciser pour les béotiens en matière de développement logiciel, la méthode "à l'ancienne" impose de développer, de lancer le fameux _build_ comprenant la compilation et les tests unitaires (ce qui peut prendre de 20 minutes à plus de 2 heures), et d'attendre le résultat (pause café, internet, baby-foot) puis à nouveau coder. Parfois le développeur doit attendre le résultat des tests effectués par une autre équipe souvent appelée de qualification ou de recette. On peut même pousser cette situation de rupture à certaines entreprises qui pratiquent des périodes dites de gel, où aucune livraison en production n'est permise, et par voie de conséquence qui ralentit la cadence de développement, voire en provoque l'arrêt.

L'effet secondaire d'une telle organisation est que les périodes consacrées au développement sont particulièrement chargées. Le développement est souvent un travail intensif et fractionné. Il est fréquent que les développeurs aient le double sentiment suivant les phases d'être exploité et inutile.

![](images/continuous_dev.jpg)

La nouveauté avec les pratiques DevOps est dans la continuité du travail du développeur tout autant que dans la continuité du flux. Le développeur n'a plus à attendre et peut réaliser son travail sans à-coup. Ce qui supprime les sentiments d'exploitation et d'inutilité.
De plus ce travail régulier permet de réaliser un travail plus rigoureux que lorsqu'il est précipité par un pilotage en silo serré.

>Les gains personnels pour chaque développeur sont :
- La sérénité dans son travail
- La satisfaction du travail bien fait
- Le sentiment d'apporter ses compétences aux projets

>Les gains pour l'entreprise sont :
- Une meilleure productivité des développeurs
- Une meilleure qualité de développement 

## Intégration, livraison, déploiement

Si l'adjectif "continu" précise le concept, c'est le nom commun qui définit la finalité. Autrement c'est intégration, livraison et déploiement qui définissent la finalité du processus. Et par finalité j'entends ce que l'on veut faire du code produit.

* Intégration continue : La finalité est de déployer un produit intégré sur un environnement à disposition de certains (testeurs / valideurs) pour vérifier que cela réponde bien au besoin (vérifier : en gros est-ce que cela a une bonne tête). On peut pousser cette vérification en un contrôle et validation.
* Livraison continue : La finalité est d'être fin prêt à livrer soit mettre en production.
* Déploiement continu : La finalité est de mettre en production tout ce qui passe tous les tests. En clair : aucune intervention humaine entre le moment où le développeur pousse son code et la mise à disposition aux utilisateurs.

![](images/continuous.jpg)

L'effort pour atteindre le déploiement continu à partir de la livraison continue, n'est pas seulement l'automatisation de la mise en production et la suppression du déclenchement, c'est surtout l'ajout d'un asservissement sur la plupart des tâches sensibles, les débrayages de fonctionnalités (_feature toggle_ en anglais), et la conversion des campagnes de tests manuelles en automatisées. Et c'est dans la mise en place de toute cette grille de tests qu'est l'essentiel de l'effort.

>A retenir :
- Intégration continue : La fonctionnalité est déployée sur une recette
- Livraison continue : La fonctionnalité est prête à être livrée en production
- Déploiement continu : La fonctionnalité est déployée en production

