# Carte interactive des communes belges — APERÇU

**Statut :** 🟢 Fonctionnel en local — mise en ligne à finaliser

## L'idée

Une page web interactive présentant les **565 communes belges** sur une carte cliquable.
Quand on sélectionne une commune (clic ou recherche), un panneau affiche l'ensemble de
ses statistiques issues de la base de données du TFE (densité de kinésithérapeutes,
part de conventionnés, données socio-démographiques, tendances électorales…).

La carte est une **choroplèthe** : les communes sont colorées selon l'indicateur choisi
dans le menu déroulant, avec une échelle en 5 classes (quintiles) reprenant le code
couleur bleu→blanc→rouge de la base de données.

## Public visé

Support de visualisation pour le TFE (mémoire de kinésithérapie). Destiné à être
mis en ligne pour consultation et illustration.

## Sources de données

| Source | Contenu |
|---|---|
| `Commune-2025-01-01.shp` (Lambert 2008) | Fond de carte des 565 communes (codes NIS, noms FR/NL/DE) |
| `TFE JL - Répartition communale.xlsx` | 14 indicateurs statistiques par commune |

Les deux sources sont reliées par le **code NIS** (correspondance vérifiée : 565/565).

## Stack technique

| Outil | Rôle |
|---|---|
| Leaflet.js | Carte interactive (CDN) |
| HTML / CSS / JS « vanilla » | Page autonome, aucune compilation |
| GeoJSON + JSON | Données géo et statistiques (générées depuis le SHP et l'Excel) |
| Vercel (prévu) | Hébergement statique + déploiement |
