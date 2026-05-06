# FICHE 28 — Tests d’intégration et tests fonctionnels

---

## Problématique

Comment vérifier qu’une application fonctionne correctement dans son ensemble avant sa mise en production ?

---

## Bonnes pratiques essentielles

### Rôle des tests

Les tests permettent de :

* détecter les erreurs ;
* vérifier les fonctionnalités ;
* garantir la stabilité de l’application.

Objectif :

* assurer la qualité du logiciel.

---

### Tests unitaires

Les tests unitaires vérifient :

* une méthode ;
* une fonction ;
* un composant isolé.

Objectif :

* tester un élément précis du code.

---

### Tests d’intégration

Les tests d’intégration vérifient :

* le fonctionnement entre plusieurs composants ;
* les échanges entre modules ;
* les connexions avec la base de données ou les API.

Exemple :

* formulaire → contrôleur → base de données.

Objectif :

* vérifier que les éléments fonctionnent ensemble.

---

### Tests fonctionnels

Les tests fonctionnels vérifient :

* les fonctionnalités attendues par l’utilisateur ;
* le respect du cahier des charges.

Exemple :

* création de compte ;
* connexion ;
* validation d’une commande.

Objectif :

* contrôler le comportement global de l’application.

---

### Jeux de données de test

Les tests doivent utiliser :

* des données réalistes ;
* des cas normaux ;
* des cas limites ;
* des cas d’erreur.

---

### Rapport de tests

Un rapport de tests doit indiquer :

* les scénarios réalisés ;
* les résultats obtenus ;
* les anomalies détectées.

---

### Automatisation des tests

Les tests peuvent être automatisés afin :

* d’être rejoués rapidement ;
* de détecter les régressions ;
* de sécuriser les évolutions du projet.

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* distinguer tests unitaires, intégration et fonctionnels ;
* proposer des scénarios de test ;
* analyser un résultat de test ;
* rédiger un rapport simple.

Le référentiel E5 insiste fortement sur les tests et la validation des solutions applicatives. 

---

## Réflexe à retenir

TESTER → VÉRIFIER → VALIDER

---

## À retenir

Une application n’est considérée comme fiable que si ses fonctionnalités ont été testées dans des conditions réalistes.
