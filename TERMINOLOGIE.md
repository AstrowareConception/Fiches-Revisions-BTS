# Architecture & conception

**Architecture MVC** : 
Modèle d’organisation d’une application séparant les responsabilités en trois composants : Modèle (données), Vue (interface) et Contrôleur (logique de contrôle). Cette séparation permet de faciliter la maintenance, les tests et l’évolution du code.

**Modèle (MVC)** : 
Composant chargé de gérer les données et la logique métier. Il est indépendant de l’interface utilisateur et peut être réutilisé dans différents contextes.

**Vue (MVC)** : 
Composant responsable de l’affichage des données à l’utilisateur. Elle ne contient pas de logique métier et se limite à la présentation.

**Contrôleur (MVC)** : 
Composant qui reçoit les requêtes utilisateur, appelle les traitements nécessaires dans le modèle et retourne la vue appropriée. Il joue le rôle d’intermédiaire.

**Couche métier** : 
Partie de l’application contenant les règles de gestion spécifiques au domaine fonctionnel. Elle traduit les besoins métier en logique applicative.

**Couche d’accès aux données** : 
Partie chargée de communiquer avec la base de données (requêtes, persistance). Elle isole les détails techniques liés au stockage des données.

**API RESTful** : 
API respectant les principes REST : ressources identifiées par URL, utilisation des méthodes HTTP et absence d’état côté serveur. Elle est conçue pour être simple, standardisée et scalable.

**DTO (Data Transfer Object)** : 
Objet utilisé pour transporter des données entre couches ou systèmes. Il ne contient pas de logique métier et sert uniquement à structurer les échanges.

---

# Bases de données & données

**SGBD (Système de Gestion de Base de Données)** : 
Logiciel permettant de créer, manipuler et administrer des bases de données. Il garantit la cohérence, la sécurité et l’intégrité des données.

**Transaction** : 
Ensemble d’opérations exécutées de manière atomique : soit toutes réussissent, soit aucune n’est appliquée. Cela garantit la cohérence des données même en cas d’erreur.

**Index** : 
Structure de données permettant d’accélérer l’accès aux enregistrements d’une table. Il améliore les performances des requêtes au prix d’un coût en écriture.

**Clé primaire** : 
Attribut unique identifiant chaque enregistrement d’une table. Elle ne peut pas contenir de valeur nulle.

**Clé étrangère** : 
Attribut reliant une table à une autre en référencant une clé primaire. Elle garantit la cohérence des relations entre tables.

**Normalisation** : 
Processus d’organisation des données visant à éliminer les redondances et anomalies. Elle améliore la cohérence et la maintenabilité des bases.

**ORM (Object-Relational Mapping)** : 
Technique permettant de manipuler une base relationnelle via des objets. Elle simplifie le développement en évitant d’écrire directement du SQL.

**NoSQL** : 
Type de base de données non relationnelle adaptée aux données volumineuses ou peu structurées. Elle privilégie la performance et la flexibilité.

**Requête préparée** : 
Requête SQL paramétrée compilée à l’avance. Elle protège contre les injections SQL et améliore les performances.

**Jointure (JOIN)** : 
Opération SQL permettant de combiner des données provenant de plusieurs tables. Elle est essentielle pour exploiter des modèles relationnels.

**Vue (SQL)** : 
Table virtuelle basée sur une requête SQL. Elle permet de simplifier des requêtes complexes ou de restreindre l’accès aux données.

**Trigger** : 
Procédure exécutée automatiquement lors d’un événement sur une table (INSERT, UPDATE, DELETE). Elle permet d’automatiser certains traitements.

**Procédure stockée** : 
Programme enregistré dans le SGBD et exécuté côté serveur. Elle permet de centraliser des traitements et d’améliorer les performances.

**Cardinalité** : 
Relation quantitative entre deux entités (1-1, 1-N, N-N). Elle décrit le nombre d’occurrences possibles entre deux tables.

**Intégrité référentielle** : 
Règle garantissant que les relations entre tables restent cohérentes. Elle empêche les références invalides.

**Schéma de base de données** : 
Structure globale d’une base de données (tables, colonnes, relations). Il représente le modèle logique des données.

---

# Web & API

**REST** : 
Style d’architecture basé sur des ressources accessibles via HTTP. Il favorise la simplicité, la standardisation et l’interopérabilité.

**Endpoint** : 
URL exposée par une API permettant d’accéder à une ressource ou d’exécuter une action. Chaque endpoint correspond à une fonctionnalité précise.

**Middleware** : 
Composant intermédiaire exécuté lors du traitement d’une requête. Il permet d’ajouter des traitements transverses (authentification, logs, etc.).

**Requête HTTP** : 
Message envoyé par un client vers un serveur pour demander une ressource. Elle contient une méthode, des headers et éventuellement un corps.

**Réponse HTTP** : 
Message retourné par le serveur contenant le résultat de la requête. Elle inclut un code de statut, des headers et éventuellement des données.

**Méthodes HTTP** : 
Verbes définissant l’action sur une ressource : GET (lecture), POST (création), PUT (mise à jour), DELETE (suppression). Elles structurent les API REST.

**Code HTTP** : 
Code numérique indiquant le résultat d’une requête (ex : 200 succès, 404 non trouvé, 500 erreur serveur). Il permet au client d’interpréter la réponse.

**Header HTTP** : 
Informations supplémentaires envoyées avec une requête ou une réponse. Ils décrivent le contexte (type de contenu, authentification, etc.).

**Payload** : 
Données transportées dans le corps d’une requête ou d’une réponse. Il contient les informations utiles échangées entre client et serveur.

**Encodage (UTF-8)** : 
Format de représentation des caractères permettant de gérer la majorité des langues. Il garantit la compatibilité internationale.

---

# Sécurité

**JWT (JSON Web Token)** : 
Jeton sécurisé contenant des informations d’authentification signées. Il permet de gérer des sessions sans stockage côté serveur.

**CORS** : 
Mécanisme de sécurité contrôlant les requêtes entre domaines différents. Il empêche certains accès non autorisés côté navigateur.

**Session** : 
Mécanisme de stockage temporaire des données utilisateur côté serveur. Il permet de maintenir l’état entre plusieurs requêtes.

**Cookie** : 
Donnée stockée côté client envoyée automatiquement au serveur. Il est utilisé pour maintenir une session ou stocker des préférences.

**Hashage** : 
Transformation irréversible d’une donnée en empreinte. Utilisé principalement pour stocker des mots de passe de manière sécurisée.

**Salage (salt)** : 
Ajout d’une valeur aléatoire avant hashage. Cela empêche l’utilisation de tables de correspondance (rainbow tables).

**Pare-feu (Firewall)** : 
Système filtrant les communications réseau selon des règles définies. Il protège contre les accès non autorisés.

**Faille CSRF** : 
Attaque exploitant la confiance d’un site envers un utilisateur authentifié. Elle permet d’exécuter des actions à son insu.

**OWASP** : 
Organisation qui recense et documente les principales vulnérabilités web. Elle sert de référence en sécurité applicative.

**Principe du moindre privilège** : 
Principe consistant à accorder uniquement les droits nécessaires. Il limite l’impact d’une compromission.

**Authentification** : 
Processus de vérification de l’identité d’un utilisateur. Exemple : login/mot de passe.

**Autorisation** : 
Processus de vérification des droits d’un utilisateur authentifié. Elle détermine ce qu’il peut faire.

**Authentification forte** : 
Authentification utilisant plusieurs facteurs (mot de passe + code). Elle renforce la sécurité.

**Gestion des rôles (RBAC)** : 
Système d’attribution des droits basé sur des rôles. Il simplifie la gestion des permissions.

**Sanitization** : 
Nettoyage des données d’entrée pour éviter les injections. Elle est essentielle pour la sécurité des applications.

**Validation des données** : 
Vérification que les données respectent un format attendu. Elle évite les erreurs et attaques.

**HTTPS** : 
Version sécurisée de HTTP utilisant le chiffrement TLS. Elle garantit la confidentialité et l’intégrité des échanges.

---

# Développement & qualité logicielle

**Framework** : 
Structure logicielle imposant une organisation et fournissant des outils. Il accélère le développement et standardise les pratiques.

**Bibliothèque (librairie)** : 
Ensemble de fonctions réutilisables. Contrairement à un framework, elle est appelée librement par le développeur.

**Tests unitaires** : 
Tests vérifiant une unité de code isolée. Ils permettent de valider le bon fonctionnement d’une fonction ou méthode.

**Tests d’intégration** : 
Tests vérifiant l’interaction entre plusieurs composants. Ils assurent que les modules fonctionnent ensemble.

**Tests fonctionnels** : 
Tests validant le comportement global de l’application. Ils vérifient la conformité aux besoins.

**Debug** : 
Processus de recherche et correction d’erreurs dans le code. Il est essentiel pour garantir la stabilité.

**Compilation** : 
Transformation du code source en code exécutable. Elle est utilisée dans les langages compilés.

**Interpréteur** : 
Programme exécutant directement le code source. Il permet une exécution immédiate sans compilation.

**Versioning** : 
Gestion des versions du code source dans le temps. Il permet de suivre les modifications et collaborer.

**Refactoring** : 
Amélioration du code sans modifier son comportement. Il vise à améliorer la lisibilité et la maintenabilité.

**Dette technique** : 
Accumulation de compromis techniques dégradant la qualité du code. Elle rend les évolutions plus coûteuses.

**Convention de nommage** : 
Règles définissant la manière de nommer variables et fonctions. Elles améliorent la lisibilité et la cohérence.

**Documentation technique** : 
Documentation destinée aux développeurs. Elle décrit le fonctionnement interne du système.

**Documentation utilisateur** : 
Documentation destinée aux utilisateurs finaux. Elle explique l’utilisation de l’application.

**Logs (journalisation)** : 
Enregistrement des événements d’une application. Ils sont utilisés pour le suivi et le diagnostic.

**Gestion des erreurs (exceptions)** : 
Mécanisme permettant de gérer les erreurs à l’exécution. Il évite les plantages et améliore la robustesse.

---

# Projet & environnement professionnel

**Cahier des charges** : 
Document décrivant les besoins, contraintes et objectifs d’un projet. Il sert de référence contractuelle.

**Spécifications fonctionnelles** : 
Description des fonctionnalités attendues du point de vue utilisateur. Elles traduisent le besoin sans technique.

**Spécifications techniques** : 
Description des solutions techniques retenues pour répondre au besoin. Elles guident le développement.

**Recette (tests d’acceptation)** : 
Validation finale de l’application par rapport aux exigences. Elle permet de vérifier que le produit est conforme.
