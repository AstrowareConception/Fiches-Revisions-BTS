# FICHE 11 — Modélisation et minimisation des données

---

## Problématique

Comment concevoir une base de données respectant les besoins métier tout en limitant les données personnelles ?

---

## Bonnes pratiques essentielles

### Modélisation des données

Une base de données doit :

* représenter les informations nécessaires au fonctionnement de l’application
* être structurée de manière cohérente (tables, attributs, clés)
* éviter les redondances

Objectif : garantir la cohérence et l’efficacité des données.

---

### Minimisation des données

Principe fondamental du RGPD :

* ne collecter que les données nécessaires
* supprimer ou ne pas stocker les données inutiles
* adapter la structure aux usages réels

Exemple :

* pour des statistiques, inutile de stocker nom et prénom

---

### Anonymisation

L’anonymisation consiste à :

* supprimer les éléments identifiants
* conserver uniquement les données utiles

Exemples :

* âge au lieu de date de naissance
* département au lieu d’adresse complète

Objectif : exploiter les données sans identifier les personnes.

---

### Création de tables adaptées

On peut créer une nouvelle table dédiée :

* contenant uniquement les données utiles
* sans informations sensibles

Exemple :

* table pour statistiques clients anonymes

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* proposer une structure de table cohérente
* distinguer données utiles et inutiles
* appliquer le principe de minimisation
* adapter une base de données à un besoin précis

Ces compétences sont évaluées dans les questions de conception de base de données .

---

## Réflexe à retenir

SÉLECTIONNER → SIMPLIFIER → PROTÉGER

---

## À retenir

Une bonne base de données ne stocke pas toutes les données possibles, seulement celles qui sont nécessaires.
