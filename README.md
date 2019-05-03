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

## Création, modification et suppression de note :
Tout d'abord vous allez avoir besoin d'un compte, pour cela vous devez faire une requête vers un endpoint particulier.
En effet cela sera /notes/ :

```
https://esgi-note-api2.herokuapp.com/signup
```

* Créer un utilisateur :

  ```
  $ curl -X POST --header "Content-Type: application/json" -H "x-access-token: token" --data "{\"username\":\"YOUR_USERNAME\", \"password\":\"YOUR_PASSWORD\"}" https://esgi-note-api2.herokuapp.com/signup
  ```
  Remplacer token par votre Token reçu lors du signup ou du signin.
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

# Installation

Assurez-vous d'avoir installé Node.JS avant de commencer.

```
$ npm install
```

## Déploiement

Afin de le déployer en local sur une machine modifier la variable url par votre localhost par exemple :
```
const url = "http://localhost:27017/mydatabase";
```

## Créer avec

* [Express](https://expressjs.com/en/api.html) - The web framework used

## Versions

Pour les versions disponibles, se référer [tags on this repository](https://github.com/nmorouche/nodeJS1/tags). 

## Auteurs

* **Nassim MOROUCHE** - [Nassim](https://github.com/nmorouche)
