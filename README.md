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

## Configuration du fichier `docker-compose.yml`

```yaml
version: '3.8'

services:
  db:
    image: mysql:5.7
    container_name: mysql
    volumes:
      - db_data:/var/lib/mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: example
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress

  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    container_name: wordpress
    ports:
      - "8000:80"
    restart: always
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress
    volumes:
      - wordpress_data:/var/www/html

volumes:
  db_data:
  wordpress_data:
