# La métrologie
Votre IT est porteur du besoin de votre activité. Mais comment établir leur rapport en terme de business ?
Vos développements dégagent-ils autant de profit que prévu ? Utilisez-vous votre IT à bon escient ? Les ressources sont-elles allouées au regard de l'activité ? Maintenez-vous des systèmes rentables ? Livrez-vous bien de la valeur ?

Nous verrons dans ce chapitre comment la métrologie répond à toutes ces questions.

## Feedback
Beaucoup d'entreprises au sein desquelles je suis intervenu, travaillent au jugé. Combien de fois ai-je entendu "c'est plutôt lent", "ça prend un certain temps", "j'ai l'impression que ça fonctionne plus ou moins" ?
Pour savoir de quoi l'on parle, il faut obtenir un retour tangible des éléments et des événements, un _feedback_.

Une des clefs de succès d'une démarche DevOps est la **mesure**. L'intitiave de mesurer les choses s'appelle la métrologie.

> Le bateau DevOps ne navigue pas au doigt mouillé mais aux instruments.

Pourquoi est-ce un élément clef ? Parce qu'une transformation DevOps est une amélioration constante, et qu'on ne peut améliorer que ce que l'on peut mesurer.
Mise en situation. Il est très délicat de répondre à ce cas de figure : "Et là ? C'est plus lent ou c'est moins lent ?". Alors que "on est passé de 3s à 12ms" expose deux constats et un résultat.

>A retenir :
On ne peut améliorer que ce que l'on peut mesurer.

## Partie intégrante de l'application
La métrologie, est un socle indispensable à l'ensemble des pratiques DevOps. Elle permet de constater les améliorations ou les dégradations sur l'ensemble des processus mis en oeuvre entre le _commit_ du développeur et le maintien en condition opérationnel.

Il faut considérer la métrologie comme une partie intégrante de l'application. Une application doit être livrée avec la métrologie afférente, ce n'est pas une démarche à part voire a posteriori. Il faut donc adopter la mise en oeuvre de la métrologie à l'ensemble des environnements et des processus de recette, les tests, les sauvegardes, les provisions, les applications de configurations, etc.

## Générer, collecter, analyser
La métrologie est une pratique se réalisant en trois étapes indispensables :
- générer
- collecter
- analyser

#### Générer
Il faut générer les historiques, les métriques, les informations nécessaires. Sans cette première étape rien n'est possible.

#### Collecter
Les informations générées sont disséminées dans différents fichiers de _log_, de base, sur différents fichiers. Pour pouvoir confronter et corréler ces informations, il faut les collecter dans un dépôt central.

#### Analyser
Une fois collectées ces informations pourront être consultées et affichées sous forme de tableau, de graphe, de camembert dans le but de les analyser. Que ce soit pour mieux comprendre une situation incidentelle ou particulière, ou pour mieux anticiper une évolution.

>A retenir :
Les trois actions de la métrologie sont générer, collecter, analyser.

## Tout collecter
Quand on s'intéresse à la métrologie, il est fréquent de lire l'aphorisme anglais _measure everything_. J'apporterai une traduction et interprétation personnelles : Tout collecter.

Il faut générer et collecter un maximum d'éléments dans l'optique de répondre à tous les cas de figures.
On peut imaginer le cas de figure où la base de données présente des soucis de performances et qu'après investigation on mette en doute les temps d'accès disques. Depuis quand est-ce que ces temps se sont dégradés ? Zut ! On n'a pas collecté cette information.
Qu'est-ce que cela aurait pu donner comme information ? Que cela correspond à la date à laquelle une nouvelle baie a été installée dans le _datacenter_, par exemple.

Cet exemple souligne l'importance de la collecte de ce que l'on appelle des événements.

## Evénements
Les événements sont des marqueurs temporels, des jalons pour lesquels il y a un avant et un après. Pour reprendre l'exemple de la nouvelle baie disque, on pourra noter les deux événements début et fin de la mise en place qui marquent le avant, le pendant et le après la mise en place.
Ces informations pourraient être utiles pour déterminer une corrélation de faits sur le matériel proche voire l'ensemble du _datacenter_.

Un autre exemple qui permet de mieux comprendre l'usage des événements pour la métrologie en tant qu'instrument d'amélioration : le nouveau développeur. Ca parait farfelu que de notifier à son outil de métrologie qu'un nouveau développeur est arrivé. Et pourtant ! Suite à son arrivée on pourra prévoir une dégradation des indicateurs de qualité du développement. Ce qui est normal pour un nouvel arrivant. Après une petite période d'adaptation on constatera un retour à la normale.
Pourquoi est-ce pertinent ? La pertinence est dans la confrontation de la longueur de cette période d'adaptation pour tous les nouveaux arrivants. Si la période s'allonge, il faut agir (pour limiter la perte de qualité), et l'action pourra se porter sur la méthode de recrutement, sur l'effort de _on-boarding_ voire sur le contexte (l'application est peut-être de plus en plus complexe à aborder).

Evidemment il faut notifier le déploiement d'une application avec sa version qu'on puisse corréler une version en production et son comportement dans les différents environnements de recette. Ce qui n'est pas chose facile quand il faut retrouver la période de tests de telle version dans un tableau d'avancement de projet. En marquant dans son outil de métrologie l'événement _Release_ il sera possible de filter et afficher la même mesure dans différents environnements.

>A retenir :
Les événements sont les marqueurs temporels distinguant l'avant de l'après d'un fait ce qui aide à la compréhension d'un comportement.

Pour citer d'autres exemples d'événements communs, notons le changement de matériel, le changement de configuration, les déménagements, les montées de version des différents outils, progiciels ou gratuiciels, la date d'ouverture d'une nouvelle agence, la mise en service d'un nouveau plateau, le lancement d'une campagne de publicité, la publication d'un article vous concernant, une actualité, un fait, une loi concernant votre activité.

>Les gains associés à la prise en compte des événements sont dans la réactivité sur incidents, ou sur anticipation.

## La supervision
Très souvent, le terme métrologie est compris comme de la supervision. Voyons donc ici que ces deux pratiques sont différentes et présente une complémentarité. En d'autres termes, l'un n'est pas l'autre, et il faut les deux pour être complet.

La supervision est la surveillance d'un état inattendu ou d'un seuil franchi. C'est binaire voire ternaire : OK, KO, incertain (ou warning). Le résultat appelle ou non à une intervention (d'urgence ou planifiée). On s'attache ici non pas aux valeurs des sondages, mais à leur confrontation avec un seuil ou à l'état attendu.

La supervision répond (par oui ou par non) à ce genre de questions : Le taux d'occupation de l'espace disque dépasse-til 80% ? Dans les 10 dernières secondes la CPU est-elle à 100% ? Le traitement est-il bien terminé ? Le service est-il démarré ? 

A ne pas confondre donc avec la métrologie qui collecte des mesures et analyse la bonne santé générale de tout ou partie de son SI.

>A retenir :
La supervision est la surveillance d'un état inattendu ou d'un seuil franchi.

### Parenthèse terminologique
La terminologie de _monitoring_ est floue et confuse, et interfère avec celle de supervision. Parfois, on peut lire l'approche monitoring = supervision + métrologie, pourquoi pas. Certains contestent l'incorporation ou non de l'état des traitements. Sauf que tel qu'à l'hôpital, le _monitoring_, ce qui importe n'est pas la valeur en soi, mais le bip lorsque ça sort du scope.

Pour ma part mon approche est que le _monitoring_ est l'anglicisme de supervision. De faire de subtiles distinctions entre _monitoring_ et supervision, de toutes façons, ne change rien sur le concept exposé ici.

### Différence entre supervision et métrologie
Un exemple vaut mieux que deux définitions tu l'auras. Imaginons un espace disque dédié pour la réception de fichiers à intégrer. Ils ont une rétention définie pour se caler avec les besoins de reprise et les sauvegardes. L'occupation devrait être peu ou prou constant.
Dans un tel cas, une supervision de contrôle de l'espace disque sera mise en place avec des seuils de taux d'occupation, par exemple de 80% à 94% l'alerte sera un warning, pour anticiper une action de fond, et de 95 à 100% un KO pour une action immédiate.
Comme nous l'avons déjà dit, dans le cas de la métrologie, on abordera le sujet différemment. Aucun seuil, mais des mesures à effectuer. Et si on retrouvera l'espace disque, on retrouvera aussi l'activité disque (I/O, répartitions sur le raid, etc.), mais aussi la taille des fichiers reçus, leur date/heure d'arrivée. Car, pour l'exemple, la taille croissante des fichiers est la cause du franchissement du seuil d'occupation disque. Et c'est l'énorme différence !

Cette différence n'est pas seulement sur la forme, mais c'est aussi sur le fond. En mesurant l'évolution de la taille de mes fichiers, non seulement je vais anticiper mon occupation disque, mais je vais aussi pouvoir corréler cette mesure avec la mesure du temps d'intégration afin de théoriser sur cette relation de cause à effet taille de fichiers / temps de traitement. Je vais pouvoir mettre en relation, ma charge CPU, mémoire, les temps de réponse, la charge réseau, etc. L'ensemble de ces mesures me permettent de mieux comprendre comment évolue la partie de mon SI en charge de l'intégration de ces fichiers.

Un autre exemple plus sommaire :
La supervision surveille si l'espace disque dépasse les 80 %. Oui ou non ?
Avec la métrologie, on mesurera : l'espace disque totale est de 1To, son occupation actuelle est de 750 Go, quotidiennement sont reçus des fichiers de 1Go. On analysera une rupture prévisionnelle dans 250 jours.
Au bout de 100 jours, on mesurera : une occupation est de 850 Go, mais plus de réception de fichiers, on analysera qu'il n'existe plus aucune rupture prévisionnelle.
Noter qu'on parle d'un côté d'un taux (80%) et de l'autre de valeurs (1To, 750GO, 1Go, 850Go).

La supervision n'opère pas à des corrélations, elle ne s'attache qu'à relever les cas anormaux.

>A retenir :
La supervision surveille l'état et les seuils et alerte des cas anormaux, alors que la métrologie mesure la bonne santé du SI.
La supervision alerte des conséquences quand la métrologie peut prévenir des causes.

### Ne répond pas à la perception
L'autre point de différence est dans la perception. Avec la supervision, on peut connaitre un état OK ou KO, mais ça ne permet pas de répondre à l'utilisateur qui perçoit l'application, par exemple le fameux "c'est lent". Avec la métrologie, on peut mieux déceler le point d'achoppement responsable du malaise que ce soit une latence, ou une perte d'informations. "Selon nos mesures, ça prenait 1,2 secondes, effectivement, nous sommes actuellement à 9 secondes". "Après correction, nous sommes passé de 2 secondes à 4 ms". Dans un sens ou un autre, déterioration ou amélioration, la métrologie permet de quantifier en partie la perception des utilisateurs.
La supervision n'a pas cette grille de lecture, c'est noir ou blanc mais pas entre gris clair et gris foncé.

### Pratiques complémentaires
Pour terminer cette longue parenthèse sur la supervision, on pourrait s'imaginer à cette lecture, qu'on pourrait se passer de la supervision au profit de la métrologie, or ce n'est pas le cas.

Le but avoué de la supervision est de s'aider lors des interventions et pour cela on tente de surveiller bien des aspects de sa production dans les conséquences et non dans les causes. Et on pourrait donc s'imaginer réduire la supervision en supprimant le superflu (ceinture, bretelles, parachute) quant aux conséquences en privilégiant bien plus la prévention, en s'attachant aux causes. Et cette analyse préventive est un des objectifs de la métrologie.

Effectivement, on pourrait réduire sa supervision au profit d'une meilleure métrologie, mais on ne pourrait jamais la supprimer. Ne serait-ce que la prise en compte d'un aléa, un matériel qui crame, une réception de fichier d'une taille exorbitante, un déni de service, etc.

Si la position du curseur entre supervision et métrologie devrait (pour une amélioration de la qualité de service) être revu, les deux sont complémentaires. D'ailleurs beaucoup d'outils proposent les deux approches en solution native ou à l'aide de greffons.

>Les gains associés à cette pratique de supervision sont dans la réactivité face à un aléa.

### Dans une démarche DevOps
On pourrait considérer que la mise en place de la supervision est une démarche classique et qu'elle ne s'inscrit pas particulièrement dans une démarche DevOps. Plus trivialement, que la supervision n'offre rien de plus dans une démarche DevOps. Ce n'est pas exact.

D'une part, la supervision est trop souvent cantonnée à la production, et peu voire pas du tout mise en place dans les environnements de recette. Il faut bien sentir la nécessité première de la mise en place de la supervision sur tous les environnements. Découvrir par voie de conséquences qu'un banc de tests est arrêté est préjudiciable en terme de durée accrue des tests et donc de temps de livraison. Il est préférable d'être alerté (objet de la supervision) et d'intervenir au plus vite.

D'autre part, il faut considérer la supervision comme une partie intégrante de l'application. Une application doit être livrée avec la supervision afférente, ce n'est pas une démarche à part voire a posteriori. Il faut donc éprouver cette supervision à l'ensemble des environnements de recette. La supervision doit elle aussi être recettée.

>A retenir :
Quant à la supervision, l'approche DevOps apporte la nécessité de la considérer comme une fonctionnalité de l'application qui doit être recettée.


