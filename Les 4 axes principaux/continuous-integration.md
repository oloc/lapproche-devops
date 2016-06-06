# Continuous integration
La compétence irremplaçable du développeur, celle qui doit occuper tout son temps est dans le code et rien d'autre. Toutes les autres tâches nécessaires à l'obtention d'un programme doivent être effectuées par des mécanismes automatisés.
Nous verrons dans ce chapitre comment oeuvrent les rouages d'une usine de développement.

## Usine logicielle
Une application est un ensemble de fonctionnalités qui sont développées comme autant de pièce d'un grand puzzle.

## Qualimétrie
Le maîtrise de la qualité de ce qui est développé peut s'effectuer à deux niveaux :

 * En amont au moment de la conception et de la rédaction du code
 * En aval avec des outils de contrôle

### De la belle ouvrage
>Pour obtenir de la qualité, il faut coder de la qualité.

La préoccupation de la qualité lors du développement passe par un ensemble de pratiques à adopter qui est souvent regroupé sous le terme anglais de _Craftmanship_. Si la traduction en est délicate, elle recouvre les notions de **savoir-faire, maîtrise, expertise**. Ces pratiques sont décrites dans un chapitre dédié, néanmoins elles ont le trait commun de privilégier la collaboration d'un exercice -la programmation- qui a souvent été considéré comme solitaire.

Une des idées clef est que le code appartient à tous (_**collective code ownership**_) et non plus à un seul codeur. Il peut être rédigé à deux dans le cadre d'une session **TDD**, **BDD** ou en _**pair programming**_. Les développeurs s'entraident par du _**code review**_ ou en appliquant la _**boy scout rule**_.

Le gain personnel pour chaque développeur est la stimulation intellectuelle (sous l'influence du regard tiers), et parfois l'apprentissage de nouveauté en bonnes et dues formes (plus que la "petite bricole" qui rend service). Et _in fine_ c'est une satisfaction de son travail bien fait.
Pour l'entreprise le gain de ces pratiques de collaboration est l'implication de chacun pour produire du beau code lisible et compréhensible, en d'autres termes, le gain en maintenabilité.

D'autres pratiques tel que le _**style guide**_ permet à chacun d'apprendre à coder, passez-moi l'expression, "comme partout dans le monde", et donc de pouvoir reprendre le code de tous, au sein de l'entreprise ou ailleurs. Cet apprentissage est transposable dans d'autres entreprises. Pour l'entreprise le gain change de point de vue mais reste le même. La montée à bord d'un nouveau développeur est facilitée lorsqu'on suit les canons de la communauté.

>A retenir :
Le développement est un domaine d'expertise.

### Contrôle qualité

 * Duplications de code
 * Respect des règles de programmation
 * Couverture de code par les tests unitaires


## Services
