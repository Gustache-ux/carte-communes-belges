# Avancement — Carte interactive des communes belges

Dernière mise à jour : 1er juin 2026

---

## ✅ Terminé

- [x] Inspection du shapefile (565 communes, Lambert 2008, codes NIS + noms)
- [x] Inspection de l'Excel (565 communes, 14 indicateurs + légende)
- [x] Conversion du shapefile → GeoJSON reprojeté en WGS84 et simplifié (923 Ko)
- [x] Extraction de l'Excel → JSON indexé par code NIS (176 Ko)
- [x] Vérification de la correspondance NIS (565/565, match parfait)
- [x] Page HTML interactive (Leaflet) :
  - [x] Carte choroplèthe en 5 classes (quintiles, code couleur bleu→blanc→rouge)
  - [x] Sélecteur d'indicateur (14 variables)
  - [x] Légende dynamique qui s'adapte à l'indicateur
  - [x] Clic sur une commune → panneau de statistiques complet (14 lignes)
  - [x] Recherche de commune par nom (avec navigation clavier)
  - [x] Survol → infobulle nom + valeur de l'indicateur courant
  - [x] Design sombre, responsive (mobile/desktop)
- [x] Test local validé (rendu des 565 polygones + interactions confirmés)

---

## 🔲 À faire

- [ ] **Mise en ligne** (choix de la méthode : Vercel / GitHub Pages — voir ci-dessous)
- [ ] Acheter / configurer un nom de domaine (optionnel)
- [ ] Relecture des libellés et unités avec l'auteur du TFE

---

## 💡 Améliorations possibles (optionnel)

- Bouton d'export de la carte en image (PNG) pour le mémoire
- Comparaison côte à côte de deux indicateurs
- Mode clair / impression
- Affichage des frontières de provinces

---

## 🛠 Comment regénérer les données

Scripts dans `E:/IPCRA/_agents_workspace/carte/` :
- `convert_geo.py` → `data/communes.geojson`
- `convert_stats.py` → `data/stats.json`

Dépendances Python : `pyshp`, `pyproj`, `shapely`, `openpyxl`.

## 🛠 Tester en local

```
cd "E:/IPCRA/1 Projets/TFE/Carte interactive communes"
python -m http.server 8000
```
Puis ouvrir http://localhost:8000 dans le navigateur.
