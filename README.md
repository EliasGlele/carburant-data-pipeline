# 🛢️ Data Pipeline complet : identification des stations les plus économiques dans le Var

## Description du projet
Mise en œuvre d’un pipeline analytique complet : récupération et nettoyage de données de “data carburant”, analyse SQL sous BigQuery, et création d’un dashboard interactif sous Looker Studio.  
Ce projet illustre ma capacité à transformer une donnée brute en insight exploitable pour la prise de décision.

🔗 Lien du dashboard :  
https://lookerstudio.google.com/reporting/2670ee47-66d5-437b-893c-696414f0e8a7

---

## 🧭 Contexte et objectif du projet
Ce projet de data analyse s’inscrit dans une logique d’exploration de données publiques et de mise en œuvre d’un pipeline analytique complet.  
L’objectif était d’identifier les stations essence les plus avantageuses autour d’une adresse donnée, en combinant des données de prix en temps réel, des calculs géographiques et une visualisation dynamique.

L’étude a été menée à partir d’une base de données publique issue de data.gouv.fr, regroupant les prix instantanés des carburants sur l’ensemble du territoire français.

---

## 🧩 Étape 1 – Collecte et préparation des données
Les données ont été extraites depuis la plateforme Data.gouv.fr via le jeu de données  
« Prix des carburants en France (flux instantané) » :  
https://www.data.gouv.fr/datasets/prix-des-carburants-en-france-flux-instantane-v2-amelioree/

Ce flux contient des informations détaillées sur plus de 10 000 stations-service : identifiants, adresses, coordonnées GPS, type de carburant, horaires, ruptures, prix actualisés quotidiennement, etc.

Une première étape de préparation sous Excel a permis de rendre le jeu de données exploitable :

- Sélection des colonnes pertinentes (adresse, ville, latitude, longitude, type et prix du carburant)
- Nettoyage et suppression des doublons
- Normalisation des en-têtes de colonnes (suppression des espaces, renommage cohérent)
- Filtrage du département concerné (code_departement = 83)

Cette étape a permis d’obtenir un jeu de données propre, structuré et standardisé, prêt à être intégré dans un entrepôt de données.

---

## 🗄️ Étape 2 – Stockage et traitement sur BigQuery
Une fois nettoyé, le dataset a été importé dans Google BigQuery afin de bénéficier d’une infrastructure scalable et d’outils SQL avancés pour l’analyse.

L’objectif était d’enrichir la base avec des informations calculées, par exemple la distance entre le domicile de référence et chaque station essence, pour déterminer la plus économique à proximité avec la requête suivante :

*(requête SQL à insérer ici)*

Les résultats obtenus ont ensuite servi de source directe à la visualisation Looker Studio.

---

## 📊 Étape 3 – Visualisation dynamique avec Looker Studio
Le jeu de données traité a été connecté à Google Looker Studio pour créer un dashboard interactif accessible et lisible par tout utilisateur.

Les objectifs principaux de la visualisation étaient de :
- Présenter les stations les plus proches et les moins chères selon le prix du SP95
- Visualiser la répartition des prix sur l’ensemble du département
- Avoir une visualisation géographique des stations
- Offrir une expérience utilisateur fluide, avec filtres et tris dynamiques

Parmi les éléments clés du dashboard :
- Un tableau dynamique listant les stations avec adresse, prix et distance
- Un graphique à barres de répartition des prix du SP95
- Une carte interactive géolocalisant les stations du Var
- Des filtres permettant à l’utilisateur de sélectionner une ville ou un rayon de distance spécifique

L’ensemble a été pensé pour offrir une lecture rapide et orientée décision, dans la logique d’un “Decision Support Dashboard”.

---

## 🔍 Étape 4 – Bilan
Ces résultats soulignent l’intérêt d’une approche analytique multi-critères (prix + distance), utile aussi bien pour un particulier souhaitant optimiser ses trajets que pour un professionnel gérant une flotte de véhicules.

🔗 Lien du dashboard :  
https://lookerstudio.google.com/reporting/2670ee47-66d5-437b-893c-696414f0e8a7

---

## 🧠 Compétences techniques mobilisées

| Domaine | Compétences et outils utilisés |
|------|-------------------------------|
| Data Collection | Importation de données publiques depuis Data.gouv.fr |
| Data Cleaning | Nettoyage et standardisation sous Excel |
| Data Warehousing | Stockage et modélisation sous Google BigQuery |
| SQL Analytics | Écriture de requêtes analytiques |
| Data Visualization | Création d’un dashboard interactif sous Looker Studio |
| Analytical Thinking | Définition d’indicateurs, interprétation et storytelling data |
