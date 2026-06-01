# Carte interactive des communes belges

Visualisation interactive des **565 communes belges** : carte choroplèthe + statistiques
communales (densité de kinésithérapeutes, données socio-démographiques, tendances électorales).
Réalisée dans le cadre d'un TFE (kinésithérapie).

## Utilisation

Site statique — aucune compilation. Ouvrir `index.html` via un serveur HTTP :

```bash
python -m http.server 8000
# puis http://localhost:8000
```

## Structure

```
index.html              Page complète (carte Leaflet + interface)
data/communes.geojson   Fond de carte (565 communes, WGS84)
data/stats.json         Statistiques par commune (indexées par code NIS)
```

## Données

- Fond de carte : communes 2025 (reprojeté Lambert 2008 → WGS84).
- Statistiques : base de données du TFE, reliées par code NIS.
