# FICHE 9 — Attaque CSRF (Cross-Site Request Forgery)

---

## Problématique

Comment empêcher qu’un utilisateur effectue, sans le savoir, une action sur une application à laquelle il est déjà connecté ?

---

## Bonnes pratiques essentielles

### Principe de l’attaque CSRF

Une attaque CSRF consiste à :

* exploiter une session utilisateur active
* envoyer une requête à son insu
* faire exécuter une action non souhaitée

Exemple :

* modification de mot de passe
* validation d’une action sensible

L’application pense que la requête est légitime car l’utilisateur est authentifié.

---

### Origine de la faille

La faille apparaît lorsque :

* aucune vérification supplémentaire n’est faite sur les requêtes
* la session utilisateur suffit à valider l’action

---

### Protection par token

La protection repose sur un jeton (token) :

* un token unique est généré côté serveur
* il est envoyé dans le formulaire
* il est vérifié lors de la requête

Principe :

* si le token reçu correspond à celui stocké en session → requête valide
* sinon → requête rejetée

Cette méthode est utilisée dans les applications Web sécurisées .

---

### Vérification côté serveur

Le serveur doit :

* vérifier la présence du token
* comparer avec celui en session
* refuser la requête si invalide

Objectif : s’assurer que la requête vient bien de l’application.

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* expliquer le fonctionnement d’une attaque CSRF
* comprendre le rôle du token
* analyser un code mettant en place cette protection
* expliquer pourquoi cette protection est efficace

Ces notions sont évaluées dans les questions de sécurité Web .

---

## Réflexe à retenir

VÉRIFIER LA REQUÊTE, PAS SEULEMENT L’UTILISATEUR

---

## À retenir

Être authentifié ne suffit pas : chaque action sensible doit être sécurisée individuellement.
