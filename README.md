# Tritou Boards

Plateforme de gestion de projets & équipes (type Jira / Trello / Asana light) en Java (Spring Boot) + Angular.

## Fonctionnalités technique de l'application:

- Backend REST propre et structuré
- Front Angular moderne (state, composants, services)
- Authentification / sécurité
- Relations complexes entre entités
- Pagination, filtres, rôles, permissions
- Architecture proche du monde pro

## Architecture générale

### Backend – **Spring Boot**

- API REST
- Base de données : PostgreSQL ou MySQL
- JPA / Hibernate
- Spring Security + JWT
- Validation, exceptions globales
- Tests unitaires (JUnit + Mockito)

### Frontend – **Angular**

- Angular
- Angular Material ou PrimeNG (a voir)
- Lazy loading
- Guards (auth / rôles)
- Services + Observables
- Formulaires réactifs

## Fonctionnalités principales

### Utilisateurs & rôles

- Inscription / connexion
- Rôles : `ADMIN`, `MANAGER`, `MEMBER`
- Gestion des permissions (Spring Security + Guards Angular)

### Projets

- CRUD projet
- Un projet a :
  - un manager
  - plusieurs membres
  - plusieurs tâches

### Tâches

- CRUD tâches
- Statuts : `TODO`, `IN_PROGRESS`, `DONE`
- Priorité
- Deadline
- Assignation à un utilisateur
- Commentaires sur une tâche

### Recherche & filtres

- Filtrer par statut, priorité, date
- Pagination côté backend

## Modèle de données

```
User
- id
- email
- password
- role

Project
- id
- name
- description
- manager
- members

Task
- id
- title
- description
- status
- priority
- dueDate
- project
- assignedUser
```

## Sécurité

- Auth JWT
- Refresh token (bonus)
- Protection des endpoints par rôle
- Guards Angular (`canActivate`)
- Interceptors HTTP Angular (token automatique)

## Bonus

### Notifications

- WebSocket (Spring + Angular)
- Notification quand une tâche est assignée

### Dashboard

- Graphiques (tâches par statut, par projet)
- Charts Angular

### Upload de fichiers

- Pièces jointes sur une tâche
- Stockage local ou S3-like (aws)

### DevOps

- Docker (backend + DB)
- Docker Compose
- Mise en production (docker)
- Kubernetes (des services simple)

## Initialiser le projet Java Spring Boot

[start.spring.io](https://start.spring.io/#!type=maven-project&language=java&platformVersion=4.0.2&packaging=jar&configurationFileFormat=properties&jvmVersion=21&groupId=com.example&artifactId=demo&name=backend&description=Backend%20app%20of%20tritou-boards&packageName=com.example.demo&dependencies=web,data-jpa,validation,postgresql,h2,lombok,devtools,security)

## Intialiser le projet Angular

### Installer les dépendances

```sh
npm install -g @angular/cli
```

Créer le projet Angular:

```sh
ng new <project-name>
```
