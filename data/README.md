# Données

## Fichiers

| Fichier | Description |
|---|---|
| `airbnb_train.csv.gz` | 22 234 logements, avec la variable cible `log_price` |
| `airbnb_test.csv.gz` | 51 877 logements à prédire (sans `log_price`) |
| `prediction_example.csv` | Format de rendu attendu : identifiant du logement + `logpred` |

Les CSV sont fournis compressés (`.gz`) pour limiter la taille du dépôt ; `pandas.read_csv`
les lit directement sans décompression manuelle (`pd.read_csv("data/airbnb_train.csv.gz")`).

Ce jeu de données correspond à un format largement utilisé dans les cours de data science
(colonnes `log_price`, `property_type`, `amenities`, `host_since`, etc.) ; il a été fourni
directement dans le cadre du cours.

## Schéma des colonnes

| Colonne | Type | Description |
|---|---|---|
| `id` | int | Identifiant du logement |
| `log_price` | float | **Variable cible** — logarithme du prix de la nuitée |
| `property_type` | str | Type de bien (Apartment, House, Condominium…) |
| `room_type` | str | Entire home/apt, Private room, Shared room |
| `amenities` | str | Liste d'équipements au format texte (ex. `{TV,Wifi,Kitchen}`) |
| `accommodates` | int | Nombre de personnes accueillies |
| `bathrooms` | float | Nombre de salles de bain |
| `bed_type` | str | Type de lit |
| `cancellation_policy` | str | Politique d'annulation |
| `cleaning_fee` | bool | Frais de ménage (oui/non) |
| `city` | str | Ville |
| `description` | str | Description textuelle de l'annonce |
| `first_review` / `last_review` | date | Dates de première / dernière review |
| `host_has_profile_pic` / `host_identity_verified` | t/f | Statut de l'hôte |
| `host_response_rate` | str (%) | Taux de réponse de l'hôte |
| `host_since` | date | Ancienneté de l'hôte |
| `instant_bookable` | t/f | Réservation instantanée |
| `latitude` / `longitude` | float | Localisation |
| `name` | str | Titre de l'annonce |
| `neighbourhood` | str | Quartier |
| `number_of_reviews` | int | Nombre d'avis |
| `review_scores_rating` | float | Note moyenne |
| `zipcode` | str | Code postal |
| `bedrooms` / `beds` | float | Nombre de chambres / lits |

## ⚠️ Format de rendu attendu

Le fichier de soumission doit contenir le **logarithme** du prix (`log_price`), pas le prix
brut. Si un modèle prédit directement le prix, il faut appliquer `np.log()` avant de remplir
le fichier de rendu (voir `prediction_example.csv` pour le format exact : identifiant du
logement + colonne de prédiction).
