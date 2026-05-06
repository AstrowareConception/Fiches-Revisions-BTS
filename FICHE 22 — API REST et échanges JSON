# FICHE 22 — API REST et échanges JSON

---

## Problématique

Comment permettre à plusieurs applications de communiquer entre elles de manière standardisée et sécurisée ?

---

## Bonnes pratiques essentielles

### Principe d’une API

Une API (Application Programming Interface) permet à une application :

* d’envoyer des données ;
* de recevoir des données ;
* d’utiliser des fonctionnalités distantes.

Exemple :

* application mobile ↔ serveur web ;
* site e-commerce ↔ service de paiement.

---

### Principe REST

Une API REST repose sur :

* des URL représentant des ressources ;
* des méthodes HTTP ;
* des échanges généralement en JSON.

Exemple :

```text id="s1jk6q"
GET /api/utilisateurs
```

---

### Méthodes HTTP importantes

| Méthode | Rôle                  |
| ------- | --------------------- |
| GET     | récupérer des données |
| POST    | créer une donnée      |
| PUT     | modifier une donnée   |
| DELETE  | supprimer une donnée  |

---

### Format JSON

Le JSON est utilisé pour échanger des données structurées.

Exemple :

```json
{
  "id": 1,
  "nom": "Dupont",
  "email": "dupont@mail.fr"
}
```

Avantages :

* léger ;
* lisible ;
* compatible avec la plupart des langages.

---

### Structure d’une API REST

Une API doit :

* avoir des routes claires ;
* retourner des réponses cohérentes ;
* utiliser les bons codes HTTP.

Exemples :

| Code | Signification         |
| ---- | --------------------- |
| 200  | succès                |
| 201  | création réussie      |
| 400  | requête invalide      |
| 401  | non authentifié       |
| 403  | accès interdit        |
| 404  | ressource introuvable |
| 500  | erreur serveur        |

---

### Sécurisation des API

Une API doit :

* vérifier l’identité des utilisateurs ;
* utiliser HTTPS ;
* contrôler les droits d’accès ;
* protéger les données échangées.

---

### Authentification par token

Après connexion :

* le serveur génère un token ;
* le client l’envoie à chaque requête.

Objectif :

* éviter d’envoyer le mot de passe en permanence.

---

### JWT (JSON Web Token)

Un JWT contient :

* des informations utilisateur ;
* une signature de sécurité.

Avantages :

* authentification simple ;
* API stateless ;
* très utilisé dans les applications modernes.

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* expliquer le rôle d’une API REST ;
* distinguer les méthodes HTTP ;
* lire et produire du JSON ;
* comprendre le fonctionnement d’un token ;
* sécuriser les échanges entre applications.

Ces notions sont de plus en plus présentes dans les sujets SLAM et dans les projets E5.

---

## Réflexe à retenir

RECEVOIR → TRAITER → RÉPONDRE

---

## À retenir

Une API REST permet à des applications de communiquer de manière standardisée grâce au protocole HTTP et au format JSON.
