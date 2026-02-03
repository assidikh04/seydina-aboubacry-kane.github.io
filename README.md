# Portfolio - Seydina Aboubacry Kane

Portfolio professionnel d'un étudiant en BUT GEII (Génie Électrique et Informatique Industrielle) et apprenti au CEA-Leti, spécialisé en électronique, microélectronique et systèmes embarqués.

## 🌐 Visite le portfolio

[👉 Voir le portfolio en ligne](https://seydina-aboubacry--kane.github.io)

## 📋 À propos

Je suis actuellement :
- **Étudiant en 3e année** du BUT GEII à l'Université Grenoble Alpes (UGA)
- **Apprenti ingénieur** au CEA-Leti (Commissariat à l'Énergie Atomique et aux Énergies Alternatives)
- Spécialisé en **électronique**, **microélectronique** et **systèmes embarqués**

### 🎯 Domaines d'expertise

- **Électronique & Microélectronique**
  - Conception de circuits analogiques
  - Microfabrication de transistors (NMOS)
  - Caractérisation électrique et RF
  - Packaging et wire bonding

- **Systèmes Embarqués**
  - Programmation C/C++ pour microcontrôleurs
  - Contrôle PID et régulation
  - Python pour analyse de données

- **Outils & Logiciels**
  - KiCad / Altium (CAO électronique)
  - SILVACO Athena (simulation process)
  - Analyseur VNA et oscilloscope
  - Git / GitHub

## 📁 Structure du projet

```
portfolio/
├── index.html           # Page d'accueil
├── competences.html     # Page compétences avec barres de progression
├── projets.html         # Page projets détaillés
├── experiences.html     # Page formation et expérience
├── style.css            # Feuille de styles CSS
├── images/              # Dossier pour les images des projets
│   ├── nmos-transistor.png
│   ├── antenne-rf.png
│   ├── etuve-pid.png
│   └── microbatteries.png
├── README.md            # Ce fichier
└── .gitignore           # Fichiers à ignorer par Git
```

## 🚀 Projets en vedette

### 1. Transistor NMOS Microfabriqué
- **Technologies** : SILVACO Athena, Salle blanche CIME Nanotech
- **Résultats** : Simulation et fabrication complète de transistors avec grilles 1-10 µm
- **Compétences** : Microfabrication, caractérisation électrique, analyse de résultats

### 2. Antenne RF 2.5 GHz
- **Technologies** : Conception RF, Analyseur VNA
- **Résultats** : Mesure S11/S21, validation des performances
- **Compétences** : Conception RF, instrumentation, paramètres S

### 3. Étuve Régulée PID à 37°C
- **Technologies** : Régulation PID, Instrumentation thermique
- **Résultats** : Stabilisation précise à 37°C, temps de montée 48 min
- **Compétences** : Régulation, contrôle en temps réel, optimisation

### 4. Caractérisation de Microbatteries
- **Technologies** : CEA-Leti, Wire bonding, Packaging
- **Résultats** : Procédés de packaging optimisés
- **Compétences** : Wire bonding, packaging, tests électriques

## 🛠️ Technologies utilisées

### Frontend
- **HTML5** - Structure sémantique moderne
- **CSS3** - Design responsive avec gradients et animations
- **Vanilla JavaScript** - Animations et interactions

### Design
- Dark theme moderne et professionnel
- Design responsive (mobile, tablette, desktop)
- Animations fluides avec CSS transitions
- Gradient colors (purple & pink)

## 📱 Caractéristiques

✅ **Design responsive** - Fonctionne sur tous les appareils  
✅ **Sombre & moderne** - Dark theme professionnel  
✅ **Performance** - Chargement rapide, optimisé  
✅ **Accessibilité** - Navigation claire et intuitive  
✅ **SEO friendly** - Métadonnées complètes  
✅ **Support des images** - Dossier d'images pour les projets  

## 🎨 Customisation

### Ajouter des images aux projets
1. Créez un dossier `images/` à la racine
2. Placez vos images (PNG, JPG, WebP)
3. Les images s'affichent automatiquement
4. S'il y a une erreur, un placeholder s'affiche

```html
<div class="project-image">
  <img src="images/votre-image.png" alt="Description">
</div>
```

### Modifier les couleurs
Cherchez les variables de couleur dans `style.css` :
- Gradient purple-pink : `#a855f7`, `#ec4899`
- Text clair : `#f9fafb`, `#cbd5e1`
- Background sombre : `#020617`, `#0f172a`

### Ajouter des projets
1. Ouvrez `projets.html`
2. Dupliquez un `<article class="project-card">`
3. Remplissez avec vos informations
4. Assignez un ID unique pour la navigation

## 🚀 Déploiement sur GitHub Pages

### 1. Créer un dépôt GitHub
```bash
git init
git add .
git commit -m "Initial commit: portfolio"
git branch -M main
git remote add origin https://github.com/seydina-kane/portfolio.git
git push -u origin main
```

### 2. Activer GitHub Pages
1. Allez dans `Settings` → `Pages`
2. Sélectionnez `main` comme source
3. Confirmez (votre site sera à `https://seydina-kane.github.io`)

### 3. (Optionnel) Domaine personnalisé
1. Créez un fichier `CNAME` à la racine
2. Écrivez votre domaine (ex: `seydina-kane.com`)
3. Configurez votre registrar DNS

## 📂 Ajouter vos images

### Étapes :
1. Créez un dossier `images/` dans le repo
2. Compressez vos images avant upload (webp de préférence)
3. Mettez à jour les chemins dans le HTML
4. Committez avec `git add images/` et `git push`

### Formats recommandés :
- `.webp` - Meilleure compression (recommandé)
- `.png` - Pour transparence
- `.jpg` - Pour photos

### Compression d'images :
```bash
# Avec ImageMagick
convert image.jpg -quality 85 -resize 1200x800 image-optimized.jpg

# Ou utiliser des outils en ligne:
# - TinyPNG
# - Squoosh (Google)
```

## 📊 Statistiques du portfolio

- **Pages** : 4 (Accueil, Compétences, Projets, Expérience)
- **Projets** : 4 projets détaillés
- **Compétences** : 15+ domaines couverts
- **Responsive** : Mobile, Tablette, Desktop

## 🔧 Améliorations futures

- [ ] Blog/Articles techniques
- [ ] Galerie interactive des projets
- [ ] Formulaire de contact
- [ ] Dark/Light mode toggle
- [ ] Animation parallaxe
- [ ] Intégration GitHub API
- [ ] Section "En savoir plus" avec liens externes

## 📝 Licence

Ce portfolio est distribué sous licence MIT. Libre d'utilisation à titre personnel ou professionnel.

## 📞 Contact

- **GitHub** : [@seydina-kane](https://github.com/seydina-aboubacry-kane)
- **Email** : [kaneaboubacry903@gmail.com]
- **LinkedIn** : [www.linkedin.com/in/seydina-aboubacry-kane]
- **Location** : Grenoble, France

---

**© 2026 · Seydina Aboubacry Kane**

*Portfolio BUT GEII & CEA-Leti · Électronique & Microélectronique*
