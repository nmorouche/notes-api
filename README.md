# notes-api NodeJS

Ce projet est un projet scolaire et le but est de créer une API de gestion de notes.
Vous aurez donc accès ici, à une application hébergé sur Heroku afin d'effectuer les différents tests (ou bien cloner le repo et le tester en local).
Application : https://esgi-note-api2.herokuapp.com/

# Comment utiliser
## Authentification :

Tout d'abord vous allez avoir besoin d'un compte, pour cela vous devez faire une requête vers un endpoint particulier.
En effet cela sera /signup :

```
https://esgi-note-api2.herokuapp.com/signup
```

* Créer un utilisateur :

  ```
  $ curl -X POST --header "Content-Type: application/json" --data "{\"username\":\"YOUR_USERNAME\", \"password\":\"YOUR_PASSWORD\"}" https://esgi-note-api2.herokuapp.com/signup
  ```
  Remplacer "YOUR_USERNAME" & "YOUR_PASSWORD" par votre nom d'utilisateur ainsi que votre mot de passe.
  <br>
  <br>
Par la suite pour se connecter cela se fera sur /signin :

```
https://esgi-note-api2.herokuapp.com/signin
```

* Se connecter :

  ```
  $ curl -X POST --header "Content-Type: application/json" --data "{\"username\":\"YOUR_USERNAME\", \"password\":\"YOUR_PASSWORD\"}" https://esgi-note-api2.herokuapp.com/signin
  ```
  Remplacer "YOUR_USERNAME" & "YOUR_PASSWORD" par votre nom d'utilisateur ainsi que votre mot de passe.

## Création, récupération, modification et suppression de note :
Après vous être authentifié, vous recevrez un token qu'il faudra placer dans le header (x-access-token) afin d'avoir accès au differentes fonctionnalités des notes (Création, récupération, modification et suppression)
En effet cela sera /notes :

* Créer une note :
  Afin de créer une note nous allons faire un PUT :
  ```
  $curl -X PUT --header "Content-Type: application/json" -H "x-access-token: YOUR_TOKEN" --data "{\"content\":\"Note content\"}" https://esgi-note-api2.herokuapp.com/notes
  ```
  Remplacer token par votre Token reçu lors du signup ou du signin.
  <br>
  <br>
Par la suite pour récupérer l'ensemble de vos notes il va falloit faire un GET :

* Récupération des notes de l'utilisateur :

  ```
  $ curl -X GET --header "Content-Type: application/json" -H "x-access-token: YOUR_TOKEN" https://esgi-note-api2.herokuapp.com/notes
  ```
  Remplacer token par votre Token reçu lors du signup ou du signin.
  <br>
  <br>
  * Modification d'une note :

  ```
  $ curl -X PATCH --header "Content-Type: application/json" -H "x-access-token: YOUR_TOKEN" --data "{\"content\":\"Note content\"}" https://esgi-note-api2.herokuapp.com/notes/(id_note)
  ```
  Remplacer token par votre Token reçu lors du signup ou du signin & (id_note) par l'id de la note à modifier.
  <br>
  <br>
  * Suppression d'une note :

  ```
  $ curl -X DELETE --header "Content-Type: application/json" -H "x-access-token: YOUR_TOKEN" https://esgi-note-api2.herokuapp.com/notes/(id_note)
  ```
  Remplacer token par votre Token reçu lors du signup ou du signin & (id_note) par l'id de la note à supprimer.
  <br>
  <br>
  
  ***Il est important à savoir que seules vos notes seront disponible pour les récupérations, modifications ou suppressions***

# Installation & Déploiement

Assurez-vous d'avoir installé Node.JS avant de commencer.

```
$ npm install
```
Vous aurez besoin aussi d'une base de données MongoDB qu'il vous faudra installer ([Lien utile](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/))
Une fois ces deux éléments installer vous n'aurez plus qu'a lancer la commande suivant :
```
$ npm start
```

# Sources
## Créer avec

* [Express](https://expressjs.com/en/api.html) - The web framework used
* [JsonWebToken](https://github.com/auth0/node-jsonwebtoken) - Token authentification
* [MD5](https://www.npmjs.com/package/md5) - MD5 password encryption

## Versions

Pour les versions disponibles, se référer [tags on this repository](https://github.com/nmorouche/notes-api/tags). 

## Auteurs

* **Nassim MOROUCHE** - [Nassim](https://github.com/nmorouche)
