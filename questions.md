# Questions

## Question 1: Donnez moi votre définition du DevOps ?

Le devops est pour moi une philosophie qui vise à mettre en relation les parties "Développement" et "Opérationnel" d'un service.

C'est un peu un workflow global à mettre en place au sein d'une équipe, qui lisse les responsabilités des uns et des autres, et qui introduit des principes et technologies telles que l'intégration continue, le déploiement continu ...

## Question 2: Qu'est-ce que le continuous delivery ?
La livraison continue est une facette de la philosophie devops, qui vise à fournir un exécutable applicatif testé, et prêt à être déployé.

Cette étape est la suite logique d'un processus d'intégration continue, et peut ensuite donner lieu à un déploiement continu.

## Question 3: Donnez le nom d'un serveur d'intégration continue (nom de la solution) ?
Il existes de nombreux outils/Serveurs d'intégration continue, tels que Gitlab CI/CD, ou Jenkins.

## Question 4: Pourquoi tester automatiquement ?

Pour pouvoir mettre en place un circuit complètement automatisé, de validation des changements (intégration continue).
Le passage ou non des tests, conditionnera ainsi l'issue d'un "pipeline" CI/CD lancé

## Question 5: Pouvez-vous me citer des méthodologies d'amélioration du niveau technique interne de l'équipe agile ?

Il existe de nombreuses manières de renforcer la montée en puissance d'une équipe (d'un point de vue technique).

Une des plus connues: le pair programming ! Rudement efficace, il permet un step-up du niveau technique, et de la cohésion, d'une équipe.

Cela peut aussi passer par des présentations effectuées, lors de technical breakfast, ou en fin de sprint. En plus d'instruire le reste de l'équipe, cela renforce les compétences du "présentateur".

## Question 6: Quel est le but d'une démo de fin de sprint ?
Une démo en fin de sprint permet à un employé de faire découvrir une technologie ou un sujet au reste de l'équipe. Il peut s'agir d'un side project qu'il a à coeur de présenter, ou d'une veille technologique portant sur un sujet d'actualité.

L'idée ici est de renforcer la communication, ainsi que la culture, d'une équipe.

## Question 7: J'essaye d'accéder au site suivant : https://www.google.com/. Cependant, je n'arrive pas à y accéder depuis mon poste. Quelles sont les commandes que je peux lancer pour identifier ce qui m'empêche d'accéder à ce site ?

Je peux dans un premier temps, essayer un **ping google.com**, et regarder s'il y a des packet loss (potentiellement de mon côté, pas de connexion...?), ou des problèmes du côté de Google

Il peut aussi s'agir d'un problème de dns, qui nécessitera un changement de serveurs DNS au niveau du fichier  **/etc/resolv.conf**
