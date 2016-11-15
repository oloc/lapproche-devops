# Le constat

## Le paradigme actuel ne suffit plus.
Pour répondre à toutes ces nouvelles questions, le paradigme actuel ne suffit plus. Certes, mais pourquoi ? Qu'est-ce qui provoque cette perte de vitesse ?

## Divergence d'approche
Si on simplifie une DSI à deux équipes, on constate :
- Les équipes d'exploitation sont garantes de la stabilité et de l'intégrité du système
- Les équipes de développement apportent des aménagements et des nouveautés.

La recherche de stabilité des exploitants, pour le bien de l'entreprise,  peut se traduire par une tendance à refuser toute modification de ce qui est en place. Alors que pour répondre à un besoin du client (ce qui est toujours bon pour le commerce), l'apport de nouvelles fonctionnalités, applications et/ou technologies reste un leitmotiv des développeurs.
Cette description certes caricaturale permet de mettre en relief la divergence d'approche entre les deux équipes apportant leur contribution à l'activité.

>A retenir :
Alors que les équipes de développement et d'exploitation oeuvrent toutes les deux pour le bénéfice de l'activité, leurs approches sont antagonistes.

## Clivage entre les Devs et les Ops
Il n'est pas rare qu'à la machine à café des exploitants (les Ops) l'on se raconte la dernière des Devs qui mettent la production en péril avec des programmes calamiteux et des processus de livraisons mal ficelés.
De même les Devs vont parler de « ces gros bourrins de la prod' » qui n'ont pas compris et/ou appliqué les consignes comme il se doit.

Le fameux « ça fonctionnait sur mon laptop », lui révèle une méconnaissance des configurations et/ou contraintes de sécurité des serveurs de production.
Son corollaire, pour régler un problème urgent, entraîne une distorsion « temporaire » de la production, en faisant fi des standards.

Outre ces anecdotes, d'autres symptômes sont révélateurs :
Combien de temps vous faut-il pour détecter un _bug_, l'analyser, et livrer le correctif ?  Et combien de correctifs faudrait-il pour ce même incident ?
Ces résultats sont directement liés à la coopération entre les équipes.

## Silos
Le terme _Ops_ vient de la contraction du terme anglais  _Operationals_ souvent traduits par exploitants. Derrière ce terme se cache l'ensemble des exploitants. Et la liste est longue.

Que l'on observe la DSI d'un grand groupe ou une petite équipe informatique, les fonctions sont les mêmes. Citons pêle-mêle, les administrateurs systèmes (Linux, Windows, iSeries, etc.), les administrateurs réseaux, les administrateurs de bases de données, les administrateurs intergiciel (_middleware_), les responsables de la sécurité informatiques, les gestionnaires de stockage, les experts de la virtualisations, et les superviseurs. Et j'en oublie, néanmoins, ça donne une idée de ce que sont les _Ops_.

Quand toutes ces fonctions sont séparées en autant d'équipe, on parle de **silos**.

Et lors d'un projet informatique, il faut faire appel à tous ces corps de métier oeuvrant tour à tour, de silo en silo.

## Principale perte de temps
Comme évoqué plus tôt, la perte de vitesse dans un monde en pleine accélération est le premier motif au changement. Dans la recherche de ce qui provoque cette perte de vitesse, il est pertinent de se pencher sur les processus adoptés dans une DSI. Or lors d'une telle analyse, on constate que les latences ne sont pas dans l'exécution des tâches, mais dans l'attente entre deux tâches, entre deux silos.

![](images/TimeLine.jpg)

Prenons pour exemple une nouvelle application nécessitant deux machines virtuelles pour porter un serveur d'application et une base de données. L'utilisateur fera une demande qui sera prise en compte par l'équipe de virtualisation, puis par les administrateurs système, puis par les administrateurs de base de données, puis l'équipe intergiciel (_middleware_). Comme le suggère l'illustration, il faut 12 jours à l'utilisateur pour obtenir l'infrastruture prête à accueillir son application. Et ce, alors que la charge (temps de réalisation) est de 1 heure et demie.

L'utilisateur peut s'impatienter et se demander où en est sa demande, à quelle étape, pourquoi est-ce que c'est aussi long. Il est malheureusement courant d'entendre "ce n'est pourtant pas compliqué ça te prend deux minutes !". Il est possible que les équipes se renvoient la balle, ce n'est pas nous mais les autres qui ont pris leur temps.
Parfois les attentes des uns ne correspondent pas à ce qui est livré par les autres. Les raisons sont variées, inadéquations techniques, différents sur la sécurisation, mauvaises anticipations...

>A retenir :
Cette organisation en silo, génère un climat de tensions entre les équipes, voire de la défiance.


## Perte de qualité et de vélocité
Le clivage entre les équipes Dev et Ops et/ou dans une organisation en silos, entraînent des frictions voire des crises. Pragmatiquement, ça se traduit par des pertes de temps, des mauvaises livraisons, et à terme à une perte globale de qualité.

Pour rattraper cette qualité, certaines entreprises mettent l'accent sur :
- Les processus, ce qui crée encore plus de la latence.
- Les campagnes de tests, ce qui allongent les délais.

Ce qui génère de la perte de vélocité.


>A retenir :
Aucun perfectionnement des méthodes en place ne parvient à répondre à cette exigence de vélocité, il faut donc adopter une nouvelle approche !
