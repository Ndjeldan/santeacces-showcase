#  SantéAccès Cameroun — Crisis Room Platform

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Leaflet](https://img.shields.io/badge/Leaflet-199900?style=for-the-badge&logo=leaflet&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-Ready-5A0FC8?style=for-the-badge&logo=pwa&logoColor=white)

> ** Note sur le code source :** *Le code complet du backend (FastAPI) et du frontend est conservé dans un dépôt privé pour des raisons de sécurité des données de santé et de protection de la propriété intellectuelle. Ce dépôt public sert de vitrine technique (architecture, méthodologie, captures d'écran). Une démonstration complète peut être fournie sur demande lors d'un entretien.*

## 📖 Executive Summary

**SantéAccès Cameroun** est une plateforme de « Salle de crise » conçue pour les équipes humanitaires intervenant dans des zones d'urgence sanitaire.

Le premier cas d'usage ciblé est la **réponse au choléra dans le district de Minawao (Extrême-Nord, Cameroun)**. L'outil permet de centraliser les données fragmentées (alertes sanitaires, points d'eau, obstacles logistiques) pour accélérer la prise de décision et la coordination des secours sur le terrain.

##  Architecture & Stack Technique

L'application repose sur une architecture Full-Stack moderne et sécurisée :

```mermaid
graph TD
    A[Frontend: Leaflet / JS / PWA] -->|REST API + JWT| B[Backend: FastAPI / Python]
    B -->|Auth & Validation| C{Sécurité}
    C -->|Admin / User| D[Moteur Métier]
    D -->|Nettoyage & Import| E[(SQLite / Pandas)]
    D -->|Génération PDF| F[ReportLab]
    F --> G[Plan de Mission PDF]
```

###  Technologies utilisées

- **Backend :** Python 3.10+, FastAPI, Uvicorn, SQLAlchemy
- **Data & Ingestion :** Pandas (nettoyage et validation des fichiers CSV), SQLite (base de données)
- **Sécurité :** Authentification par JWT (JSON Web Tokens), rôles différenciés (Admin/User)
- **Génération de documents :** ReportLab (création dynamique de plans de mission PDF)
- **Frontend :** HTML5, JavaScript (Vanilla), Leaflet.js, CSS3
- **Résilience :** Progressive Web App (PWA) avec Service Worker pour un fonctionnement hors-ligne

##  Fonctionnalités clés

- **Import de données intelligent :** téléversement de fichiers CSV. Le backend utilise Pandas pour nettoyer les données, valider les coordonnées (dans les limites du Cameroun) et détecter les doublons avant l'insertion en base.
- **Cartographie interactive (Salle de crise) :** visualisation en temps réel des alertes (suspectées/confirmées), des points d'eau en panne et des obstacles routiers sur un fond de carte sombre optimisé pour les salles d'opérations.
- **Génération de plans de mission :** création en un clic de rapports PDF incluant la carte de la zone, la liste des points d'eau à réparer et les coordonnées GPS pour les équipes terrain.
- **Mode hors-ligne (PWA) :** l'interface est conçue pour se charger et fonctionner avec une connexion Internet limitée ou instable, caractéristique des zones d'intervention.
- **Sécurité :** accès protégé par authentification. Les données sensibles ne sont visibles que par les utilisateurs autorisés.

##  Impact & Cas d'usage

- **Gain de temps :** réduction du temps de préparation d'une mission (centralisation des données en un seul écran vs. compilation manuelle de multiples fichiers Excel).
- **Meilleure coordination :** permet aux coordinateurs WASH (Eau, Assainissement, Hygiène) et Santé de croiser leurs données géographiques.
- **Aide à la décision :** identification visuelle immédiate des zones où les points d'eau sont en panne à proximité des alertes sanitaires.

##  Aperçu de l'application

| Salle de crise (Carte) | Panneau latéral |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/c3e5b6e4-2de0-4450-8772-20ac3e19545b" alt="Salle de crise - carte sombre" width="100%"> | <img src="https://github.com/user-attachments/assets/a72fc64a-c46c-46d0-8232-c8d695ef87ca" alt="Panneau latéral" width="100%"> |

| Plan de mission PDF (FR) | Plan de mission PDF (EN) |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/fc7d6f76-5ce4-46e1-ab50-4679d59e855a" alt="Plan de mission PDF en français" width="100%"> | <img src="https://github.com/user-attachments/assets/2e5b6726-1972-4e0c-bd18-b845bfc3374e" alt="Mission plan PDF in English" width="100%"> |

##  Auteur

**NDJEL DAN David Thierry**
*Ingénieur Géospatial Full-Stack & Spécialiste Humanitaire Tech*

[Portfolio](https://ton-portfolio.com) · [LinkedIn](https://www.linkedin.com/in/ton-profil)
