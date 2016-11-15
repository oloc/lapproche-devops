# _Craftsmanship_
Une même phrase écrite sur du papier avec un stylo (je me permets de préciser) peut être griffonnée, être lisible ou illisible, ou parfaitement calligraphiée. Et pourtant ça reste la même phrase.

Pour le développement, l'analogie est assez pertinente. Même si le programme fera bien ce qui est demandé, qu'il est fonctionnel, le code source peut être de qualités diverses. Certains codes sont agréables lire, compréhensibles à la première lecture, d'autres vont être rédhibitoires à lire, et incompréhensibles.
Ces difficultés de lecture peuvent entrainer une incompréhension, donc des retards dans la maintenance ou les évolutions voire de mauvais apports ou corrections. 

> Un code bien écrit facilite la maintenance et les évolutions. 

Qu'est-ce qu'un bon code ? bien écrit ? La réponse à une telle question est délicate. Et sans doute que chacun aura une réponse différente. Néanmoins, on peut énoncer un ensemble de pratiques qui aident à son obtention.
Voyez le tableau suivant présentant un ensemble de pratiques décrites ci-après. 

![](images/Pratiques_Craftsmanship.png)

## TDD - Test-Driven Development
C'est une technique de développement logicielle préconisant d'écrire le test avant le code logiciel, dans un cycle tel que :
1. Ecrire le test
2. Vérifier qu'il échoue (car la partie de logicielle concernée n'existe pas encore)
3. Ecrire le minimum de code pour répondre à ce test.
4. Vérifier que ce test passe (et tous les autres empilés depuis le début)
5. Réusiner le code, on le simplifie ou l'améliore pour plus de lisibilité tout en gardant les fonctionnalités

Plusieurs avantages à cette technique. Tout d'abord, au travers du test, on définit et on utilise l'application avant de la coder, ce qui réclame d'avoir une vision de ce que devrait être l'application. On ne se place pas dans la logique de coder et on verra ce que ça donne, mais dans la démarche d'apporter le code répondant à ce que devrait être l'application.
Ensuite, étant donné qu'on conçoit le test avant le code, tout est testé, et si d'aventure le développeur a introduit un effet de bord, cela se révélera aussitôt. On évite donc de le découvrir plus tard voire très tard, dans le cours du projet, et surtout cela apporte de la confiance au développeur dans la mesure où il est de suite averti s'il a "cassé quelque chose". Ce qui évite les excès de précautions -pourvu que je ne casse rien- qui entraine des délais dans les développements.
Enfin, tout développeur peut apporter des améliorations sans risque au code d'un autre avec une connaissance seulement partielle de l'application. Les garde-fous (entendre les tests) sont là pour lui rappeler le bon fonctionnement de l'application.

## BDD - Behaviour Driven Development

## Collective Code Ownership
Il est fréquent que dans une équipe de développeurs, chacun soit responsable de "son bout de code", et personne ne peut le modifier sans l'aval du développeur concerné.
Avec cette pratique, tout le monde est responsable du code. Cette notion entraine que chacun peut modifier toute partie du code.

Ce n'est donc plus une personne dédiée qui pourra corriger un bug, c'est tout le monde. C'est un gain en vélocité dans la résolution d'incident.

Un développeur peut apporte des erreurs en s'imaginant corriger et/ou améliorer une partie du code qu'il maîtrise mal. C'est pourquoi la contrainte de cette pratique est qu'il est impératif que des tests unitaires sont exécutés systématiquement pour déceler ces introductions d'erreurs.


## Software Entropy
Le second principe de la thermodynamique énoncé pour la première fois par Sadi Carnot en 1824 introduit la notion d'entropie. Elle représente la mesure du désordre. Appliqué au développement, il faut retenir :

> L'entropie d'un système isolé ne peut qu'augmenter ou rester constante.

Pour simplifier, il est inéluctable qu'un programme utilisé voit ce qu'on appelle **la complexité** augmenter, et donc le potentiel de désordre augmenter. Plus votre code est complexe et plus il est délicat à maintenir et améliorer. Il faut donc prendre garde à contrôler et maitriser ce phénomène.

## KISS - Keep it simple stupid
Ce principe préconise la simplicité. Toute complexité inutile est à proscrire.

Cet énoncé peut paraitre évident, je me permets d'ajouter un peu de contexte. De part mon expérience, j'ai pu rencontrer des personnes cherchant à optimiser la performance de leur programme avant même d'avoir testé une implémentation simple. Ce qui ajoute de la complexité sans avoir de référence. Est-ce qu'une version plus simple sans doute non optimisée ne répondait pas au besoin ? Et est-ce que ce premier code produit avec la préoccupation de la performance est réellement plus performant qu'une version simple ?
Dans ce cas il est préférable de produire un code simple et selon le besoin de l'optimiser. Cet enchaînement limite la complexité et l'optimisation à leur plus stricte nécessité.

Cette pratique est afférente à la _software entropy_.

> Maitriser votre complexité en codant simple puis en optimisant.

## Broken windows
La théorie de la _vitre cassée_ est issue des sciences sociales et de la criminologie.

Imaginons un bâtiment avec quelques vitres cassées. Si ces vitres ne sont pas remplacées, la tentation pour des vandales d'en casser d'autres s'accroit. Eventuellement certains pourraient chercher à entrer dans le bâtiment, pour le dégrader, l'incendier ou le squatter. De telles situations ont une influence sur le voisinage proche voire tout le quartier.

Pour revenir sur une application de cette pratique au développement logiciel, il faut la résumer au fait qu'une petite négligence ou étourderie peut, par l'accumulation, entrainer un développeur à y intégrer du code approximatif. En se plaçant dans la tête de ce développeur, on pourrait y entendre "vu comment le reste est codé, je ne vais pas m'éreinté."

Il faut donc prendre le soin de réparer ses fenêtres. Dès qu'une imperfection est découverte opportunément ou détectée par un outil de qualité de code par exemple, il faut prendre le soin de la corriger. Suivant cette pratique, ce petit effort évitera de grosses refontes de code.

> Les petits efforts réguliers de correction évitent l'effet boule neige provoquant un code grossier. 

## Boy scout rule
Une des règles de Baden-Powell créateur des _boy scouts_ est de toujours laisser le site de campement plus propre qu'en arrivant.

Appliqué au développement, ça consiste à corriger quelques coquilles ou de rendre un peu meilleur (et non tout recoder). Par exemples, rendre le nom d'une variable plus parlant, ou transformer une partie de code en fonctions.
Ces petits aménagements rendre le code plus lisible donc plus maintenable.

> Laisser le code plus propre que vous ne l'avez trouvé.

On pourrait rapprocher cette pratique qui est un apport d'amélioration à la _broken windows_ qui est une correction.

## Newspaper Style
Cette pratique empreinte à la maquette des journaux.

Quand on ouvre un journal de presse écrite, on sait de suite où trouver les articles, l'édito, la météo, la politique intérieure, les articles internationaux, etc.
En pratique de développement, on privilégiera une disposition constante des différentes parties de son code (fonctions, déclaration de variables, valorisation, etc.), afin qu'une habitude s'établisse pour chaque mainteneur et que ça devienne instinctif pour retrouver un élément.

De plus, il est plus confortable pour nos yeux de lire des colonnes de peu de mots, et les journaux s'y sont adaptés.
Quand on programme, on cherchera à éviter les longues lignes de code.

> Une constance dans la disposition, et des lignes courtes favorisent la lecture d'un code.

## Pair Programming

## Style Guide

## Design Patterns

## Lint

## Refactoring

## Coding Dojo

## Clean Code

## Test Harness

## Tech leading

## DRY - Don't repeat yourself

## Unit testing

## Egoless Programming

## YAGNI - You ain't gonna need it

## SOC - Separation of concerns

## Code review

## Data Separation

## Katas

