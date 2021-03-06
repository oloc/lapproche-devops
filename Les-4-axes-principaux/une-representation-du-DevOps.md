# Une représentation du DevOps

![](../images/DevOps_Schema.jpg)

Après moult réflexions sur la façon de présenter le DevOps, il m'est apparu qu'il fallait le représenter, qu'il fallait un visuel pour aborder le sujet. Sur ce visuel présenté dans ce chapitre apparaissent les 4 axes principaux du DevOps :
- Métrologie
- _Continuous Integration_
- _Continuous Delivery_
- Infrastructure élastique

Chacun de ces 4 axes est composé de 3 briques. Chacune de ces briques figure un ensemble de concepts et/ou de pratiques. Une telle description, j'en ai bien conscience, reste abstraite, soyez assuré ami lecteur que nous aborderons tous ces éléments plus en détail par la suite. Voyons ici une première définition de chacune de ces briques.

## Métrologie
Le premier axe, la métrologie, est en support des 3 autres, comme un socle indispensable, comme un liant. Cet axe particulier est le caractère spécial d'une approche DevOps. A mon sens c'est même le signe particulier du DevOps, dans le sens où l'on ne peut pas parler de DevOps sans métrologie. Au risque d'insister, si vous ne deviez mettre en place qu'une seule pratique pour prétendre "faire du DevOps", ce devrait être la métrologie.

>A retenir :
Pas de DevOps sans métrologie.

### Qualité
Le niveau d'exigence des utilisateurs/clients augmente chaque jour. Il est indispensable de livrer de la qualité, et pour s'en assurer, il faut contrôler, mesurer cette qualité.

### Fiabilité
Manipuler des items de qualité est une première étape, néanmoins, il faut éviter qu'ils soient dénaturés voire corrompus. La mise en place de processus, de cycles, de circuits sont des méthodes qu'il faut savoir maitriser, éprouver, améliorer et donc étalonner.

### Vélocité
Nous l'avons abordé, notre objectif est de réduire le _time-to-market_. Il faut donc être en capacité de vérifier, mesurer cette vitesse.

## _Continuous Integration_
Plusieurs définitions peuvent être trouvées sur internet. Pour ma part, je cite Martin Fowler le pionnier, l'inventeur du _Continuous Integration_ :

* Maintenir un dépôt unique de code source versionné
* Automatiser la construction
* Rendre la construction autotestante
* Tout le monde propage sur l'activité principale chaque jour
* Chaque propagation doit déclencher une construction de l'activité principale sur une machine d'intégration
* Maintenir une construction rapide
* Tester dans un environnement qui est une copie de la production
* Rendre facilement disponibles les exécutables les plus récents
* Tout le monde peut voir ce qu'il se passe
* Automatiser le déploiement

Nous reviendrons sur tous ces points dans le chapitre dédié au _Continuous Integration_.

Source: http://www.martinfowler.com/articles/continuousIntegration.html

### L'usine logicielle
Un programme est un assemblage de pièces développées au sein de l'entreprise, par une communauté, par un éditeur. Il est parfois délicat d'opérer à cet assemblage dans une suite d'étapes variées. Ce qu'on appelle **usine logicielle** (_software factory_) est l'ensemble des pratiques qui prennent en charge l'assemblage aussi compliqué qu'il soit. L'objectif est de décharger le développeur de ces tâches pour le sublimer dans ce qu'il fait de mieux : coder.

### Qualimétrie
Le contrôle de la qualité du code doit être effectué au sein de l'usine logicielle. Cette brique regroupe un ensemble de pratiques de développement à adopter (on utilise le terme anglais de _Craftmanship_) tout autant que les tests et les mesures associés.

### Services
Une application a longtemps été monolithique. Avec l'évolution des besoins, il est apparu nécessaire de la tronçonner en plusieurs modules. De part cette architecture logicielle des dépendances fortes sont apparues. Et avec ces dépendances des latences de livraison que j'ai coutume d'appeler "aller à la vitesse du gnou le plus lent". Afin de s'abstraire de ces dépendances entre autre, il est nécessaire d'envisager une applications comme un ensemble de services. Cette orientation permet un souplesse interne à l'application et une ouverture vers d'autres applications.

## _Continuous Delivery_
La réduction du temps de mise sur le marché, le fameux _time-to-market_ est la clef de voûte du mouvement DevOps. L'automatisation, l'industrialisation, l'orchestration, sont autant d'éléments de réponse qui ne prennent leur sens que dans un pipeline.

### Déploiement
La mise en production est un moment clef dans la vie d'une DSI. Afin d'éviter les oublis, les écarts, les fautes de frappe, il devient vital d'automatiser, de fiabiliser son déploiement. Et ce geste ne devrait plus être stressant, mais naturel.

### Tests automatiques (Stratégie de tests)
Quand il est aisé de déployer, il est aisé d'opérer sur ces plate-formes de tests autant qu'il le faudra pour reprendre les tests encore et toujours. Un nouveau patch ? Déploiez, testez. A cette mécanique s'ajoute la diversité des cas de tests, ce que l'on veut tester, et comment. A l'instar des sauvegardes aux stratégies granulaires, les recettes s'appuient sur une stratégie de tests.

### Pipeline
Elément principal de la réduction du _time-to-market_, il permet de supprimer toutes les attentes, les latences, entre les équipes. 

## Infrastructure élastique
De part son caractère matériel, l'infrastructure a longtemps été considérer comme de l'immobilier, qui par définition ne peut être mobile. Plus simplement, un serveur est une boite qu'on pose dans une salle machine, et il n'en bouge plus. Cette image d'Epinal n'a plus cours. De nos jours l'infrastructure est un ensemble de ressources allouées ou désallouées en fonction des besoins. L'infrastructure est devenue élastique.

### _Infra-as-code_
L'infrastructure étant un ensemble de ressources remplaçables pour des raisons de maintenance ou de recherche de performances, qu'elle en est la valeur réelle ? Sa vraie valeur est dans la topologie qu'elle porte, et donc dans notre capacité à reproduire cette topologie. En informatique, le geste de reproduire et la source de ce geste passe par du code. L'estimation de la valeur de son infrastructure passe par l'appréhension que l'infrastructure est du code.

### Environnements éphémères
Quand une infrastructure est définie dans du code reproductible, il est donc possible de générer un environnement complet à l'envi. De le détruire et le recréer. On est donc en capacité d'utiliser des environnements éphémères. Cette capacité tire des pratiques inédites.

### Infrastructure asservie
L'asservissement de l'infrastructure est le dernier étage des concepts ouvrant à l'élasticité. Il est possible et prometteur d'adosser la création et le suivi de ses environnements éphémères à une mécanique d'asservissement. L'infrastructure devient dynamique et à géométrie variable.
