![SQL](https://img.shields.io/badge/SQL-%23000.svg?style=for-the-badge&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-%23336791.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![GitHub CLI](https://img.shields.io/badge/GitHub%20CLI-%23181717.svg?style=for-the-badge&logo=github&logoColor=white)
![Lazygit](https://img.shields.io/badge/Lazygit-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![Gitflow](https://img.shields.io/badge/Gitflow-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

# Table of Contents

- [English Documentation](#english-documentation)
  - [Introduction](#introduction)
  - [Management Rules](#management-rules)
    - [User Management](#user-management)
    - [Product Management](#product-management)
    - [Order Management](#order-management)
  - [MERISE Acronym](#merise-acronym)
  - [Roles and Permissions (RBAC)](#roles-and-permissions-rbac)
  - [Installation](#installation)
    - [Prerequisites](#prerequisites)
    - [Installation Steps](#installation-steps)
  - [Configuration](#configuration)
    - [Row-Level Security (RLS)](#row-level-security-rls)
  - [Usage](#usage)
    - [Data Access](#data-access)
    - [Password Security](#password-security)
  - [Conclusion](#conclusion)
- [Documentation en Français](#documentation-en-français)
  - [Introduction](#introduction-1)
  - [Règles de Gestion](#règles-de-gestion)
    - [Gestion des Utilisateurs](#gestion-des-utilisateurs)
    - [Gestion des Produits](#gestion-des-produits)
    - [Gestion des Commandes](#gestion-des-commandes)
  - [Acronyme MERISE](#acronyme-merise)
  - [Rôles et Permissions (RBAC)](#rôles-et-permissions-rbac)
  - [Installation](#installation-1)
    - [Prérequis](#prérequis)
    - [Étapes d'Installation](#étapes-dinstallation)
  - [Configuration](#configuration-1)
    - [Sécurité au Niveau des Lignes (RLS)](#sécurité-au-niveau-des-lignes-rls)
  - [Utilisation](#utilisation)
    - [Accès aux Données](#accès-aux-données)
    - [Sécurité des Mots de Passe](#sécurité-des-mots-de-passe)
  - [Conclusion](#conclusion-1)

# "AuBonDeal" Database Documentation

## Introduction

The "AuBonDeal" database is a crucial component of the "AuBonDeal" e-commerce application. This database stores all the necessary information for the application's operation, including user data, product data, and order data. This documentation will guide you through the installation, configuration, and use of this database.

## Management Rules

### User Management
- Each user must have a unique username.
- User passwords are stored securely using hash functions.
- Users can be activated or deactivated.

### Product Management
- Each product must have a unique name.
- The price of a product cannot be null or negative.
- The available quantity of a product cannot be negative.

### Order Management
- Each order is associated with a user.
- The total cost of an order cannot be null or negative.
- The total quantity of products in an order cannot be negative.

## MERISE Acronym

The acronym "MERISE" comes from the field of information systems modeling. It is defined as follows:

- **MERISE**: Methodology for the Study and Development of Computer Systems for Business.

MERISE is a widely used methodology in computer science and database development.

## Roles and Permissions (RBAC)

The "AuBonDeal" database uses a role-based access control (RBAC) model. Two main roles are defined:

- `readOnly`: This role has permission to read data.
- `writeOnly`: This role has permission to add and update data.

## Installation

### Prerequisites
Before installing the "AuBonDeal" database, ensure that the following elements are installed on your system:
- PostgreSQL: A relational database management system.
- pgcli: A command-line interface for PostgreSQL.
- The `pgcrypto` extension must be enabled in PostgreSQL for password hashing.

### Installation Steps

1. **Create a Database**: Open a terminal window and execute the following command to create a new "AuBonDeal" database (make sure PostgreSQL is running):
   ```bash
   createdb auBonDeal
   ```

2. **Import the Database Structure**: Use pgcli to connect to the "AuBonDeal" database and import the database structure from a SQL file (replace `/path/to/your/script.sql` with the path to your SQL file):
   ```bash
   pgcli -d auBonDeal -U your_user -f /path/to/your/script.sql
   ```

## Configuration

### Row-Level Security (RLS)

The database also uses row-level security (RLS) to ensure that each user accesses only their own data.

## Usage

The "AuBonDeal" database includes the following tables:

1. **`users` Table**: Stores user information, including their usernames, passwords, and activation status.

2. **`products` Table**: Contains details of available products, such as their names, descriptions, prices, and quantities.

3. **`orders` Table**: Records orders placed by users, including order details, total cost, and delivery date.

### Data Access

- Users with the `readOnly` role can view existing data.
- Users with the `writeOnly` role can add new products, update product data, and place orders.

### Password Security

User passwords are secured using hash functions to ensure confidentiality.

## Conclusion

The "AuBonDeal" database is ready for use with the eponymous e-commerce application. Follow the installation and configuration steps to prepare your environment. You can now start managing users, products, and orders securely.

# Documentation de la Base de Données "AuBonDeal"

## Introduction

La base de données "AuBonDeal" est un composant essentiel de l'application e-commerce "AuBonDeal". Cette base de données stocke toutes les informations nécessaires au fonctionnement de l'application, notamment les données des utilisateurs, des produits et des commandes. Cette documentation vous guidera à travers l'installation, la configuration et l'utilisation de cette base de données.

## Règles de Gestion

### Gestion des Utilisateurs
- Chaque utilisateur doit avoir un nom d'utilisateur unique.
- Les mots de passe des utilisateurs sont stockés de manière sécurisée à l'aide de fonctions de hachage.
- Les utilisateurs peuvent être activés ou désactivés.

### Gestion des Produits
- Chaque produit doit avoir un nom unique.
- Le prix d'un produit ne peut pas être nul ou négatif.
- La quantité disponible d'un produit ne peut pas être négative.

### Gestion des Commandes
- Chaque commande est associée à un utilisateur.
- Le coût total d'une commande ne peut pas être nul ou négatif.
- La quantité totale de produits dans une commande ne peut pas être négative.

## Acronyme MERISE

L'acronyme "MERISE" est un terme qui provient de la modélisation des systèmes d'information. Il est défini comme suit :

- **MERISE** : Méthode d'Étude et de Réalisation Informatique pour les Systèmes d'Entreprise.

MERISE est une méthodologie de modélisation des systèmes d'information largement utilisée dans le domaine de l'informatique et du développement de bases de données.

## Rôles et Permissions (RBAC)

La base de données "AuBonDeal" utilise un modèle de contrôle d'accès basé sur les rôles (RBAC). Deux rôles principaux sont définis :

- `readOnly` : Ce rôle a la permission de lire les données.
- `writeOnly` : Ce rôle a la permission d'ajouter et de mettre à jour des données.

## Installation

### Prérequis
Avant d'installer la base de données "AuBonDeal", assurez-vous d'avoir les éléments suivants installés sur votre système :
- PostgreSQL : Un système de gestion de base de données relationnelles.
- pgcli : Une interface en ligne de commande pour PostgreSQL.
- L'extension `pgcrypto` doit être activée dans PostgreSQL pour le hachage des mots de passe.

### Étapes d'Installation

1. **Créez une Base de Données** : Ouvrez une fenêtre de terminal et exécutez la commande suivante pour créer une nouvelle base de données "AuBonDeal" (assurez-vous que PostgreSQL est en cours d'exécution) :
   ```bash
   createdb auBonDeal
   ```

2. **Importez la Structure de la Base de Données** : Utilisez pgcli pour vous connecter à la base de données "AuBonDeal" et importez la structure de la base de données à partir d'un fichier SQL (remplacez `/chemin/vers/votre/script.sql` par le chemin vers votre fichier SQL) :
   ```bash
   pgcli -d auBonDeal -U votre_utilisateur -f /chemin/vers/votre/script.sql
   ```

## Configuration

### Sécurité au Niveau des Lignes (RLS)

La base de données utilise également la sécurité au niveau des lignes (Row Level Security - RLS) pour garantir que chaque utilisateur n'accède qu'à ses propres données.

## Utilisation

La base de données "AuBonDeal" comprend les tables suivantes :

1. **Table `users`** : Stocke les informations des utilisateurs, y

 compris leurs noms d'utilisateur, mots de passe et état d'activation.

2. **Table `products`** : Contient les détails des produits disponibles, tels que leurs noms, descriptions, prix et quantités.

3. **Table `orders`** : Enregistre les commandes passées par les utilisateurs, y compris les détails de la commande, le total et la date de livraison.

### Accès aux Données

- Les utilisateurs avec le rôle `readOnly` peuvent consulter les données existantes.
- Les utilisateurs avec le rôle `writeOnly` peuvent ajouter de nouveaux produits, mettre à jour les données des produits et passer des commandes.

### Sécurité des Mots de Passe

Les mots de passe des utilisateurs sont sécurisés à l'aide de fonctions de hachage pour garantir la confidentialité.

## Conclusion

La base de données "AuBonDeal" est prête à être utilisée avec l'application e-commerce éponyme. Suivez les étapes d'installation et de configuration pour préparer votre environnement. Vous pouvez maintenant commencer à gérer les utilisateurs, les produits et les commandes de manière sécurisée.