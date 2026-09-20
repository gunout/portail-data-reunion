# 🌋 Portail des données publiques — La Réunion

[![Licence Ouverte Etalab 2.0](https://img.shields.io/badge/Licence-Etalab%202.0-000091?style=flat-square)](https://www.etalab.gouv.fr/licence-ouverte-open-licence)
[![Source](https://img.shields.io/badge/Source-data.regionreunion.com-e1000f?style=flat-square)](https://data.regionreunion.com)
[![API](https://img.shields.io/badge/API-OpenDataSoft%20v2.1-18753c?style=flat-square)](https://help.opendatasoft.com/apis/ods-explore-v2/)
[![Statut](https://img.shields.io/badge/Statut-Production-000091?style=flat-square)]()
[![Accessibilité](https://img.shields.io/badge/RGAA-4.1%20AA%20vis%C3%A9-a5770a?style=flat-square)]()

> **Tableau de bord des politiques publiques de La Réunion**
> Portail de visualisation des données ouvertes du territoire réunionnais.
> Source : `data.regionreunion.com` — API OpenDataSoft Explore v2.1 · Aucune clé requise.

---

## 📋 Présentation

Ce portail fournit une **vision consolidée** des indicateurs territoriaux de La Réunion à partir des données ouvertes publiées par la Région, l'Insee, l'IEDOM, l'Observatoire de l'Énergie et les autres producteurs de données publics.

Il permet aux agents publics, élus, chercheurs et citoyens d'accéder en un coup d'œil aux **26 modules thématiques** couvrant l'économie, l'emploi, le logement, la santé, l'éducation, l'environnement, les transports et les risques.

---

## ✨ Fonctionnalités

### 26 modules thématiques

| Domaine | Modules |
|---|---|
| **Économie & Emploi** | Économie · Emploi · Tourisme · Logement · Transport |
| **Société** | Éducation · Santé · Social · Culture · Administration |
| **Territoire** | Environnement · Énergie · Géographie · Télécom · Risques · Population |
| **Spécialisé** | Agriculture · Équipements · Patrimoine · Hébergement · À proximité · Possession · Territoire · Urbanisme · Météo |
| **Recherche** | Exploration du catalogue (~270 datasets) |

### Fonctionnalités techniques

- 🔍 **Module d'exploration** du catalogue complet avec recherche par mot-clé
- 📊 **Visualisations Chart.js** — 75+ graphiques (doughnut, line, bar)
- 🔄 **Rafraîchissement automatique** toutes les heures
- 💾 **Cache local** (localStorage, 6 h d'expiration)
- 📱 **Responsive** de 400 px à 2560 px (mobile, tablette, desktop, 4K)
- ♿ **Accessibilité RGAA 4.1** — niveau AA visé
- 🌙 **Mode sombre automatique** (`prefers-color-scheme`)
- ⚡ **Fallback intégré** — valeurs de référence si l'API est indisponible
- 🎨 **Charte officielle de l'État** — Marianne, bleu France `#000091`, rouge Marianne `#e1000f`

---

## 🚀 Déploiement

### Option 1 — GitHub Pages (recommandé)

1. **Créer un dépôt public** sur GitHub
2. **Cloner et placer le fichier**

```bash
git clone https://github.com/<votre-utilisateur>/<nom-du-depot>.git
cd <nom-du-depot>
cp /chemin/vers/dashboard.html index.html
git add index.html
git commit -m "Initial commit — Dashboard Réunion"
git push origin main
```

3. **Activer GitHub Pages**
   - Settings → Pages → Source : `main` branch → `/ (root)`
   - Le site sera disponible à `https://<votre-utilisateur>.github.io/<nom-du-depot>/`

### Option 2 — Serveur local

```bash
python -m http.server 8000
# Ouvrir http://localhost:8000
```

### Option 3 — Tout autre hébergement statique

Le fichier est **100 % autonome** (HTML + CSS + JS inline). Il peut être servi par :
- Netlify · Vercel · Cloudflare Pages
- Nginx · Apache · Caddy
- Tout CDN statique

Aucun backend, aucune base de données, aucune variable d'environnement requise.

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│  Navigateur (client unique)                             │
│  ┌───────────────────────────────────────────────────┐  │
│  │  index.html                                       │  │
│  │  ├── Structure (HTML)                             │  │
│  │  ├── Charte DSFR (CSS inline)                     │  │
│  │  └── Logique (JS inline)                          │  │
│  └───────────────────────────────────────────────────┘  │
│           │                                             │
│           │  fetch()                                    │
│           ▼                                             │
│  ┌───────────────────────────────────────────────────┐  │
│  │  API OpenDataSoft Explore v2.1                    │  │
│  │  https://data.regionreunion.com/api/explore/v2.1  │  │
│  └───────────────────────────────────────────────────┘  │
│           │                                             │
│           ▼                                             │
│  ┌───────────────────────────────────────────────────┐  │
│  │  Cache local (localStorage) — 6 h                 │  │
│  └───────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
```

**Aucune dépendance serveur.** Pas de build, pas de compilation.

---

## 📡 Sources de données

| Producteur | URL | Licence |
|---|---|---|
| **Région Réunion** | [data.regionreunion.com](https://data.regionreunion.com) | Etalab 2.0 |
| **Insee** | [insee.fr](https://www.insee.fr) | Etalab 2.0 |
| **IEDOM** | [iedom.fr](https://www.iedom.fr) | Etalab 2.0 |
| **Observatoire de l'Énergie** | [oer.fr](https://www.oer.fr) | Etalab 2.0 |

**Producteurs intermédiaires** consultés via le portail :
- France Travail (Pôle emploi)
- CAF Réunion
- CNAM
- DAAF Réunion
- DEAL Réunion
- Rectorat de La Réunion
- Observatoire Régional du Tourisme
- Atmo Réunion
- Chambre des Notaires
- Aéroport Roland Garros

---

## 📊 Indicateurs clés affichés

| Indicateur | Valeur | Source |
|---|---|---|
| Population 2026 | **911 000 habitants** | Insee |
| PIB | **24,4 Md€** | Insee |
| Croissance 2025 | **+1,1 %** | CEROM/Insee |
| Taux de chômage 2025 | **16 %** | Insee |
| Inflation 2025 | **+1,4 %** | IEDOM/Insee |
| Touristes 2024 | **556 534** | Observatoire |
| Part renouvelable | **96,2 %** | EDF Réunion |
| CO₂/habitant | **3,12 t** | OER |

---

## 📁 Structure du projet

```
.
├── index.html          # Fichier unique autoportant
├── README.md           # Ce fichier
├── LICENSE             # Licence du code (MIT recommandé)
└── .gitignore          # (optionnel)
```

---

## ⚖️ Cadre juridique

### Code source

Le code de ce dashboard est publié sous **licence MIT** (ou toute autre licence open source de votre choix). Vous pouvez le modifier, le redistribuer et l'utiliser commercialement.

### Données

Les données affichées proviennent de **sources publiques** sous **Licence Ouverte Etalab 2.0** :

- ✅ Réutilisation gratuite, y compris commerciale
- ✅ Rediffusion, publication, transmission autorisées
- ✅ Durée illimitée, monde entier
- ⚠️ **Obligation de mentionner la source** et la date de dernière mise à jour

### Mention obligatoire

> **Source : data.regionreunion.com — Licence Ouverte Etalab 2.0**

Cette mention est intégrée dans le footer du dashboard et dans les cartouches de source de chaque module.

### Avertissement

Ce dashboard **n'est pas un site officiel** de la Région Réunion, de l'État français ou de l'une des administrations citées. Il s'agit d'un outil de visualisation indépendant qui exploite des données ouvertes.

---

## ♿ Accessibilité

Ce dashboard vise la conformité **RGAA 4.1 niveau AA** :

- Contrastes de couleurs conformes
- Navigation clavier complète
- Focus visible sur tous les éléments interactifs
- Compatibilité lecteurs d'écran (structure sémantique)
- Zones tactiles ≥ 42 px sur mobile
- Respect de `prefers-reduced-motion`

---

## 🧪 Compatibilité navigateurs

| Navigateur | Version minimale |
|---|---|
| Chrome / Edge | 90+ |
| Firefox | 88+ |
| Safari | 14+ |
| Opera | 76+ |

Nécessite un navigateur supportant :
- `fetch()`
- `localStorage`
- CSS Grid & Flexbox
- `<canvas>` HTML5

---

## 🛠️ Stack technique

- **HTML5** sémantique
- **CSS3** — Grid, Flexbox, `clamp()`, variables CSS
- **JavaScript ES2020** — `async/await`, `Promise.all`, `Intl.NumberFormat`
- **Chart.js 4.4.0** — visualisations
- **API OpenDataSoft Explore v2.1** — source de données

Aucun framework, aucune dépendance npm, aucun build.

---

## 🤝 Contribution

Les contributions sont bienvenues :

1. Fork du dépôt
2. Créer une branche (`git checkout -b feature/nouveau-module`)
3. Commit (`git commit -m 'Ajout module XYZ'`)
4. Push (`git push origin feature/nouveau-module`)
5. Ouvrir une Pull Request

### Idées d'extension

- Ajout d'une carte interactive (Leaflet / MapLibre)
- Export PDF ou CSV des vues
- Comparaison multi-communes
- Alertes sur seuils (qualité air, chômage, etc.)
- Intégration du module **catalog** complet (108 outils mcp-reunion)

---

## 📜 Licence

```
MIT License

Copyright (c) 2026 [Votre nom]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📞 Contact

- **Issues GitHub** : [ouvrir une issue](https://github.com/<votre-utilisateur>/<nom-du-depot>/issues)
- **Région Réunion** : [www.regionreunion.com](https://www.regionreunion.com)
- **Portail Open Data** : [data.regionreunion.com](https://data.regionreunion.com)

---

<div align="center">

**République Française**
*Portail des données publiques — La Réunion*

Fait avec ❤️ pour la transparence des politiques publiques

</div>

---

<div align="center">

### 🇫🇷 Gunout · 2026

![Made in France](https://img.shields.io/badge/Made_in-France-002395?style=flat-square&labelColor=FFFFFF&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA5MDAgNjAwIj48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzAwMjM5NSIvPjxyZWN0IHdpZHRoPSI5MDAiIGhlaWdodD0iNDAwIiB5PSIxMDAiIGZpbGw9IiNmZmYiLz48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjIwMCIgeT0iNDAwIiBmaWxsPSIjZWQyOTM5Ii8+PC9zdmc+)
![GitHub](https://img.shields.io/badge/GitHub-gunout-181717?style=flat-square&logo=github&logoColor=white)
![Year](https://img.shields.io/badge/2026-ED2939?style=flat-square&labelColor=FFFFFF)

<sub>© 2026 <strong>Gunout</strong> — Tous droits réservés.</sub>

</div>
