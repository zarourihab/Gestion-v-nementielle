## Application Java Swing & JDBC ##
# Thème : Gestion Événementielle #
### 1. Introduction ###

Dans le cadre du module Java (Swing & JDBC), nous avons réalisé une application desktop permettant la gestion d’événements, des participants et des inscriptions.

L’application permet :

Ajouter / modifier / supprimer des événements

Gérer les participants

Gérer les inscriptions

Filtrer par lieu ou date

Afficher des statistiques (participants par événement)

Générer un installateur Windows via Inno Setup

### 2. Analyse & Conception UML###

*Diagramme de classe:*

<img width="399" height="323" alt="Capture d’écran 2026-03-01 180439" src="https://github.com/user-attachments/assets/757d8018-0a14-417a-9bec-09fac78880dc" />

*Diagramme de cas d'utilisation:*

<img width="440" height="335" alt="Capture d’écran 2026-03-01 180651" src="https://github.com/user-attachments/assets/c03f06f1-dea8-45b3-80a6-00fa5bc48e48" />

### 3. Architecture du Projet###

src/
 ├── model
 │     ├── Evenement.java
 │     ├── Participant.java
 │     └── Inscription.java
 ├── dao
 │     ├── EvenementDAO.java
 │     ├── ParticipantDAO.java
 │     ├── InscriptionDAO.java
 ├── dao.impl
 │     ├── EvenementDAOImpl.java
 │     ├── ParticipantDAOImpl.java
 │     └── InscriptionDAOImpl.java
 ├── view
 │     ├── MainFrame.java
 │     ├── EvenementPanel.java
 │     ├── ParticipantPanel.java
 │     └── InscriptionPanel.java
 ├── util
 │     └── DBConnection.java
 
5. Implémentation CRUD

Un CRUD complet est réalisé pour les trois entités (Evenement, Participant, Inscription) avec méthodes create, update, delete, findById et findAll.
Les opérations utilisent des PreparedStatement, avec gestion des erreurs (try/catch) et validation des champs obligatoires.

6. Filtrage & Recherche

Un système de filtrage par lieu et date ainsi qu’une recherche par titre est implémenté via TableRowSorter ou requêtes SQL paramétrées.
Le filtrage est fonctionnel et sécurisé. 

7. Sécurité

Les mots de passe sont sécurisés avec un hash SHA-256 et ne sont jamais stockés en clair.
Lors du login, le mot de passe saisi est haché puis comparé au hash enregistré.

9. Statistiques & Graphiques

Un graphique en barres (JFreeChart) affiche le nombre de participants par événement à partir d’une requête SQL d’agrégation. Les données sont calculées dynamiquement et le graphique est clair et lisible
9. Ergonomie

L’interface propose une navigation simple (menus/onglets), des messages de confirmation, des alertes d’erreur via JOptionPane et une validation des champs obligatoires, garantissant une utilisation stable et intuitive. 
10. Tests

Des tests console et JUnit ont été réalisés pour valider toutes les opérations CRUD, la gestion des erreurs (email dupliqué, double inscription) et assurer la stabilité de la couche DAO 
1. Packaging & Installation

L’application est générée en JAR exécutable, organisée dans un dossier de distribution (jar + libs + assets + script SQL) et packagée avec Inno Setup pour produire un fichier MonApp_Setup.exe avec installation, raccourci et désinstallation
12. Livrables

Livraison de l’application complète (CRUD 3 entités + recherche + graphique), du script SQL, du code structuré en MVC, de la documentation et du setup Windows
13. Conclusion

Le projet a permis d’appliquer UML, JDBC, architecture MVC, CRUD sécurisé, statistiques et déploiement.
14. Tests finaux

Des tests globaux ont été effectués pour vérifier le bon fonctionnement complet de l’application, suivis d’améliorations ergonomiques et de refactoring du code.
15. Documentation finale

Finalisation du README/PDF incluant description du projet, schéma de la base de données, instructions d’exécution et captures d’écran
