# Java Chat — Client / Serveur

Application de chat en ligne de commande, basée sur des sockets TCP. Un serveur
accepte plusieurs clients simultanés ; tout message envoyé par un client est
diffusé aux autres participants connectés (broadcast). Un historique récent des
échanges est conservé côté serveur et transmis aux nouveaux arrivants.

## Raison d'être

Ce projet sert de base de travail. Vous héritez d'une application fonctionnelle,
à faire évoluer selon les consignes des itérations. Il n'a pas vocation à être
réécrit de zéro : l'objectif est de partir de l'existant.

## Prérequis

- JDK 11 ou supérieur
- Le wrapper Gradle fourni (`gradlew` / `gradlew.bat`) — aucune installation
  globale de Gradle nécessaire

## Structure

Le dépôt contient deux projets Gradle indépendants :

- `Server/` — le serveur de chat (point d'entrée `org.example.Main`)
- `Client/` — le client de chat (point d'entrée `org.example.Main`)

## Compilation

Dans chaque projet :

```bash
cd Server && ./gradlew build
cd Client && ./gradlew build
```

Sous Windows, remplacer `./gradlew` par `gradlew.bat`.

## Lancement

Démarrer le serveur en premier, puis un ou plusieurs clients (idéalement au
moins deux pour observer le broadcast). Le plus simple est d'ouvrir chaque
projet dans votre IDE et d'exécuter sa classe `Main`.

Par défaut :

- le serveur écoute sur le port `12345`
- le client se connecte sur `localhost:12345`

## Utilisation

1. À la connexion, le client saisit un nom.
2. Tout texte saisi est envoyé au serveur et diffusé aux autres clients.
3. Fermer le client met fin à la session.
