# GestionBILLETS
-------------------- Date limite de rendu : 31 Décembre 2025 -------------

🚀 Fonctionnalités Principales
✅ Gestion des Films et Séances
Consultation du catalogue de films

Affichage des horaires des séances

Gestion des disponibilités en temps réel

✅ Système de Réservation
Réservation de billets individuels

Création de forfaits (groupes de billets)

Calcul automatique des prix avec remises

Vérification des places disponibles

✅ Gestion des Utilisateurs
Inscription et authentification

Profils utilisateurs (normal, étudiant, groupe)

Historique des réservations

✅ Système de Paiement
Multiples modes de paiement (carte, PayPal, espèces)

Traitement sécurisé des transactions

Génération de reçus

✅ Notifications Automatiques
Confirmation de réservation
Alertes de disponibilité
Rappels avant la séance

🏗️ Architecture Technique
Modèle MVC
## Architecture MVC

| Couche      | Responsabilités        | Exemples de Classes                              |
|-------------|------------------------|--------------------------------------------------|
| Modèle      | Gestion des données     | Film, Seance, Utilisateur, Reservation            |
| Vue         | Interface utilisateur   | VuePrincipale, VueReservation, VuePaiement        |
| Contrôleur  | Logique métier          | ControleurReservation, ControleurPaiement         |


------------------------------------------------------------------------------------------------
📁 Structure du Projet
ProjetCinema_GL2/
├── 📂 src/
│   ├── 📂 com/
│   │   └── 📂 cinema/
│   │       ├── 📂 modele/              # Couche Modèle
│   │       │   ├── Film.java           # Membre 1
│   │       │   ├── Seance.java         # Membre 1
│   │       │   ├── Salle.java          # Membre 1
│   │       │   ├── Utilisateur.java    # Membre 2
│   │       │   ├── Profil.java         # Membre 2
│   │       │   ├── Transaction.java    # Membre 3
│   │       │   ├── Reservation.java    # Membre 5
│   │       │   └── Notification.java   # Membre 6
│   │       │
│   │       ├── 📂 vue/                 # Couche Vue
│   │       │   ├── VuePrincipale.java
│   │       │   ├── VueFilm.java
│   │       │   ├── VueReservation.java # Membre 5
│   │       │   ├── VuePaiement.java    # Membre 3
│   │       │   ├── VueUtilisateur.java # Membre 2
│   │       │   └── VueNotification.java # Membre 6
│   │       │
│   │       ├── 📂 controleur/          # Couche Contrôleur
│   │       │   ├── ControleurPrincipal.java # Membre 1
│   │       │   ├── ControleurFilm.java
│   │       │   ├── ControleurReservation.java # Membre 5
│   │       │   ├── ControleurPaiement.java   # Membre 3
│   │       │   ├── ControleurUtilisateur.java # Membre 2
│   │       │   ├── ControleurTarification.java # Membre 4
│   │       │   └── ControleurNotification.java # Membre 6
│   │       │
│   │       └── 📂 patrons/             # Implémentation des 4 patrons
│   │           ├── 📂 singleton/       # Patron Singleton
│   │           │   ├── CinemaManager.java     # Membre 1
│   │           │   └── UserManager.java       # Membre 2
│   │           │
│   │           ├── 📂 strategie/       # Patron Stratégie
│   │           │   ├── 📂 paiement/
│   │           │   │   ├── PaymentStrategy.java      # Interface - Membre 3
│   │           │   │   ├── CreditCardPayment.java    # Membre 3
│   │           │   │   ├── PayPalPayment.java        # Membre 3
│   │           │   │   └── CashPayment.java          # Membre 3
│   │           │   │
│   │           │   └── 📂 tarification/
│   │           │       ├── PricingStrategy.java      # Interface - Membre 4
│   │           │       ├── StandardPricing.java      # Membre 4
│   │           │       ├── StudentPricing.java       # Membre 4
│   │           │       └── GroupPricing.java         # Membre 4
│   │           │
│   │           ├── 📂 composition/     # Patron Composition
│   │           │   ├── TicketComponent.java    # Classe abstraite - Membre 5
│   │           │   ├── SingleTicket.java       # Membre 5
│   │           │   └── TicketPackage.java      # Membre 5
│   │           │
│   │           └── 📂 observateur/     # Patron Observateur
│   │               ├── BookingObserver.java    # Interface - Membre 6
│   │               ├── BookingSubject.java     # Interface - Membre 6
│   │               ├── NotificationManager.java # Membre 6
│   │               ├── EmailNotifier.java      # Membre 6
│   │               └── SMSNotifier.java        # Membre 6
│   │
│   └── Main.java                      # Point d'entrée principal
│
├── 📂 test/                           # Tests unitaires
│   ├── CinemaManagerTest.java         # Membre 1
│   ├── UserManagerTest.java           # Membre 2
│   ├── PaymentStrategyTest.java       # Membre 3
│   ├── PricingStrategyTest.java       # Membre 4
│   ├── CompositionTest.java           # Membre 5
│   └── ObserverTest.java              # Membre 6



------------------------------------------------------------------------------------------------



👥 Équipe de Développement : 
-- Membre 1 - Architecte Principal
Rôle : Singleton Principal & Coordination

Responsabilités : CinemaManager, architecture globale, diagrammes UML

Classes : CinemaManager.java, Film.java, Seance.java, MainController.java

-- Membre 2 - Gestion Utilisateurs
Rôle : Singleton Utilisateurs

Responsabilités : Système d'authentification, gestion des profils

Classes : UserManager.java, User.java, UserProfile.java, UserController.java

-- Membre 3 - Système de Paiement
Rôle : Stratégie Paiement

Responsabilités : Modes de paiement, transactions

Classes : PaymentStrategy.java, CreditCardPayment.java, PayPalPayment.java, PaymentController.java

-- Membre 4 - Système de Tarification
Rôle : Stratégie Tarification

Responsabilités : Calcul des prix, promotions, remises

Classes : PricingStrategy.java, StandardPricing.java, StudentPricing.java, PricingController.java

-- Membre 5 - Gestion Réservations
Rôle : Composition Billets

Responsabilités : Structure des billets, forfaits, réservations

Classes : TicketComponent.java, SingleTicket.java, ForfaitBillets.java, BookingController.java

-- Membre 6 - Système de Notifications
Rôle : Observateur Notifications

Responsabilités : Notifications automatiques, alertes

Classes : BookingObserver.java, NotificationManager.java, EmailNotifier.java, SMSNotifier.java




📋 Scénarios d'Utilisation
* Réservation Simple:
1. Utilisateur se connecte
2. Consulte les films disponibles
3. Sélectionne une séance et des places
4. Paiement en ligne
5. Reçoit une confirmation par email

* Réservation Groupe: 
1. Création d'un forfait "Groupe"
2. Ajout de plusieurs billets
3. Application d'une remise automatique
4. Paiement unique
5. Notifications individuelles

* Gestion Administrative:
1. Ajout de nouveaux films
2. Programmation des séances
3. Consultation des statistiques
4. Gestion des utilisateurs



📚 Documentation
Documentation Technique
Javadoc : Documentation complète des classes et méthodes

Diagrammes UML : Diagrammes de classes, séquences, cas d'utilisation

Spécifications : Besoins fonctionnels et non-fonctionnels
