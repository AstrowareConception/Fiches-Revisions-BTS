# FICHE 4 — Authentification et habilitation

---

## Problématique

Comment contrôler l’accès des utilisateurs à une application en fonction de leurs droits ?

---

## Bonnes pratiques essentielles

### Authentification

L’authentification permet de vérifier l’identité d’un utilisateur.

Exemples :

* identifiant + mot de passe
* session utilisateur

Objectif : s’assurer que l’utilisateur est bien celui qu’il prétend être.

---

### Habilitation (autorisation)

L’habilitation permet de définir ce que l’utilisateur a le droit de faire.

Exemples :

* consulter des données
* modifier des informations
* accéder à certaines fonctionnalités

Objectif : limiter les actions selon le rôle de l’utilisateur.

---

### Gestion des droits

Chaque utilisateur possède un niveau ou un rôle :

* administrateur
* utilisateur standard
* invité

Les fonctionnalités accessibles dépendent de ce niveau.

Principe :

* un utilisateur ne doit accéder qu’aux fonctionnalités autorisées
* les accès doivent être contrôlés systématiquement

---

### Contrôle dans l’application

Le système doit :

* vérifier le niveau d’habilitation
* comparer avec le niveau requis
* autoriser ou refuser l’accès

Exemple :

* un menu n’est accessible que si le niveau est suffisant

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* distinguer authentification et habilitation
* comprendre un système de gestion des droits
* exploiter un niveau d’habilitation dans un code
* expliquer l’intérêt de restreindre les accès

Ces notions sont directement évaluées dans les questions sur la sécurité des applications .

---

## Réflexe à retenir

IDENTIFIER → VÉRIFIER → AUTORISER

---

## À retenir

Un utilisateur authentifié n’est pas forcément autorisé à tout faire.
