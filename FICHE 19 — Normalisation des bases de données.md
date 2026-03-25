# FICHE 19 — Normalisation des bases de données

---

## Problématique

Comment structurer une base de données pour éviter les incohérences et les redondances ?

---

## Bonnes pratiques essentielles

### Objectif de la normalisation

* éviter les duplications
* garantir la cohérence des données
* faciliter la maintenance

---

### Formes normales

1NF :

* pas de données répétées
* attributs atomiques

2NF :

* dépendance complète à la clé primaire

3NF :

* pas de dépendance entre attributs non clés

---

### Exemple

Au lieu de stocker :

* client + commande dans la même table

On sépare :

* table Client
* table Commande

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* comprendre les principes de normalisation
* repérer une base mal structurée
* proposer une amélioration

---

## Réflexe à retenir

SÉPARER → STRUCTURER → RELIER

---

## À retenir

Une base bien normalisée limite les erreurs et les incohérences.
