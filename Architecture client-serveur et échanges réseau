# FICHE 26 — Architecture client / serveur et échanges réseau

---

## Problématique

Comment une application communique-t-elle avec une base de données ou un serveur distant ?

---

## Bonnes pratiques essentielles

### Principe client / serveur

Une architecture client / serveur repose sur deux éléments :

* le client :
  interface utilisée par l’utilisateur ;

* le serveur :
  machine qui fournit des services ou des données.

Exemple :

* navigateur web ↔ serveur web ;
* application mobile ↔ API.

---

### Fonctionnement général

1. Le client envoie une requête ;
2. Le serveur traite la demande ;
3. Le serveur renvoie une réponse.

Exemple :

```text id="ujdc4i"
Client → Requête HTTP → Serveur
Serveur → Réponse → Client
```

---

### Requête HTTP

Une requête HTTP contient :

* une méthode (GET, POST…) ;
* une URL ;
* éventuellement des données.

Exemple :

```text id="d9l7q5"
GET /api/produits
```

---

### Réponse du serveur

Le serveur renvoie :

* un code HTTP ;
* des données ;
* parfois du JSON.

Exemple :

* 200 : succès ;
* 404 : ressource introuvable ;
* 500 : erreur serveur.

---

### Architecture 3 tiers

Très utilisée en développement web.

Elle sépare :

* présentation (interface) ;
* logique métier ;
* données.

Exemple :

```text id="dn9nlm"
Client → Serveur applicatif → Base de données
```

Objectif :

* améliorer la maintenance ;
* sécuriser les traitements ;
* séparer les responsabilités.

---

### Communication avec la base de données

Le serveur :

* reçoit la requête du client ;
* interroge la base ;
* renvoie les résultats.

Le client ne communique généralement pas directement avec la base.

---

### Sécurisation des échanges

Les échanges doivent être protégés :

* HTTPS ;
* authentification ;
* contrôle des accès ;
* validation des données.

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* expliquer une architecture client / serveur ;
* distinguer client, serveur et base de données ;
* comprendre le fonctionnement d’une requête HTTP ;
* expliquer le rôle d’un serveur applicatif.

Ces notions sont présentes dans tous les projets web et API du BTS SLAM.

---

## Réflexe à retenir

DEMANDER → TRAITER → RÉPONDRE

---

## À retenir

Dans une architecture client / serveur, le client demande un service et le serveur traite la requête avant de renvoyer une réponse.
