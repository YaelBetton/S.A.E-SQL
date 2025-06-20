# 🎮 SAE R1.04 – Analyse des ventes de jeux vidéo avec SQL

## 👥 Membres du groupe
- Betton Yaël  
- Bastide Rémi  
- Sacristan Thurian  

---

## 📌 Objectifs du projet

Ce projet vise à :
- Importer et nettoyer un dataset de ventes de jeux vidéo
- Créer une base de données relationnelle structurée
- Réaliser des requêtes SQL avancées
- Visualiser les résultats à l'aide de **SQLPad**

Les données utilisées proviennent de [Kaggle - vgsales.csv](https://www.kaggle.com/datasets/gregorut/videogamesales).

---

## 🧱 Architecture du projet

### 🗂 Phase 1 : Préparation

- **Import du fichier `vgsales.csv`** dans SQL Server
- Création d'une table brute `vgsales`
- **Analyse des données** :
  - Champs vides
  - Données “N/A” ou “Unknown”
  - Redondances

### 🧾 Phase 2 : Modélisation relationnelle

- **Schéma relationnel** : séparation en 5 tables
  - `GENRE`, `EDITEUR`, `PLATEFORME`, `JEUX`, `VENTES`
- **Création et insertion de données** :
  - Nettoyage des années (`'N/A' → NULL`)
  - Relations via clés étrangères
- **Suppression** (facultative) de la table initiale `vgsales`

### 📊 Phase 3 : Requêtes et visualisations

Les requêtes SQL réalisées incluent :

1. **Plateformes ayant plus de 20M de jeux vendus en Europe depuis 2010**
2. **Éditeurs PS4 ayant vendu plus de 2M de jeux**, triés par ventes décroissantes
3. **Évolution des ventes par genre en Amérique du Nord (2000–2010)** avec graphiques
4. **Répartition du nombre de jeux par genre** sur 4 périodes (1980–2023)
5. **Requêtes supplémentaires** :
   - Évolution des ventes globales par décennie
   - Part de marché des plateformes entre 2000 et 2010

### 🛠 SQLPad

Utilisé pour lancer les requêtes et générer des visualisations.  
L'installation est faite via script `.sh` sur les ordinateurs de l’IUT.

---

## 🧮 Schéma des tables (résumé)

```sql
JEUX(idJeu, NomDuJeu, Classement, Annee, idPublisher, idPlateforme, idGenre)
VENTES(idJeu, VenteNA, VenteEU, VenteJP, VenteAutre, VenteGlobales)
GENRE(idGenre, NomGenre)
EDITEUR(idEditeur, NomEditeur)
PLATEFORME(idPlateforme, NomPlateforme)
