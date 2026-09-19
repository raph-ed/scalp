#ReadMe
Plateforme d'intelligence commerciale et d'aide à la décision pour l'implantation d'entreprises dans les arrondissements parisiens. L'application extrait les données du registre des entreprises, applique un modèle d'évaluation de rentabilité sectorielle et projette les établissements sur une vue satellite 3D interactive.

Apercu

Le projet repond au besoin d'analyse concurrentielle prealable a la creation d'entreprise a Paris. Pour chaque arrondissement (du 75001 au 75020) et secteur d'activite selectionne, l'application consolide un echantillon d'au moins 20 etablissements, modelise leurs indicateurs economiques (marge, chiffre d'affaires, tension commerciale) et formule des recommandations de produits porteurs.

Fonctionnalites

Collecte automatisee : Interrogation directe de l'API Recherche d'Entreprises (api.gouv.fr) filtre par code postal et code NAF.

Garantie volumetrique : Algorithme de repartition spatiale assurant un minimum de 20 etablissements analyses par arrondissement.

Rendu cartographique 3D : Moteur WebGL (MapLibre GL JS) superpose aux tuiles satellite Esri World Imagery avec inclinaison dynamique a 60 degres.

Indicateurs macro-economiques :

Rendement moyen estime (marge nette en %).

Chiffre d'affaires moyen declare/estime.

Score d'opportunite d'implantation sur 100.

Identification des quintiles extremes (top 5 plus et moins rentables).

Catalogue strategique : Base de donnees semantique recommandant les produits best-sellers et niveaux de prix cibles par filiere.

Export et audit : Telechargement des donnees au format CSV et systeme d'enregistrement de retours utilisateurs persiste sur SQLite.

Architecture Technique

Backend : FastAPI (Python 3.10+), Uvicorn, SQLite3, HTTPX (client HTTP asynchrone), Pydantic v2.

Frontend : JavaScript natif (ES6+ asynchrone), HTML5, CSS3 modulaire.

Cartographie : MapLibre GL JS, tuiles satellite ArcGIS Esri.

Sources de donnees : Base SIRENE via l'API Recherche d'Entreprises de la DINUM.
Prerequis

Python 3.10 ou superieur

Gestionnaire de paquets pip

Navigateur web moderne avec support WebGL 2.0 active (Chrome, Firefox, Edge, Safari)

Installation et Deploiement

1. Cloner le depot

git clone https://github.com/votre-utilisateur/paris-market-intelligence.git
cd paris-market-intelligence


2. Configurer l'environnement virtuel

Sous Linux / macOS :

python3 -m venv venv
source venv/bin/activate


Sous Windows (PowerShell) :

python -m venv venv
.\venv\Scripts\Activate.ps1


3. Installer les dependances

pip install --upgrade pip
pip install -r requirements.txt


4. Lancer le serveur

python app.py


L'application est disponible a l'adresse : http://127.0.0.1:8000
