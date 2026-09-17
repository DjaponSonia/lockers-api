## Résultat du test

Lors de l'exécution du pipeline, 2 tests passent et 1 test échoue.

Le test `test_occupancy_rate` attend une valeur de `33.33`, tandis que l'application retourne `33.3`.

J'ai conservé cet état sans modifier le code, car cette différence doit être clarifiée avec l'équipe : il faut déterminer si le taux doit être arrondi à une ou deux décimales.



# Synthèse technique

## 1. Ce que j'ai mis dans le pipeline

J'ai mis en place un workflow GitHub Actions déclenché lors des `push` et des `pull_request`.

Le pipeline réalise les étapes suivantes :

1. récupération du dépôt ;
2. configuration de Python 3.12.6;
3. installation des dépendances depuis `requirements.txt` ;
4. exécution des tests avec `pytest`.

J'ai choisi ce socle car il permet de détecter automatiquement les régressions lors des modifications du projet, tout en restant adapté à la taille de l'application et au temps disponible pour l'exercice.

## 2. Ce que j'ai volontairement laissé de côté

Je n'ai pas mis en place de déploiement automatique (CD), car l'exercice demande prioritairement une intégration continue et ne fournit pas d'environnement cible de déploiement.

Je n'ai pas non plus ajouté une chaîne exhaustive de sécurité, de build ou de déploiement afin de privilégier les contrôles essentiels dans le temps imparti.

## 3. Si j'avais une semaine supplémentaire

Je commencerais par :

- ajouter un linter et un formateur Python ;
- ajouter des contrôles de sécurité des dépendances ;
- améliorer la gestion des secrets et de la configuration ;
- renforcer les tests ;
- mettre en place une stratégie de protection de la branche `main` ;
- étudier un processus de build et de déploiement automatisé si un environnement cible est disponible.

## 4. Ce qui m'a manqué

Le principal élément manquant pour aller plus loin dans le déploiement est un environnement cible clairement défini.

Il aurait également été utile de connaître les contraintes de production, notamment l'infrastructure utilisée, le mode d'hébergement et les exigences de sécurité.
