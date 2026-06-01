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

- [x] Dépôt GitHub créé et code poussé → https://github.com/Gustache-ux/carte-communes-belges
- [x] **Site mis en ligne sur Vercel** ✅ (déploiement auto à chaque push) — _URL `.vercel.app` à coller ici_
- [ ] Acheter / configurer un nom de domaine (optionnel)
- [ ] Relecture des libellés et unités avec l'auteur du TFE
- [ ] (Optionnel) Ajouter les 3 régions (Flandre / Wallonie / Bruxelles) si fond fourni
- [ ] (Optionnel) Mini-légende des couleurs directement sur la carte en mode mobile

---

## 🚀 Mise en ligne sur Vercel (à faire par Jérémie)

Le code est déjà sur GitHub. Pour le publier :

1. Aller sur **https://vercel.com/new**
2. Se connecter avec le compte GitHub (Gustache-ux)
3. Dans la liste des dépôts, choisir **`carte-communes-belges`** → cliquer **Import**
4. Laisser tous les réglages par défaut (Framework Preset = « Other », pas de build) → cliquer **Deploy**
5. Au bout de ~30 s, Vercel donne une URL en `…vercel.app` : le site est en ligne.

Ensuite, **chaque modification poussée sur GitHub se redéploie automatiquement** (comme pour le site kiné).

---

## ✅ Peaufinage (1er juin 2026)

- [x] Frontières des provinces ajoutées en surcouche (11 provinces, fichier `data/provinces.geojson`)
- [x] Clic sur une commune = sélection seule (plus de zoom automatique)
- [x] Fenêtre « Méthodologie & légende » : code couleur, légende des 14 indicateurs, note méthodologique INAMI
- [x] Sources affichées en pied de page (Statbel, INAMI, SPF Intérieur, Atlas de Belgique)
- [x] Refonte graphique : thème clair, accent sarcelle/vert (le bleu reste réservé aux données)
- [x] Correction du libellé de la province de Liège

## ✅ Peaufinage visuel & mobile (1er juin 2026, suite)

- [x] Titre du site : « Communes belges : Où sont les kinés ? »
- [x] Libellés des indicateurs explicités (abréviations développées, IPEC/IPGC définis)
- [x] Statistiques colorées par quintile dans le panneau (pastilles, code couleur de l'Excel)
- [x] Contour survol/sélection en gris foncé `#2D2F33` (épaisseurs 1,8 / 3,5)
- [x] Bordures des communes en gris moyen `#8a9099` (épaisseur 1)
- [x] Frontières de provinces dans un calque dédié (toujours au premier plan), trait foncé `#2b3340`
- [x] Version mobile : carte plein écran, panneau en bottom sheet ouvert via bouton « Détails »
      (sélection commune et changement d'indicateur gardent la carte en grand)

## 💡 Améliorations possibles (optionnel)

- Bouton d'export de la carte en image (PNG) pour le mémoire
- Comparaison côte à côte de deux indicateurs
- Mode impression
- Dégradé centré sur zéro pour les indicateurs d'évolution

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
