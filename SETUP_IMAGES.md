# 📸 Guide : Ajouter vos images aux projets

## Structure des dossiers

Créez cette structure à la racine du projet :

```
portfolio/
├── images/
│   ├── nmos-transistor.png      # Transistor NMOS
│   ├── antenne-rf.png            # Antenne RF
│   ├── etuve-pid.png             # Étuve PID
│   ├── microbatteries.png        # Microbatteries
│   ├── portfolio-preview.png     # (Optionnel) Aperçu du portfolio
│   └── projects/                 # Optionnel: sous-dossier pour projets
│       ├── nmos/
│       ├── antenne/
│       ├── etuve/
│       └── batteries/
```

## Étapes pour ajouter les images

### 1. Créer le dossier `images/`
```bash
mkdir images
```

### 2. Ajouter vos images
Placez vos images dans le dossier `images/` :
- Les fichiers doivent être en `.png`, `.jpg`, `.webp`
- Nommez-les selon les noms utilisés dans le HTML

### 3. Les chemins dans le HTML
Les images sont déjà configurées dans les fichiers HTML :

```html
<!-- Dans projets.html -->
<div class="project-image">
  <img src="images/nmos-transistor.png" alt="Transistor NMOS microfabriqué" loading="lazy">
</div>
```

### 4. Optimiser vos images

#### Avec ImageMagick (en ligne de commande)
```bash
# Redimensionner et compresser JPG
convert original.jpg -quality 85 -resize 1200x800 images/nmos-transistor.jpg

# Convertir en WebP (meilleur format)
convert original.jpg -quality 85 images/nmos-transistor.webp
```

#### Outils en ligne (gratuit, pas d'installation)
- **TinyPNG** : https://tinypng.com/
- **Squoosh** (Google) : https://squoosh.app/
- **ImageOptim** (Mac) : https://imageoptim.com/

#### Recommandations de taille
| Type d'image | Largeur | Format | Taille max |
|---|---|---|---|
| Project hero image | 1200px | WebP | 150-250 KB |
| Project card image | 600px | WebP | 50-100 KB |
| Screenshot | 800px | PNG | 100-200 KB |

### 5. Formato WebP (recommandé)

WebP offre une meilleure compression que PNG/JPG.

```bash
# Convertir JPG vers WebP
cwebp original.jpg -o images/nmos-transistor.webp

# Convertir PNG vers WebP
cwebp original.png -o images/nmos-transistor.webp
```

Puis modifiez le HTML :
```html
<img src="images/nmos-transistor.webp" alt="Transistor NMOS microfabriqué" loading="lazy">
```

## Images responsive avec picture tag

Pour supporter plusieurs résolutions :

```html
<picture>
  <source srcset="images/nmos-transistor-mobile.webp" media="(max-width: 600px)">
  <source srcset="images/nmos-transistor.webp">
  <img src="images/nmos-transistor.png" alt="Transistor NMOS" loading="lazy">
</picture>
```

## Gestion des images dans Git

```bash
# Ajouter le dossier images
git add images/

# Ignorer les fichiers volumineux (optionnel)
# Créez un .gitattributes pour les gros fichiers
git lfs track "*.webp"
git lfs track "images/**/*.{jpg,png,webp}"
```

## Exemple : Ajouter une image d'un projet

### Avant (sans image)
```html
<div class="project-image">
  <img src="images/antenne-rf.png" alt="Antenne RF 2.5 GHz" loading="lazy">
</div>
```

### Après optimisation
1. Prenez une photo/screenshot du projet
2. Optimisez-la avec Squoosh :
   - Redimensionnez à 800-1200px
   - Convertissez en WebP
   - Compression 80-85%
3. Placez le fichier dans `images/antenne-rf.webp`
4. Modifiez le HTML si nécessaire

## Placeholder automatique

Si une image est manquante, un placeholder s'affiche automatiquement grâce au JavaScript :

```javascript
img.addEventListener('error', function() {
  this.style.display = 'none';
  this.parentElement.innerHTML = 
    '<div style="...">📸 Image du projet à ajouter<br><small>...</small></div>';
});
```

## Committer et pusher les images

```bash
# Ajouter les images
git add images/

# Commit
git commit -m "Add project images"

# Push vers GitHub
git push origin main
```

## Troubleshooting

### Les images ne s'affichent pas
1. ✓ Vérifiez que le dossier `images/` existe
2. ✓ Vérifiez les chemins dans le HTML (`src="images/..."`)
3. ✓ Vérifiez l'orthographe des noms de fichiers
4. ✓ Utilisez `git add images/` pour les committer

### Les images sont trop lourdes
1. Réduisez la résolution avec ImageMagick ou Squoosh
2. Utilisez le format WebP au lieu de PNG/JPG
3. Réduisez la qualité à 80-85%

### Les images ne s'affichent après push GitHub
1. Attendez 1-2 minutes pour le cache GitHub
2. Videz le cache du navigateur (Ctrl+F5 / Cmd+Shift+R)
3. Vérifiez que les fichiers sont bien dans le repo sur GitHub

## Exemple complet : Ajout d'une image

```bash
# 1. Créer le dossier
mkdir -p images

# 2. Optimiser l'image (avec ImageMagick)
convert mon-photo-transistor.jpg -quality 85 -resize 1000x -o images/nmos-transistor.jpg

# 3. Vérifier que ça marche en local
# Ouvrir index.html dans le navigateur

# 4. Committer
git add images/
git commit -m "Add NMOS transistor image"
git push

# 5. Vérifier sur GitHub Pages
# https://seydina-kane.github.io
```

---

**Besoin d'aide ?** Consultez la section "Ajouter des images" du README.md principal.
