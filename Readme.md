# TP 1 : CI/CD

## Instructions
Les réponses aux questions posées dans cet énoncé doivent être soumises sous forme de fichiers nommé en fonction du numéro de la question au sein de votre repository, dans le dossier `answers`. 
Chaque réponse fera l'objet d'un nouveau fichier dans votre repository. 
> Les questions requérant une réponse sous forme de fichier seront taggées par l'icone suivante: ⚠️  Ces fichiers sont corrigés automatiquement par Github Autograde

> Les commits ne sont pas facultatifs. **Commitez au minimum dès que l'énoncé vous le demande**.

Le TP doit être rendu individuellement et se basera sur les réponses présentes dans les fichiers du dossier `answers`, ainsi que sur le code présent dans vos repositories personnels.

## Rappels
### Git
[Git Documentation Officielle](https://git-scm.com/docs)
Commande | Description
-- | --
`git clone` | Cloner un repository sur son poste
`git add` | Ajouter des fichiers à la staging area (qui sera prise en compte dans le prochain commit)
`git commit` | Créer un nouveau commit en local
`git push` | Pousser son arbre de commit local avec le serveur (Local --> GitHub)
`git pull` | Synchroniser son arbre local avec l'arbre distant (Local <-- GitHub)
`git branch` | Créer une nouvelle branch locale
`git merge` | Appliquer les changements d'une branche sur une autre branche localement

### Gitflow
![Gitflow diagram](https://backlog.com/app/themes/backlog-child/assets/img/guides/git/collaboration/branching_workflows_001.png)

### Pull request
![Pull request diagram](https://miro.medium.com/max/600/1*ubVyD2GaOAlSfqRNbL0Bjg.png)

### Github
* Classroom
* Issue

### Github actions
* Service SaaS - [github.com/features/actions](https://github.com/features/actions)
* Pipeline: CI vs CD
* Pipeline: Configuration as code

---

## 1 : Git 

### 1.0 : Création de compte Github
Allez sur [Github](https://github.com/) et se créer un compte si ce n'est pas déjà la cas.

### 1.1 : Accepter l'assignment 
Suivez le lien fourni par le professeur pour récupérer une copie personnelle de ce repository dans l'organisation GitHub Classroom `cours-esgi`.

### 1.2 : Cloner le repository
Clonez le repo nouvellement copié sur votre ordinateur 
 
### 1.3 : Faire un commit 
Dans votre repo, éditez le fichier `identity.md` et remplissez-le avec vos données personnelles (nom, prénom)

Committez et pushez les changements apportés au fichier
> Les commits ne sont pas facultatifs. **Commitez au minimum dès que l'énoncé vous le demande**.

> ⚠️  **ANSWER**: Créez un fichier s'intitulant `1.3` ayant pour contenu les commandes que vous avez effectué pour réaliser le commit et le push de vos changements.

### 1.4 : Naviguer dans les logs
Affichez les logs des commits précédents.

Faites attention au fait que tout est loggué depuis le début du projet. Vous pouvez trouver les messages, les dates mais aussi les auteurs des commits passés.

> ⚠️  **ANSWER**: Créez un fichier s'intitulant `1.4` ayant pour contenu la commande que vous avez effectué pour visualiser les logs.

### 1.5 : Ginny a disparu, j'ai peur qu'on ne la retrouve jamais !
A l'aide de la commande utilisée dans la question précédente, retrouvez la trace de **Ginny** avant qu'il ne soit trop tard !

> **Indice**: Cherchez dans la documentation de la commande précédente pour trouver des idées de commandes.

> ⚠️  **ANSWER**: Créez un fichier s'intitulant `1.5` ayant pour contenu **uniquement la commande** que vous avez effectué pour retrouver la trace de Ginny.

### 1.6 : Listez les branches
Listez **toutes** les branches présentes dans le repository.

Est-ce que toutes les branches vous paraissents normales ? Y a t-il une branche qui retient votre attention ? 
Si oui, déplacez vous dessus (checkout).

> ⚠️  **ANSWER**: Créez un fichier s'intitulant `1.6` ayant pour contenu la commande que vous avez effectué pour afficher les branches présentes dans votre repo et le nom de la branche qui a retenu votre attention.

### 1.7 : Créez une branche
Créez une branche à partir de la branche trouvée dans la question précédente. La branche à créer doit s'appeler `feature/` suivi de la première lettre de votre prénom puis du nom de famille en minuscule (pas d'espace ni d'accent dans le nom).

> Ex Albus Dumbledore --> feature/adumbledore

Puis, placez vous sur votre branche `feature/{nom}` nouvellement créée.

> ⚠️  **ANSWER**: Créez un fichier s'intitulant `1.7` ayant pour contenu les commandes que vous avez effectué pour créer et vous déplacez sur la nouvelle branche.

### 1.8 : Ah, c'est la que tu aurais aimé suivre le dernier cours ...
Répondez aux questions contenues dans le fichier `questions.md`, puis committez les changements sur la branche `feature/{nom}`.
Enfin, pushez tous vos changements présents réalisés sur toutes les branches sur votre repository GitHub.

> ⚠️  **ANSWER**: Créez un fichier s'intitulant `1.8` ayant pour contenu les commande que vous avez effectué pour pusher toutes les branches sur votre repo GitHub.

### 1.9 : Pull request time !!
Dans l'interface web GitHub, ouvrez une pull request partant de votre branche `feature/{nom}` pointant sur la branche develop de votre repository.

> **Warning**: Pensez bien à nous ajouter (laurent et arthur) en tant que reviewer de votre pull request afin que je puisse vous corriger.

Pour plus d'aide sur les pull requests voir la [documentation officielle](https://help.github.com/articles/about-pull-requests/)

### 1.10 : Gitflow
Lister les branches présentes dans le repo. Au sens Gitflow, à quoi servent ces chacunes de ces branches ?

> ⚠️  **ANSWER**: Créez un fichier s'intitulant `1.10` ayant pour contenu la description des branches existantes dans la méthodologie Gitflow qui sont présentes dans votre repository. (ex: la branche master sert à ...)

---

## 2 : CI/CD avec GitHub Actions
Dans cette seconde partie, vous devez utiliser le même repo que celui obtenu à la fin de la partie 1.

> ⚠️  **WARNING**: Chacunes des questions demandant une modification de code nécessite au minimum un commit et un push dans votre repository. Le découpage des commits est pris en compte dans la notation.

> Pour réaliser l'ensemble des étapes demandées dans cette partie, vous vous placerez sur la branche `develop`

Le but de cette seconde partie de TP est d'implémenter un pipeline CI (intégration continue) permettant d'automatiser:
* le téléchargement des dépendances utiles au build applicatif
* le build de l'application 
* les tests de l'application et leur mise à disposition dans une UI utilisable par n'importe qui
* la qualité de code grâce à Sonarcloud
* le package de l'application à l'aide de Docker - sans pression, je vous donne tout pour la partie Docker pour l'instant

Pour cela, nous allons utiliser une solution SaaS intégrée à GitHub appelée **GitHub Actions**.

Cette solution permet notamment grâce à son système de pipeline d'implémenter les automatisations que nous voulons réaliser dans ce TP.

Les pipelines sont décrits à travers des fichiers de code YAML (pipeline as code).

Pour avoir un aperçu des fonctionnalités de GitHub Actions, [voir la page officielle](https://docs.github.com/en/actions)
Pour plus de documentation sur la syntaxe des fichier YAML, [voir la documentation officielle](https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions)

> **Important**: La documentation ci-dessus sera indispensable pour pouvoir mener à bien ce TP et les suivants.

### 2.1 : Création de votre premier Pipeline - Build & Test
Pour créer votre premier pipeline, il est nécessaire de créer un fichier `main.yaml` au sein d'un dossier intitulé `.github/workflows/` dans votre repository applicatif.
Cela va vous permettre de créer le fichier YAML correspondant à la Continuous Integration (CI) de votre projet.

Dans ce fichier, ajoutez le code suivant :

```yaml
# This is a basic workflow to help you get started with Actions
name: CI

# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but only for the develop branch
  push:
    branches: [ develop ]
  pull_request:
    branches: [ develop ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v2
```

Ce fichier décrit plusieurs étapes essentielles à la mise en place d'un pipeline:
* **triggers** (`on` keyword): Définit à quelles conditions seront réalisées les actions décrites dans ce pipeline
* **steps**: La description des étapes à automatiser

Vous pouvez maintenant commiter le fichier et le pousser sur github.com. 

> ⚠️  **WARNING**: N'oubliez pas d'ajouter un message de commit ayant du sens à chaque commit. Cela vous aidera lorsque vous reviendrez sur le projet dans le futur

Observez dans la UI de GitHub Actions l'exécution du pipeline.

### 2.2 : Buildons notre application
Pour l'instant, le build ne fait pas grand chose.
Nous allons donc modifier le pipeline pour faire en sorte de builder notre application java.

Pour cela, modifiez le fichier `.github/workflows/main.yml` pour y ajouter les étapes de build applicatif.

Le projet est un projet Java qu'il faut donc compiler. Ce projet nécessite le JDK Java 8, ainsi que maven pour être compilé.

Il est nécessaire d'installer deux étapes supplémentaires :
* l'installation du JDK Java 8. L'action à utiliser : https://github.com/marketplace/actions/setup-java-jdk
  * Il faudra renseigner comme version de Java `11`, et comme distribution `adopt`
* la compilation avec Maven. L'action à utiliser : https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-java-with-maven
  * le goal maven à lancer est `package`

Commitez vos changements et observez le build de votre application.

### 2.3 : Intégrer les résultats de tests
Si vous observez bien les logs de build, vous verrez que des tests unitaires sont exécutés.
Nous allons récupérer le rapport de test pour l'afficher dans le résultat du pipeline.

Pour cela, modifiez le fichier `.github/workflows/main.yml` pour y ajouter les étapes de publication de tests unitaires. L'action à utiliser : https://github.com/marketplace/actions/publish-unit-test-results

Commitez vos changements et observez le build et le résultat des tests unitaires de votre application.

### 2.4 : Analysez votre code avec Sonarcloud
La prochaine étape va être d'analyser votre code applicatif. Sonarcloud est une plateforme SaaS permettant d'analyser le code Java (entre autre) pour détecter des problèmes sur votre code.

La première étape est d'aller sur le site https://sonarcloud.io/sessions/new et de se connecter avec Github. Ensuite, créez un projet sur https://sonarcloud.io/projects/create et selectionnez votre compte Github, puis le repository commencant par `lab-git-ci`. Toutes les informations nécessaires afin d'ajouter l'analyse dans Sonarcloud sont décrites dans la page du nouveau projet.

Afin que Github puisse pousser le résultat de l'analyse sur Sonarcloud, il est nécessaire d'ajouter le token fourni par Sonarcloud dans Github. Ce token sera à ajouter en tant que secret dans votre repository Github avec comme nom `SONAR_TOKEN`. Pour ajouter un secret dans Github, allez dans votre repository, puis l'onglet `Settings` et ensuite `Secrets`
L'action à utiliser : https://github.com/marketplace/actions/sonarcloud-scan

Commitez vos changements et observez le build et l'artifact publié sur la page du build.

### 2.5 : Publier l'artefact buildé
Vous allez maintenant publier l'artefact que vous avez buildé dans les étapes précédentes.
Cela vous permet de télécharger l'artefact en question mais aussi de le déployer dans des étapes ultérieures sur différents environnements.

Pour cela, modifiez le fichier `.github/workflows/main.yml` pour y ajouter les étapes de publication. L'action à utiliser : https://github.com/marketplace/actions/upload-a-build-artifact

Commitez vos changements et observez le build et l'artifact publié sur la page du build.

### 2.6 : Ajout du packaging
Jusqu'ici le pipeline build et test l'applicatif mais aucun package déployable n'est réalisé ou persisté. 
Vous allez créer une image Docker afin de rendre notre applicatif prêt à l'emploi.

Pour cela, créez un fichier Dockerfile à la racine de votre projet contenant le code suivant:
```dockerfile
FROM openjdk:8-jre-slim

COPY target/my-app-1.0-SNAPSHOT.jar /root/my-app-1.0-SNAPSHOT.jar

CMD ["java", "-jar", "/root/my-app-1.0-SNAPSHOT.jar"]
```

Puis, modifiez le fichier `.github/workflows/main.yml` pour y ajouter les étapes de packaging. L'action à utiliser : https://github.com/marketplace/actions/build-and-push-docker-images

Commitez vos changements une dernière fois et observez le build de l'image Docker via les logs.

### 2.7 : Mise en place de la gestion multi-branche
Pour l'instant votre pipeline ne se déclanche que sur la branche `develop` (cf. trigger).

Modifiez la valeur du trigger afin de lancer le pipeline sur toutes les branches de type:
* master
* develop
* feature (attention, regarder la nomenclature gitflow)

Après avoir réalisé ces changements, mergez tous vos changements proprement jusqu'à `master`

### 2.8 : Création d'une nouvelle branche
Votre pipeline est maintenant prêt à exécuter les étapes définies en son sein quelles que soient les branches qui soient créées. 

Créez une branche `feature/test-build` à partir de la branch develop et constatez que le build est automatiquement appliqué sur cette branche.

### 2.9 : Conclusion
Vous pouvez maintenant créer plusieurs branches features et vous apercevoir que ces branches se verront appliquée les étapes de build, test, code quality et package.

Toute cette configuration permet d'avoir un système de validation au plus près sans perdre de temps sur les feedback rapides attendus pour améliorer la qualité des produits.

### Bonus
Un point bonus peut-être attribué si vous arrivez à mettre un système de cache pour les dépendances Maven, ainsi que pour les images Docker.