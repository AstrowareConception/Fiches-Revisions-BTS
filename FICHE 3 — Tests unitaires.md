# FICHE 3 — Tests unitaires

---

## Problématique

Comment vérifier automatiquement qu’une fonctionnalité fonctionne correctement et éviter les régressions ?

---

## Bonnes pratiques essentielles

### Rôle des tests unitaires

Un test unitaire permet de :

* vérifier qu’une méthode fonctionne comme attendu
* détecter les erreurs rapidement
* sécuriser les évolutions du code

Objectif : garantir la fiabilité du code.

---

### Structure d’un test

Un test suit toujours la même logique :

1. Préparer les données (initialisation)
2. Exécuter la méthode à tester
3. Vérifier le résultat

Structure classique :

```text
Arrange → Act → Assert
```

---

### Assertions

Les assertions permettent de vérifier le résultat :

* `assertTrue(condition)` : vérifie que c’est vrai
* `assertFalse(condition)` : vérifie que c’est faux
* `assertEquals(valeurAttendue, valeurObtenue)`

Objectif : comparer le résultat obtenu avec le résultat attendu.

---

### Tests pertinents

Un bon test doit :

* tester un cas valide
* tester un cas invalide
* couvrir les cas limites

Exemple :

* mot de passe valide
* mot de passe trop court
* mot de passe déjà utilisé

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* comprendre un test existant
* compléter une méthode de test
* choisir les bonnes assertions
* tester différents cas (normal, erreur, limite)

Les tests unitaires sont explicitement attendus dans les exercices sur le code Java .

---

## Réflexe à retenir

PRÉPARER → EXÉCUTER → VÉRIFIER

---

## À retenir

Un code sans test est un code dont on ne peut pas garantir le bon fonctionnement.
