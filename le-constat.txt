# Le constat

## Le paradigme actuel ne suffit plus.
Pour répondre à toutes ces nouvelles questions, le paradigme actuel ne suffit plus. Certes, mais pourquoi ? Qu'est-ce qui provoque cette perte de vitesse ?

## Divergence d'approche
Si on simplifie une DSI à deux équipes, on constate :
- Les équipes d'exploitation sont garantes de la stabilité et de l'intégrité du système
- Les équipes de développement apportent des aménagements et des nouveautés.
Alors qu'elles oeuvrent toutes les deux pour le bénéfice de l'activité, leurs approches sont antagonistes.

## Clivage entre les Devs et les Ops
Il n'est pas rare qu'à la machine à café des exploitants (les Ops) l'on se raconte la dernière des Devs qui mettent la production en péril avec des programmes calamiteux et des processus de livraisons mal ficelés.
De même les Devs vont parler de « ces gros bourrins de la prod' » qui n'ont pas compris et/ou appliqué les consignes comme il se doit.

Le fameux « ça fonctionnait sur mon laptop », lui révèle une méconnaissance des configurations et/ou contraintes de sécurité des serveurs de production.
Son corollaire, pour régler un problème urgent, entraîne une distorsion « temporaire » de la production, en faisant fi des standards.

Outre ces anecdotes, d'autres symptômes sont révélateurs :
Combien de temps vous faut-il pour détecter un bug, l'analyser, et livrer le correctif ?
Et combien de correctifs faudrait-il pour ce même incident ?

Ces résultats sont directement liés à la coopération entre équipes.

## Silos
Le terme _Ops_ vient de la contraction du terme anglais  _Operationals_ souvent traduits par exploitants. Derrière ce terme se cache l'ensemble des exploitants. Et la liste est longue.

Que l'on observe la DSI d'un grand groupe ou une petite équipe informatique, les fonctions sont les mêmes. Citons pêle-mêle, les administrateurs systèmes (Linux, Windows, iSeries, etc.), les administrateurs réseaux, les administrateurs de bases de données, les administrateurs intergiciel (_middleware_), les responsables de la sécurité informatiques, les gestionnaires de stockage, les experts de la virtualisations, et les superviseurs. Et j'en oublie, néanmoins, ça donne une idée de ce que sont les _Ops_.

Quand toutes ces fonctions sont séparées en autant d'équipe, on parle de *silos*.

Et lors d'un projet informatique, il faut faire appel à tous ces corps de métier oeuvrant tour à tour, de silo en silo.

## Perte de qualité et de vélocité
Ce clivage entre les équipes entraînent des frictions voire des crises.
Pragmatiquement, ça se traduit par des pertes de temps, des mauvaises livraisons, et une perte globale de qualité.

Pour rattraper cette qualité, certaines entreprises mettent l'accent sur :
- Les processus, ce qui crée de la latence.
- Les campagnes de tests, ce qui allongent les délais.

Ce qui génère de la perte de vélocité.

