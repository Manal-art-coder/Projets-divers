**Description**

Ce projet consiste à extraire, transformer et charger des données clients provenant de fichiers JSON et CSV dans un Data Warehouse, en suivant le processus ETL (Extract, Transform, Load). Le projet utilise Python, Pandas, SQLAlchemy, et une base de données PostgreSQL pour le stockage des données. Le but est de démontrer la capacité à travailler avec des données structurées et non structurées, en nettoyant et en structurant les informations pour les rendre exploitables pour des analyses futures.

**Objectifs**

- Extraire les données depuis des fichiers JSON et CSV.
- Appliquer des transformations pour nettoyer et préparer les données.
- Charger les données transformées dans un Data Warehouse sous forme de tables de fait et de dimension.

**Technologies utilisées**

Python, Pandas, SQLAlchemy, PostgreSQL, Google Collab. 

**Utilisation**

1. Téléchargement des données : Le projet télécharge automatiquement les fichiers JSON et CSV depuis les URLs fournies dans le code.

2. Extraction des données de Glen Burnie : Une fonction extract_glen_burnie_data() est utilisée pour extraire les données des clients vivant à Glen Burnie.

3. Fusion des données : Les données des clients de Glen Burnie sont ensuite fusionnées avec les données de transactions et de produits pour créer un DataFrame complet.

4. Nettoyage des données : Les doublons et les valeurs manquantes sont supprimés dans le DataFrame fusionné.

5. Transformation des données : Le projet effectue des transformations spécifiques pour préparer les données avant leur insertion dans le Data Warehouse.

6. Chargement des données dans PostgreSQL : Le DataFrame transformé est chargé dans un Data Warehouse PostgreSQL sous forme de tables de fait et de dimension.

**Structure des données**

**transactions_fact** : Table de faits contenant les informations sur les transactions clients.
**products_dimension** : Table de dimension contenant les informations sur les produits.
**clients_dimension** : Table de dimension contenant les informations sur les clients de Glen Burnie.

**Résultats**

Après avoir exécuté le processus ETL, les données sont prêtes à être analysées dans le Data Warehouse. Les tables de faits et de dimensions permettent d'effectuer des analyses multidimensionnelles sur les transactions clients, les produits, et les clients eux-mêmes.

**Points à améliorer**

- Ajouter des validations supplémentaires sur les données avant de les charger dans la base de données.
- Optimiser le processus de chargement pour gérer des volumes de données plus importants.
- Ajouter des logs et une gestion des erreurs pour suivre le processus ETL.
