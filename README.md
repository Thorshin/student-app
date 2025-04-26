# Application de Gestion des Étudiants

Une application Spring Boot pour la gestion des dossiers étudiants avec des API RESTful.

## Description

Cette application permet de gérer efficacement les informations des étudiants dans un établissement d'enseignement. Elle offre une interface API complète pour effectuer toutes les opérations CRUD (Création, Lecture, Mise à jour, Suppression) sur les données des étudiants.

## Technologies Utilisées

- Java 17
- Spring Boot 3.4.4
- Spring Data JPA
- Base de données MySQL
- Lombok
- Maven

## Prérequis

Avant d'exécuter cette application, assurez-vous d'avoir installé les éléments suivants :

- Java Development Kit (JDK) 17 ou supérieur
- Maven 3.x
- Serveur MySQL
- Un IDE de votre choix (IntelliJ IDEA recommandé)

## Installation

1. Cloner le dépôt :
   ```bash
   git clone [repository-url]
   cd students-app
   ```

2. Configurer la base de données MySQL :
   - Créer une base de données MySQL
   - Mettre à jour le fichier `src/main/resources/application.properties` avec vos identifiants de base de données
   - Exemple de configuration :
     ```
     spring.datasource.url=jdbc:mysql://localhost:3306/students_db
     spring.datasource.username=votre_utilisateur
     spring.datasource.password=votre_mot_de_passe
     spring.jpa.hibernate.ddl-auto=update
     ```

3. Construire le projet :
   ```bash
   mvn clean install
   ```

4. Exécuter l'application :
   ```bash
   mvn spring-boot:run
   ```
   
   Ou l'exécuter depuis votre IDE en lançant la classe `StudentsAppApplication`.

## Structure du Projet

```
src/main/java/org/example/studentsapp/
├── StudentsAppApplication.java    # Classe principale de l'application
├── entities/                      # Classes d'entités JPA
│   ├── Student.java              # Entité Étudiant
│   └── ...                       # Autres entités
├── repository/                    # Repositories Spring Data JPA
│   ├── StudentRepository.java    # Repository pour les étudiants
│   └── ...                       # Autres repositories
└── web/                          # Contrôleurs REST et DTOs
    ├── StudentController.java    # Contrôleur pour les étudiants
    ├── StudentDTO.java           # DTO pour les étudiants
    └── ...                       # Autres contrôleurs et DTOs
```

## Fonctionnalités

- API RESTful complète pour la gestion des étudiants
- Opérations CRUD sur les dossiers étudiants
- Persistance des données avec MySQL
- Utilisation de Lombok pour réduire le code boilerplate
- Spring Data JPA pour les opérations de base de données
- Validation des données
- Gestion des erreurs
- Documentation API intégrée

## Documentation de l'API

L'application fournit les endpoints API suivants :

### Gestion des Étudiants

- `GET /api/students` - Récupérer tous les étudiants
  - Retourne une liste paginée des étudiants
  - Paramètres optionnels : page, size, sort

- `GET /api/students/{id}` - Récupérer un étudiant spécifique
  - Retourne les détails d'un étudiant par son ID

- `POST /api/students` - Créer un nouvel étudiant
  - Corps de la requête : informations de l'étudiant
  - Retourne l'étudiant créé avec son ID

- `PUT /api/students/{id}` - Mettre à jour un étudiant existant
  - Corps de la requête : nouvelles informations de l'étudiant
  - Retourne l'étudiant mis à jour

- `DELETE /api/students/{id}` - Supprimer un étudiant
  - Supprime l'étudiant spécifié par son ID

## Construction et Tests

Pour construire le projet :
```bash
mvn clean install
```

Pour exécuter les tests :
```bash
mvn test
```

Pour générer un rapport de couverture de tests :
```bash
mvn test jacoco:report
```

## Déploiement

L'application peut être déployée de plusieurs façons :

1. En tant que JAR exécutable :
   ```bash
   mvn clean package
   java -jar target/students-app-0.0.1-SNAPSHOT.jar
   ```

2. Dans un conteneur Docker :
   ```bash
   docker build -t students-app .
   docker run -p 8080:8080 students-app
   ```

3. Sur une plateforme cloud (AWS, Google Cloud, Azure)

## Sécurité

- L'application utilise Spring Security pour la protection des endpoints
- Authentification basée sur JWT (JSON Web Token)
- Configuration CORS pour la sécurité des requêtes cross-origin
- Validation des entrées utilisateur

## Contribution

1. Forker le dépôt
2. Créer votre branche de fonctionnalité (`git checkout -b feature/NouvelleFonctionnalite`)
3. Commiter vos changements (`git commit -m 'Ajout d'une nouvelle fonctionnalité'`)
4. Pousser vers la branche (`git push origin feature/NouvelleFonctionnalite`)
5. Ouvrir une Pull Request

## Support

Pour toute question ou problème, veuillez :
- Ouvrir une issue sur GitHub
- Consulter la documentation
- Contacter l'équipe de développement

## Licence

Ce projet est sous licence MIT - voir le fichier LICENSE pour plus de détails.

## Remerciements

- Équipe de développement
- Contributeurs
- Communauté Spring Boot
- Tous les utilisateurs qui ont contribué à l'amélioration de l'application 