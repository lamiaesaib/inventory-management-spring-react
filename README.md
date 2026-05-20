# 📦 Système de Gestion d'Inventaire — Spring Boot & React

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-green)
![React](https://img.shields.io/badge/React-18-blue)
![H2](https://img.shields.io/badge/Database-H2-lightgrey)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Description du Projet

Ce projet est une application web **Full-Stack** de gestion d'inventaire
développée dans le cadre du module de développement backend avancé.

L'application repose sur une architecture moderne et découplée :
- Le **Backend** expose une API REST sécurisée via **Spring Boot**.
- Le **Frontend** consomme cette API et affiche les données via **React JS**.
- La **Base de données H2** stocke les informations de manière relationnelle.

---

## ✅ Fonctionnalités

- 📋 Affichage de la liste complète des produits en stock
- 🔍 Consultation des détails (nom, prix, quantité)
- 🗂️ Gestion des catégories de produits
- 🏭 Gestion des fournisseurs
- 🔗 Communication temps réel entre React et Spring Boot via API REST
- 🗄️ Console H2 pour visualiser et manipuler la base de données

---

## 🏗️ Architecture du Projet

inventory-management-spring-react/
│
├── backend/ # Projet Spring Boot
│ ├── src/
│ │ └── main/
│ │ ├── java/
│ │ │ └── com/inventory/backend/
│ │ │ ├── BackendApplication.java # Point d'entrée
│ │ │ ├── model/ # Entités JPA
│ │ │ │ ├── Category.java
│ │ │ │ ├── Product.java
│ │ │ │ └── Supplier.java
│ │ │ ├── repository/ # Accès base de données
│ │ │ │ ├── CategoryRepository.java
│ │ │ │ └── ProductRepository.java
│ │ │ └── controller/ # API REST
│ │ │ └── ProductController.java
│ │ └── resources/
│ │ └── application.properties # Configuration H2
│ └── pom.xml # Dépendances Maven
│
├── frontend/ # Projet React JS
│ ├── src/
│ │ ├── App.js # Composant principal
│ │ └── index.js
│ └── package.json
│
├── README.md


---

## 🛠️ Technologies Utilisées

### Backend
| Technologie | Version | Rôle |
|-------------|---------|------|
| Java | 17 | Langage principal |
| Spring Boot | 3.x | Framework Backend |
| Spring Data JPA | 3.x | ORM & Accès BDD |
| H2 Database | 2.x | Base de données en mémoire |
| Lombok | Latest | Réduction du code Java |
| Maven | 3.x | Gestionnaire de dépendances |

### Frontend
| Technologie | Version | Rôle |
|-------------|---------|------|
| React JS | 18 | Framework Frontend |
| Axios | Latest | Appels HTTP vers l'API |
| HTML / CSS | 5 / 3 | Structure et style |

---

## ⚙️ Installation et Lancement

### Prérequis
- ✅ Java JDK 17 installé
- ✅ Node.js installé
- ✅ VS Code (ou tout autre IDE)

---

### 🔹 Étape 1 : Lancer le Backend

```bash
# Aller dans le dossier backend
cd backend

# Lancer le serveur Spring Boot
./mvnw spring-boot:run
✅ Le serveur démarre sur : http://localhost:8080

URL	Description
http://localhost:8080/api/products	Liste des produits (JSON)
http://localhost:8080/h2-console	Console base de données H2
🔹 Étape 2 : Lancer le Frontend
bash

# Aller dans le dossier frontend
cd frontend

# Installer les dépendances
npm install

# Lancer l'application React
npm start
✅ L'interface s'ouvre sur : http://localhost:3000

🔹 Étape 3 : Connexion à la Console H2
Aller sur : http://localhost:8080/h2-console
Remplir les champs :
JDBC URL : jdbc:h2:mem:testdb
User Name : sa
Password : (laisser vide)
Cliquer sur Connect
🔹 Étape 4 : Ajouter des données de test
Dans la console H2, exécuter ces requêtes SQL :

sql

-- Ajouter des catégories

INSERT INTO CATEGORY (name) VALUES ('Informatique');
INSERT INTO CATEGORY (name) VALUES ('Périphériques');

-- Ajouter des produits
INSERT INTO PRODUCT (name, price, stock_quantity, category_id)
VALUES ('PC Gamer Pro', 12500.0, 5, 1);

INSERT INTO PRODUCT (name, price, stock_quantity, category_id)
VALUES ('Smartphone Samsung', 4500.0, 15, 1);

INSERT INTO PRODUCT (name, price, stock_quantity, category_id)
VALUES ('Casque Audio Sony', 300.0, 50, 2);

INSERT INTO PRODUCT (name, price, stock_quantity, category_id)
VALUES ('Souris Logitech', 150.0, 100, 2);


🔌 Endpoints API REST
Méthode	URL	Description
GET	/api/products	Récupérer tous les produits
POST	/api/products	Ajouter un nouveau produit

📽️ Démonstration Vidéo
👉 Lien vers la vidéo de démonstration : 
(https://drive.google.com/file/d/1cC4xCf4UM1YFU1IHFwjCiHnQ8H2nKaZ2/view?usp=drive_link)Cliquez ici pour voir la démo