# Déploiement WordPress avec Docker Compose

**Auteur** : Amir EL HADRI  
**Date** : 16/02/2025

## Description
Ce projet décrit le déploiement d'une instance WordPress couplée à une base de données MySQL à l'aide de Docker Compose. L'objectif est de créer un environnement rapide, reproductible et persistant pour WordPress.

## Étapes suivies

### 1. Création de l'environnement
- Création d'un répertoire et du fichier `docker-compose.yml`.
- Définition des services `WordPress` et `MySQL` dans le fichier `docker-compose.yml`.

### 2. Déploiement et test
- Démarrage des services avec `docker-compose up -d`.
- Vérification du bon fonctionnement avec `docker ps`.
- Accès à WordPress via `http://localhost:8000` pour finaliser l'installation.
- Création d’une page et téléchargement d'un fichier pour tester la persistance des données.

