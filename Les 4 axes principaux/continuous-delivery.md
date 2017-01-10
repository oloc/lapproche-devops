# Continuous delivery
La réduction du temps de mise sur le marché, le fameux _time-to-market_ est la clef de voûte du mouvement DevOps. L'automatisation, l'industrialisation, l'orchestration, sont autant d'éléments de réponse qui ne prennent leur sens que dans un _pipeline_.

Nous verrons dans ce chapitre comment faire vite et bien.

## Déploiement
Déployer une application doit être un geste facile voire anodin. Et pour cela, il faudra porter ses efforts sur deux points :
- Tout, les actions et les vérifications, doit être automatisé
- Tous les outils de cette automatisation doivent être versionnés avec les _releases_ concernées

D'abord pour éviter les erreurs humaines ou les oublis dans le geste et dans les vérifications. Oui, même les vérifications ! Car elles font partie intégrante du processus de déploiement. Si elles demandent un jugement ou une interprétation humaine, c'est qu'elles ne répondent pas au critère de répétabilité exposé plus loin. Et quelle application stable demande des interprétations !?

Ensuite, il faut considérer l'outil de déploiement comme un élément de l'application à déployer. Une application peut changer de technologie ou de morphologie, dans un tel cas l'outil de déploiement doit évoluer avec l'application elle-même. Il est donc nécessaire de l'archiver dans l'outil de gestion de version.

> Les gains associés à ces pratiques sont dans l'éviction d'erreurs et d'oublis, et par voie de conséquence d'incidents liés au geste de mise en production.

Ces notions s'accompagnent plus avant des pratiques aux maturités successives :
- Répétabilité et fiabilité
- Unicité de l'outil
- Réversibilité

### Répétabilité et fiabilité
Les sportifs l'appliquent depuis longtemps : répéter les gestes apporte le naturel. Les développeurs ont repris la pratique dans ce qui s'appelle des _katas_. Il en est de même pour le déploiement, il faut le répéter encore et encore pour qu'il devienne naturel.

Les environnements de recette servent à tester l'application tout autant que son déploiement ! Certaines entreprises réalisent toute une batterie de tests sur un unique déploiement, autrement dit le déploiement n'est éprouvé qu'une seule fois. C'est un début qu'il faut parfaire en testant le déploiement autant de fois qu'il le faut pour qu'il devienne naturel. Ainsi le jour de la sacro-sainte mise en production, le geste a déjà été entrepris des centaines et des centaines de fois et on est dans un **non-événement**.

> Les gains associés à cette pratique sont dans :
- la fiabilisation du geste de mise en production 
- la désacralisation et donc la suppression du stress lié à une mise en production
- la facilité à déployer en recette par conséquent dans la vélocité des prises en compte des correctifs

### Unicité de l'outil
La pratique d'éprouver son outil de déploiement n'est possible qu'avec un outil unique. Il est indispensable que l'outil qui serve à déployer une application sur un environnement soit celui qui serve pour tous les environnements y compris la production, et même, il faut considérer la production en un environnement comme les autres ! Et j'insiste, non pas une copie, un duplicata, un similaire, mais bien l'unique outil lui-même. Pourquoi ? Pour parer à l'envie d'apporter des modifications seulement pour tel ou tel environnement, ce qui de facto casse le caractère unique de l'outil, et par voie de conséquence saborde la mise à l'épreuve de l'outil de déploiement.

Unicité pour les environnements tout autant que pour les livraisons. En d'autres termes, que l'on livre une livraison, majeure, mineure, ou un correctif, l'outil doit être le même. En réalisant une distinction vous perdriez le bénéfice de la répétition ou vous seriez dans l'obligation d'éprouver et maintenir non pas un unique outil, mais plusieurs outils. Cette distinction entre ces livraisons est à proscrire en terme de déploiement puisque pour simplifier mineures et corrections sont des sous-ensembles de la majeure.

Concrétement, l'outil doit comprendre le "mais ça ne concerne pas cette partie" non pas comme une méthode différente mais comme un "ne fait rien". Par exemple, si la base de données n'est modifiée qu'en majeure, et bien lors d'une mineure, on réalise le déploiement avec un _no operation_ pour la partie base de données.


Dans cette pratique d'unicité d'outil, seules les valorisations de quelques variables seront différentes. Les variables elles-mêmes seront identiques et donc sans référence à l'environnement (exemple à proscrire UAT_Server), seules les valeurs seront adaptées.

> Les gains associés à cette pratique sont directement ceux de la répétabilité, auxquels s'ajoute de facto la facilité de maintenance et d'évolution de l'outil unique.

### Réversibilité
Pour beaucoup d'entreprises le retour arrière est -permettez-moi l'expression- la cinquième roue du déploiement, une fonctionnalité considérée comme une option d'assurance plus que pour son apport fonctionnel.
On imagine trop souvent que le retour arrière est une manoeuvre de production, et trop rarement que ça peut être utilisé sur les environnements dits hors production.

On applique un correctif sur un environnement de recette, les tests ne sont pas concluants : désinstallons-le ! Attention non pas à la main à grands renforts de _rename_ et de _.bkp_, mais bien par la fonctionnalité de retour arrière de l'outil de déploiement.

Par cet usage en environnement de recette, on rejoint les deux pratiques précédentes. Eviction des erreurs humaines et oublis qui pourraient dénaturer les tests à venir sur cette plate-forme, et épreuve du retour arrière.
En s'obligeant à réaliser les retours arrière par l'outil et uniquement par lui, on garantit que cette manipulation délicate et stressante en production soit à l'instar du déploiement un **non-événement**.

> Les gains associés à cette pratique rejoint les deux autres, auxquels s'ajoute :
- la suppression des effets de bords et conséquences de cette manipulation si elle n'est pas maitrisée
- la suppression du stress de l'opération en situation sensible

### Mesures
Comme évoqué dans le chapitre de la métrologie, il est important de mesurer l'évolution de votre outil de déploiement. Voici quelques mesures communément utilisées :
- Temps de livraison pour chaque environnement
- Nombre d'actions manuelles
- Temps de chaque action manuelle
- Temps d'indisponibilité par noeud
- Temps d'indisponibilité du service (ou de l'application)
- Nombre d'incidents lors de la mise en production
- Nombre d'incidents a posteriori liés à la mise en production
- Temps de retour arrière par environnement

## Tests automatiques

## Pipeline