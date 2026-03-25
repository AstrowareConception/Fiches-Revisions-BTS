# FICHE 13 — Stockage sécurisé des mots de passe

---

## Problématique

Comment stocker les mots de passe des utilisateurs sans compromettre leur sécurité en cas de fuite de données ?

---

## Bonnes pratiques essentielles

### Interdiction du stockage en clair

Un mot de passe ne doit **jamais** être stocké en clair dans une base de données.

Risque :

* si la base est compromise → tous les comptes sont exposés

---

### Principe du hachage (hash)

Un mot de passe doit être transformé via une fonction de hachage :

* transformation irréversible
* même entrée → même résultat
* impossible de retrouver le mot de passe original

Exemple :

```
motdepasse → hash
```

---

### Ajout d’un sel (salt)

Un sel est une valeur ajoutée au mot de passe avant le hachage :

* rend chaque hash unique
* empêche les attaques par tables pré-calculées

---

### Algorithmes recommandés

Utiliser des fonctions adaptées :

* bcrypt
* Argon2
* PBKDF2

Objectif : ralentir les attaques par force brute.

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* expliquer pourquoi le stockage en clair est dangereux
* comprendre le principe du hachage
* distinguer stockage sécurisé et non sécurisé
* proposer une solution adaptée

---

## Réflexe à retenir

NE JAMAIS STOCKER → TOUJOURS HASHER

---

## À retenir

Un mot de passe ne doit jamais être stocké tel quel, uniquement sous forme hachée.
