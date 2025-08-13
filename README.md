
# 📱 Easy Bilamba

![Flutter](https://img.shields.io/badge/Flutter-02569B?logo=flutter&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?logo=java&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)
![Version](https://img.shields.io/badge/version-1.0.0-blue)

**Easy Bilamba** est une application mobile multiplateforme inspirée du modèle **Vinted** permettant à ses utilisateurs **d’acheter, vendre et échanger des articles facilement via une plateforme intuitive et sécurisée**. Développée avec **Flutter (Frontend)** et **Java Spring Boot (Backend)**, elle combine rapidité, ergonomie et sécurité.

## 🚀 Fonctionnalités principales
- **Comptes utilisateurs**
    - Inscription / connexion via email, téléphone ou réseaux sociaux
    - Profil complet avec photo, bio et localisation
    - Système de notation et avis entre membres
- **Catalogue & annonces**
    - Création d’annonces avec photos multiples, prix, description, catégorie
    - Recherche intelligente avec autocomplétion
    - Filtrage par prix, localisation, état et date
- **Transactions**
    - Messagerie instantanée acheteur ↔ vendeur
    - Paiements sécurisés via Stripe, PayPal et Mobile Money
    - Suivi des commandes et confirmation de réception
- **Notifications**
    - Push en temps réel pour messages, ventes et offres
    - Alertes personnalisées pour produits suivis
- **Sécurité**
    - Authentification JWT + mots de passe hashés BCrypt
    - Signalement et blocage des utilisateurs
    - Vérification d’identité des vendeurs

## 🛠 Technologies utilisées
**Frontend (Flutter/Dart)**  
`provider` ou `riverpod` — Gestion d’état  
`dio` — Requêtes HTTP  
`cached_network_image` — Gestion optimisée des images  
`flutter_stripe` — Paiements  
`firebase_messaging` — Notifications push  
`image_picker` — Prise de photos

**Backend (Java/Spring Boot)**  
Spring Boot — API REST  
Spring Security + JWT — Authentification  
PostgreSQL/MySQL — Base de données  
Amazon S3/Firebase Storage — Stockage images  
Stripe/PayPal API — Paiements  
Firebase Cloud Messaging — Notifications

## 🗂 Structure du projet
Easy-Bilamba/
│
├── mobile/ # Application Flutter
│ ├── lib/
│ │ ├── main.dart # Point d’entrée Flutter
│ │ ├── screens/ # Écrans de l’app
│ │ ├── widgets/ # Composants réutilisables
│ │ ├── models/ # Modèles de données
│ │ ├── services/ # API calls & gestion données
│ │ └── providers/ # Gestion d’état
│ ├── pubspec.yaml # Dépendances Flutter
│
├── backend/ # API Java Spring Boot
│ ├── src/main/java/
│ │ ├── controllers/ # Endpoints REST
│ │ ├── models/ # Entités JPA
│ │ ├── repositories/ # Accès DB
│ │ ├── services/ # Logique métier
│ │ └── security/ # Authentification & JWT
│ ├── pom.xml # Dépendances Maven
│
├── docs/ # Documentation projet
│
└── README.md # Ce fichier


## 📊 Diagramme UML simplifié
```mermaid
classDiagram
    class Utilisateur {
        -id: Long
        -nom: String
        -email: String
        -motDePasse: String
        +creerAnnonce()
        +envoyerMessage()
    }
    class Annonce {
        -id: Long
        -titre: String
        -description: String
        -prix: Double
        -images: List<String>
    }
    class Transaction {
        -id: Long
        -acheteur: Utilisateur
        -vendeur: Utilisateur
        -annonce: Annonce
        -status: String
    }
    class Message {
        -id: Long
        -contenu: String
        -date: Date
    }
    Utilisateur "1" -- "*" Annonce
    Utilisateur "1" -- "*" Message
    Utilisateur "1" -- "*" Transaction
    Annonce "1" -- "*" Transaction

# Cloner le projet
git clone https://github.com/votrecompte/easy-bilamba.git
cd easy-bilamba

# Backend
cd backend
./mvnw spring-boot:run

# Frontend
cd mobile
flutter pub get
flutter run

🌐 Endpoints API REST
Méthode	Endpoint	Description
POST	/auth/register	Inscription
POST	/auth/login	Connexion
GET	/products	Liste des annonces
POST	/products	Créer une annonce
GET	/messages/{id}	Messages d’une conversation
📦 Déploiement

Backend : AWS EC2 / Heroku

Base de données : AWS RDS / Railway

Stockage : Amazon S3 / Firebase Storage

Mobile : Google Play + Apple App Store

📸 Captures d’écran

(À insérer après design)




📝 Licence

Distribué sous licence MIT — utilisation libre avec attribution.

🤝 Contribution

Fork du projet

Créer une branche : feature/ma-fonctionnalite

Commit : git commit -m "Ajout fonctionnalité X"

Push : git push origin feature/ma-fonctionnalite

Pull Request

📧 Contact

Email : contact@easybilamba.com

LinkedIn : Easy Bilamba

Twitter : @EasyBilamba


