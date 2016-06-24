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
Toutes ces pratiques collaboratives, sont excercées sous l'influence du regard tiers, ce qui entraine l'implication de chacun pour produire du beau code lisible et compréhensible, parfois de chercher de nouvelles solutions techniques et d'apprendre des nouveautés en bonnes et dues formes (plus que la "petite bricole" personnelle qui rend service).

D'autres pratiques tel que le _**style guide**_ permet à chacun d'apprendre à coder, passez-moi l'expression, "comme partout dans le monde", et donc de pouvoir reprendre le code de tous, au sein de l'entreprise ou ailleurs. Cet apprentissage est transposable dans d'autres entreprises. Avec un code dans les canons de la communauté mondiale (et non suivant les us et coutumes propre à l'entreprise), la montée à bord d'un nouveau développeur est facilitée. A la satisfaction de l'entreprise et surtout de l'équipe.

>Les gains personnels pour chaque développeur sont :
- la stimulation intellectuelle
- la satisfaction du travail bien fait
- l'employabilité

>Les gains pour l'entreprise sont :
- la maintenabilité de ses développements
- la facilitée de la montée à bord

>A retenir :
Le développement est un domaine d'expertise.

### Contrôle qualité
Le contrôle _a posteriori_ est tout autant important. Aussi experts que soient les développeurs, il est toujours possible que dans les méandres de la subtilité d'un code ils insèrent une erreur. De la simple coquille à l'énorme boulette de neige de celles qui grossissent à vitesse vertigineuse.
Il faut donc prendre le soin de passer les développements au crible d'outils relevant certains points comme :

 * Duplications de code
 * Respect des règles de programmation
 * Couverture de code par les tests unitaires

Implacablement la machine relèvera les mal-façons suivant non perçues. Et pourquoi donc est-ce utile ? Reprenons ces trois points cités pour l'exemple.

La duplication de code est en soi peu gênante. Que l'on copie/colle un bout de code, et alors !? Là où le bât blesse c'est lors de la maintenance et/ou de l'évolution. On se doit souvent de reprendre les deux ou trois bouts de code concernés. Et parfois, on en oublie un, ce qui crée des divergences de code et donc de comportement.
Même si cela va plus vite sur le moment de reprendre un code, il constitue une erreur potentiel, et donc représente une perte de temps à retardement.

Le respect des règles de progammation rejoint le _**style guide**_ évoqué précédemment. Il peut paraitre pénible de suivre _stricto sensus_ ces règles, et pourtant... il vaut mieux pour le développeur de le percevoir commme une amélioration vers l'excellence.

La couverture de code est un sujet souvent douloureux. Mon point de vue à son sujet est que l'utilité n'est pas immédiate, parce que certes le développeur sait coder utilement, néanmoins, est-ce que ses collègues ne vont pas provoquer des cas d'usage rompant la cohérence de son code ? Voire lui-même quelques temps après ? La maîtrise des effets de bord est la partie la plus important de ce contrôle. Et, à mon sens le plus souvent négligée.

>Les gains immédiats de la mise en place de ces contrôles ne sont pas évidents, il faut les voir comme un investissement.

>A retenir :
Economiser sur les contrôles qualité est une hypothèque sur l'avenir.


## Services
