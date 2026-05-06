# Fiche de révision 21 — Requêtes préparées et protection contre les injections SQL

## BTS SIO SLAM — Cybersécurité et développement sécurisé

---

# 1. Pourquoi ce sujet est important au BTS SIO

Les injections SQL font partie des failles de sécurité les plus connues et les plus dangereuses dans les applications web.

Le BTS SIO attend qu’un étudiant SLAM sache :

* identifier une injection SQL ;
* expliquer son fonctionnement ;
* sécuriser les requêtes SQL ;
* utiliser correctement PDO et les requêtes préparées ;
* distinguer un code vulnérable d’un code sécurisé ;
* comprendre les enjeux RGPD et cybersécurité liés aux bases de données.

Ce sujet tombe très régulièrement :

* dans les sujets de cybersécurité ;
* dans les études de code PHP ;
* dans les dossiers API ;
* dans les questions sur PDO ;
* dans les questions de maintenance corrective.

---

# 2. Rappel : rôle d’une base de données

Une base de données permet de :

* stocker des informations ;
* rechercher des données ;
* modifier des données ;
* supprimer des données ;
* gérer les relations entre les informations.

Exemple :

| Table       | Contenu              |
| ----------- | -------------------- |
| utilisateur | comptes utilisateurs |
| produit     | catalogue            |
| commande    | achats               |
| message     | messagerie           |

Les applications communiquent avec la base grâce au langage SQL.

---

# 3. Qu’est-ce qu’une injection SQL ?

Une injection SQL est une attaque consistant à injecter du code SQL malveillant dans une requête exécutée par l’application.

L’attaquant exploite un champ utilisateur mal sécurisé.

Exemple typique :

```php
$login = $_POST['login'];
$sql = "SELECT * FROM utilisateur WHERE login = '$login'";
```

Si l’utilisateur saisit :

```sql
admin' OR '1'='1
```

La requête devient :

```sql
SELECT * FROM utilisateur WHERE login = 'admin' OR '1'='1'
```

La condition devient toujours vraie.

Résultat :

* contournement de l’authentification ;
* accès illégitime ;
* fuite de données.

---

# 4. Conséquences possibles d’une injection SQL

Une injection SQL peut permettre :

## Vol de données

Exemple :

* mots de passe ;
* données bancaires ;
* données personnelles ;
* informations médicales.

---

## Modification de données

Exemple :

```sql
UPDATE utilisateur SET role='admin'
```

---

## Suppression de données

Exemple :

```sql
DROP TABLE utilisateur
```

---

## Contournement d’authentification

Très fréquent dans les sujets BTS.

---

## Escalade de privilèges

L’attaquant devient administrateur.

---

# 5. Pourquoi ces failles existent-elles ?

Les injections SQL apparaissent lorsque :

* les données utilisateur sont insérées directement dans la requête SQL ;
* aucune séparation n’existe entre code SQL et données ;
* les entrées ne sont pas correctement sécurisées.

Exemple vulnérable :

```php
$sql = "SELECT * FROM utilisateur WHERE email = '$email'";
```

Le problème vient de la concaténation.

---

# 6. Principe des requêtes préparées

Une requête préparée sépare :

* la structure SQL ;
* les données utilisateur.

Le moteur SQL sait donc distinguer :

* ce qui est du SQL ;
* ce qui est une simple valeur.

Même si l’utilisateur saisit du code SQL malveillant, celui-ci sera traité comme du texte.

---

# 7. Fonctionnement général des requêtes préparées

Étapes :

## Étape 1 : préparation de la requête

```php
$sql = "SELECT * FROM utilisateur WHERE email = :email";
$stmt = $pdo->prepare($sql);
```

Le paramètre `:email` est un placeholder.

---

## Étape 2 : association de la valeur

```php
$stmt->bindParam(':email', $email);
```

---

## Étape 3 : exécution

```php
$stmt->execute();
```

---

# 8. Exemple complet sécurisé avec PDO

```php
<?php

$email = $_POST['email'];

$pdo = new PDO(
    "mysql:host=localhost;dbname=site",
    "root",
    ""
);

$sql = "SELECT * FROM utilisateur WHERE email = :email";

$stmt = $pdo->prepare($sql);

$stmt->bindParam(':email', $email, PDO::PARAM_STR);

$stmt->execute();

$resultat = $stmt->fetch(PDO::FETCH_ASSOC);

?>
```

---

# 9. Pourquoi ce code est sécurisé

Le moteur SQL reçoit :

* une requête fixe ;
* une valeur séparée.

Même si l’utilisateur saisit :

```sql
' OR '1'='1
```

Cette chaîne sera traitée comme du texte.

La requête SQL ne sera pas modifiée.

---

# 10. Les placeholders

Deux syntaxes existent.

## Placeholders nommés

```php
:email
:id
:nom
```

Exemple :

```php
SELECT * FROM utilisateur WHERE id = :id
```

---

## Placeholders anonymes

```php
?
```

Exemple :

```php
SELECT * FROM utilisateur WHERE id = ?
```

Puis :

```php
$stmt->execute([$id]);
```

---

# 11. bindParam et bindValue

## bindParam()

Lie une variable.

La valeur est lue au moment du execute().

```php
$stmt->bindParam(':id', $id);
```

---

## bindValue()

Lie directement une valeur.

```php
$stmt->bindValue(':id', 5);
```

---

# 12. Les types PDO importants

| Type            | Description |
| --------------- | ----------- |
| PDO::PARAM_STR  | chaîne      |
| PDO::PARAM_INT  | entier      |
| PDO::PARAM_BOOL | booléen     |
| PDO::PARAM_NULL | NULL        |

Exemple :

```php
$stmt->bindParam(':id', $id, PDO::PARAM_INT);
```

---

# 13. Exemple d’analyse de code type BTS

## Code vulnérable

```php
$id = $_GET['id'];
$sql = "SELECT * FROM produit WHERE id = $id";
```

---

## Pourquoi il est dangereux

L’utilisateur peut injecter du SQL.

Exemple :

```sql
1 OR 1=1
```

La requête devient :

```sql
SELECT * FROM produit WHERE id = 1 OR 1=1
```

---

## Correction attendue

```php
$id = $_GET['id'];

$sql = "SELECT * FROM produit WHERE id = :id";

$stmt = $pdo->prepare($sql);
$stmt->bindParam(':id', $id, PDO::PARAM_INT);
$stmt->execute();
```

---

# 14. Attention : htmlspecialchars ne protège PAS des injections SQL

Erreur très fréquente.

```php
htmlspecialchars()
```

sert à :

* empêcher les injections HTML ;
* éviter les attaques XSS.

Mais cette fonction ne sécurise pas SQL.

Seules les requêtes préparées protègent réellement.

---

# 15. Les autres bonnes pratiques de sécurité SQL

## Valider les données

Exemple :

* email valide ;
* entier positif ;
* date correcte.

---

## Limiter les droits SQL

Le compte SQL utilisé par l’application ne doit pas être administrateur.

Principe du moindre privilège.

---

## Journaliser les erreurs

Conserver des logs.

---

## Ne jamais afficher les erreurs SQL aux utilisateurs

Mauvais exemple :

```php
echo $e->getMessage();
```

Cela peut révéler :

* la structure de la base ;
* les tables ;
* les colonnes.

---

# 16. Injection SQL et RGPD

Une injection SQL peut entraîner :

* une violation de données personnelles ;
* une fuite d’informations ;
* une obligation de notification CNIL ;
* une responsabilité juridique.

Le développeur doit donc mettre en œuvre :

* sécurité by design ;
* protection des données ;
* contrôle des accès.

---

# 17. Cas typiques de questions d’examen

## Question classique 1

« Identifier la faille de sécurité présente dans ce code. »

Réponse attendue :

* injection SQL ;
* concaténation directe des données utilisateur.

---

## Question classique 2

« Justifier l’utilisation d’une requête préparée. »

Réponse attendue :

* séparation données/code SQL ;
* prévention des injections SQL ;
* sécurisation des accès à la base.

---

## Question classique 3

« Corriger le code. »

Il faut :

* prepare() ;
* bindParam() ou execute([]) ;
* placeholder.

---

## Question classique 4

« Expliquer pourquoi ce code n’est pas sécurisé malgré htmlspecialchars(). »

Réponse :

* htmlspecialchars protège contre XSS ;
* pas contre SQL.

---

# 18. Différence entre XSS et injection SQL

| XSS                    | Injection SQL             |
| ---------------------- | ------------------------- |
| attaque navigateur     | attaque base de données   |
| HTML/JavaScript        | SQL                       |
| cible utilisateur      | cible serveur             |
| htmlspecialchars utile | requêtes préparées utiles |

---

# 19. Ce qu’il faut absolument savoir refaire

## À maîtriser parfaitement

* écrire une requête préparée PDO ;
* expliquer prepare / execute ;
* expliquer bindParam ;
* détecter un code vulnérable ;
* corriger une injection SQL ;
* distinguer XSS et SQL ;
* expliquer le principe du moindre privilège.

---

# 20. Résumé ultra rapide

## Injection SQL

Attaque consistant à injecter du SQL malveillant.

---

## Cause

Concaténation directe des entrées utilisateur.

---

## Protection principale

Requêtes préparées.

---

## Fonctions importantes

```php
prepare()
bindParam()
execute()
fetch()
```

---

## Bonnes pratiques

* validation des données ;
* droits SQL limités ;
* logs ;
* pas d’erreur SQL affichée.

---

# 21. Mini exercice de révision

## Code donné

```php
$login = $_POST['login'];
$password = $_POST['password'];

$sql = "SELECT * FROM utilisateur
WHERE login = '$login'
AND password = '$password'";
```

---

## Questions

1. Identifier la faille.
2. Expliquer le risque.
3. Réécrire le code correctement.

---

# 22. Correction attendue

```php
$login = $_POST['login'];
$password = $_POST['password'];

$sql = "SELECT * FROM utilisateur
WHERE login = :login
AND password = :password";

$stmt = $pdo->prepare($sql);

$stmt->bindParam(':login', $login);
$stmt->bindParam(':password', $password);

$stmt->execute();
```

---

# 23. Pièges fréquents au BTS

## Piège 1

Confondre XSS et injection SQL.

---

## Piège 2

Penser que FILTER_SANITIZE_STRING suffit.

Faux.

---

## Piège 3

Oublier les types PDO.

---

## Piège 4

Concaténer une variable dans la requête malgré prepare().

Mauvais exemple :

```php
$sql = "SELECT * FROM produit WHERE id = $id";
$stmt = $pdo->prepare($sql);
```

La faille existe toujours.

---

# 24. Vocabulaire à connaître

| Terme            | Définition                           |
| ---------------- | ------------------------------------ |
| Injection SQL    | attaque injectant du SQL malveillant |
| Requête préparée | requête SQL séparant code et données |
| Placeholder      | paramètre dans une requête           |
| PDO              | interface PHP d’accès aux bases      |
| bindParam        | liaison d’une variable SQL           |
| XSS              | injection JavaScript/HTML            |
| DAO              | classe d’accès aux données           |

---

# 25. Conclusion

Les requêtes préparées constituent aujourd’hui une règle fondamentale du développement sécurisé.

Dans le référentiel BTS SIO SLAM, elles sont directement liées :

* à la cybersécurité ;
* à la protection des données ;
* au développement web ;
* aux API ;
* à la maintenance applicative.

Un étudiant doit être capable :

* d’identifier immédiatement une injection SQL ;
* d’expliquer précisément le risque ;
* de corriger le code avec PDO ;
* de justifier techniquement les protections mises en place.
