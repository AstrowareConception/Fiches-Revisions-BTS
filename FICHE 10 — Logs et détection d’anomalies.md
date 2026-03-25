# FICHE 10 — Logs et détection d’anomalies

---

## Problématique

Comment utiliser les fichiers de journalisation pour détecter des comportements anormaux ou des attaques ?

---

## Bonnes pratiques essentielles

### Rôle des logs

Les logs (fichiers de journalisation) permettent de :

* enregistrer les événements d’une application
* suivre les actions des utilisateurs
* détecter des erreurs ou incidents

Objectif : analyser le comportement du système.

---

### Types d’événements

Un log peut contenir :

* connexions réussies
* échecs de connexion
* erreurs système
* actions sensibles

Niveaux fréquents :

* INFO / NOTICE : information normale
* WARNING : comportement suspect
* ERROR : erreur critique

---

### Détection d’anomalies

Une anomalie se repère par :

* répétition d’échecs (ex : connexions multiples)
* comportement inhabituel
* enchaînement rapide d’actions

Exemple :

* plusieurs tentatives de connexion échouées en quelques secondes

---

### Analyse des logs

L’analyse consiste à :

* identifier les événements importants
* repérer les comportements suspects
* formuler une hypothèse

Objectif : comprendre l’origine d’un incident.

---

## Ce qu’il faut savoir pour le BTS

L’étudiant doit être capable de :

* lire un extrait de logs
* identifier les événements présents
* repérer une anomalie
* proposer une explication claire

Ces compétences sont évaluées dans les questions d’analyse de journalisation .

---

## Réflexe à retenir

OBSERVER → IDENTIFIER → EXPLIQUER

---

## À retenir

Les logs sont un outil essentiel pour détecter et comprendre les incidents de sécurité.
