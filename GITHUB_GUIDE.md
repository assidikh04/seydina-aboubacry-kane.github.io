# 🚀 Guide complet : Mettre votre portfolio sur GitHub

Ce guide vous accompagne étape par étape pour publier votre portfolio sur GitHub et l'héberger gratuitement avec GitHub Pages.

## Table des matières
1. [Prérequis](#prérequis)
2. [Créer un compte GitHub](#créer-un-compte-github)
3. [Configurer Git](#configurer-git)
4. [Créer le dépôt](#créer-le-dépôt)
5. [Pousser le code](#pousser-le-code)
6. [Activer GitHub Pages](#activer-github-pages)
7. [Domaine personnalisé (optionnel)](#domaine-personnalisé)
8. [Maintenance](#maintenance)

---

## 🔧 Prérequis

Vous devez avoir :
- ✓ Un compte GitHub (gratuit)
- ✓ Git installé sur votre ordinateur
- ✓ Tous les fichiers du portfolio

### Installer Git

**Windows** :
1. Téléchargez depuis https://git-scm.com/download/win
2. Installez en gardant les paramètres par défaut
3. Ouvrez "Git Bash" après l'installation

**Mac** :
```bash
# Avec Homebrew
brew install git

# Ou : installez Xcode Command Line Tools
xcode-select --install
```

**Linux (Debian/Ubuntu)** :
```bash
sudo apt update
sudo apt install git
```

---

## 👤 Créer un compte GitHub

1. Allez sur https://github.com
2. Cliquez sur **"Sign up"**
3. Entrez votre email
4. Créez un mot de passe sécurisé
5. Choisissez un **username** (recommandé: `seydina-kane`)
6. Complétez la vérification
7. Validez votre email

**Votre profil GitHub** sera à : `https://github.com/votre-username`

---

## ⚙️ Configurer Git

Configurez Git avec vos informations :

```bash
# Configurez votre nom
git config --global user.name "Seydina Aboubacry Kane"

# Configurez votre email
git config --global user.email "votre.email@example.com"

# Vérifiez la configuration
git config --global --list
```

### Setup SSH (optionnel mais recommandé)

Pour éviter de saisir votre mot de passe à chaque push :

```bash
# Générer une clé SSH
ssh-keygen -t ed25519 -C "votre.email@example.com"

# Appuyez sur Entrée 3 fois (pas de passphrase)

# Copier la clé publique (macOS)
cat ~/.ssh/id_ed25519.pub | pbcopy

# Ou sous Linux/Windows (Git Bash)
cat ~/.ssh/id_ed25519.pub
# Copiez manuellement
```

Puis sur GitHub :
1. Allez sur Settings → SSH and GPG keys
2. Cliquez "New SSH key"
3. Collez votre clé
4. Cliquez "Add SSH key"

---

## 📂 Créer le dépôt GitHub

### Via l'interface web (recommandé pour débutants)

1. Connectez-vous sur https://github.com
2. Cliquez le **+** en haut à droite
3. Sélectionnez **"New repository"**
4. Remplissez les informations :
   - **Repository name** : `portfolio` (ou `seydina-kane.github.io`)
   - **Description** : "Portfolio professionnel - Électronique & Microélectronique"
   - **Public** : ✓ (pour que ce soit visible)
   - **Initialize with README** : ✗ (on l'aura déjà)
5. Cliquez **"Create repository"**

**Note importante** : Si vous voulez utiliser `https://votre-username.github.io`, 
nommez le dépôt exactement `seydina-kane.github.io`

### Repositories recommandés

| Nom du repo | URL du site |
|---|---|
| `portfolio` | `https://github.com/seydina-kane/portfolio` |
| `seydina-kane.github.io` | `https://seydina-kane.github.io` |

---

## 📤 Pousser le code sur GitHub

### Étape 1 : Initialiser le repo local

Ouvrez le terminal dans le dossier de votre portfolio :

```bash
# Allez dans le dossier du portfolio
cd /chemin/vers/portfolio

# Initialisez Git
git init

# Ajoutez tous les fichiers
git add .

# Vérifiez ce qui a été ajouté
git status
```

### Étape 2 : Créer le premier commit

```bash
# Créez un commit initial
git commit -m "Initial commit: portfolio template"

# Ou avec une meilleure description
git commit -m "Initial commit: portfolio professionnel

- Pages: Accueil, Compétences, Projets, Expérience
- Design: Dark theme responsive
- 4 projets détaillés
- Structure prête pour GitHub Pages"
```

### Étape 3 : Connecter au dépôt GitHub

Remplacez `seydina-kane` par votre username et `portfolio` par le nom du repo :

#### Avec HTTPS (si pas de SSH)
```bash
git branch -M main
git remote add origin https://github.com/seydina-kane/portfolio.git
```

#### Avec SSH (recommandé)
```bash
git branch -M main
git remote add origin git@github.com:seydina-kane/portfolio.git
```

### Étape 4 : Pousser le code

```bash
# Poussez la branche main
git push -u origin main

# Vous devez vous authentifier :
# - HTTPS : entrez votre username et mot de passe (ou token)
# - SSH : vous êtes directement authentifié
```

### Étape 5 : Vérifiez sur GitHub

1. Allez sur https://github.com/seydina-kane/portfolio
2. Vous devez voir tous vos fichiers
3. Les commits sont visibles dans l'onglet "Commits"

---

## 📰 Activer GitHub Pages

### Méthode 1 : Settings (moderne)

1. Allez sur votre dépôt GitHub
2. Cliquez sur **"Settings"** (onglet à droite)
3. Dans la barre de gauche, cliquez **"Pages"**
4. Sous "Build and deployment" :
   - **Source** : Sélectionnez "Deploy from a branch"
   - **Branch** : Sélectionnez `main` et `/root`
5. Cliquez **"Save"**

GitHub déploie automatiquement ! Vous verrez un lien :
```
Your site is published at: https://seydina-kane.github.io
```

### Méthode 2 : Avec Actions (plus rapide)

1. Allez sur **"Actions"**
2. Cliquez **"set up a workflow yourself"**
3. Remplacez par ce workflow :

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./
```

4. Cliquez **"Commit changes"**

### Vérifier le déploiement

1. Allez sur **"Actions"**
2. Attendez que le workflow se termine (checkmark vert)
3. Votre site est en direct ! 🎉

Le lien est généralement : `https://seydina-kane.github.io/portfolio`
(ou `https://seydina-kane.github.io` si vous avez nommé le repo `seydina-kane.github.io`)

---

## 🌐 Domaine personnalisé (optionnel)

### Utiliser votre propre domaine

Si vous avez un domaine comme `seydina-kane.com` :

#### Étape 1 : Créer un fichier CNAME

1. Créez un fichier nommé `CNAME` à la racine
2. Écrivez votre domaine (une seule ligne) :
```
seydina-kane.com
```

3. Committez et poussez :
```bash
git add CNAME
git commit -m "Add custom domain"
git push
```

#### Étape 2 : Configurer votre registrar

Allez sur le site où vous avez acheté votre domaine (Namecheap, OVH, etc.) :

1. Trouvez "DNS Management" ou "Zone DNS"
2. Créez 4 enregistrements `A` pointant vers :
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`

3. Créez un enregistrement `CNAME` :
   - **Host** : `www`
   - **Value** : `seydina-kane.github.io.`

#### Étape 3 : Vérifier dans GitHub

1. Allez sur Settings → Pages
2. Sous "Custom domain", entrez votre domaine
3. Cochez "Enforce HTTPS"
4. Patientez 24-48h pour la propagation DNS

Votre site sera maintenant à `https://seydina-kane.com` 🎉

---

## 🔄 Maintenance & Mises à jour

### Ajouter des modifications

Après chaque changement :

```bash
# Vérifiez les modifications
git status

# Ajoutez les fichiers modifiés
git add .

# Ou fichier par fichier
git add competences.html
git add style.css

# Committez
git commit -m "Description des changements"

# Poussez
git push
```

### Exemples de commit

```bash
# Ajouter une image
git commit -m "Add project images"

# Modifier une page
git commit -m "Update projects page with new content"

# Bug fix
git commit -m "Fix responsive design on mobile"

# Feature
git commit -m "Add dark/light mode toggle"
```

### Historique des commits

```bash
# Voir tous les commits
git log

# Voir les commits formattés
git log --oneline --graph

# Voir les changements d'un commit spécifique
git show HASH
```

### Restaurer une version antérieure

```bash
# Voir le commit à restaurer
git log --oneline

# Revenir à une version antérieure
git revert HASH

# Ou réinitialiser (attention!)
git reset --hard HASH
```

---

## 📊 Exemple complet de déploiement

```bash
# 1. Préparation
mkdir portfolio
cd portfolio
cp style.css index.html competences.html projets.html experiences.html .
cp README.md .gitignore .

# 2. Initialiser Git
git init
git add .
git commit -m "Initial commit: portfolio"

# 3. Créer le dépôt sur GitHub
# Via l'interface web : https://github.com/new

# 4. Connecter et pousser
git branch -M main
git remote add origin https://github.com/seydina-kane/portfolio.git
git push -u origin main

# 5. Activer GitHub Pages
# Via Settings → Pages

# 6. Vérifier
# https://seydina-kane.github.io/portfolio ✅
```

---

## 🐛 Troubleshooting

### "fatal: not a git repository"
```bash
cd /chemin/vers/portfolio
git init
```

### "refusing to merge unrelated histories"
```bash
git pull --allow-unrelated-histories
```

### Les changements n'apparaissent pas
```bash
# Videz le cache
git clean -fd
git reset --hard HEAD

# Re-poussez
git push --force
```

### GitHub Pages ne déploie pas
1. Vérifiez que c'est en **public**
2. Vérifiez que **main** est la branche par défaut (Settings → Branches)
3. Vérifiez que **index.html** existe à la racine
4. Attendez 1-2 minutes pour le déploiement

### HTTPS ne fonctionne pas
1. Attendez 10 minutes pour le certificat SSL
2. Cochez "Enforce HTTPS" dans Settings → Pages

---

## 📚 Ressources supplémentaires

- **Git Documentation** : https://git-scm.com/doc
- **GitHub Help** : https://docs.github.com
- **GitHub Pages** : https://pages.github.com
- **Markdown Guide** : https://markdownguide.org/

---

## ✅ Checklist finale

- [ ] Compte GitHub créé
- [ ] Git installé et configuré
- [ ] Fichiers du portfolio prêts
- [ ] Dépôt GitHub créé
- [ ] Code poussé sur GitHub
- [ ] GitHub Pages activé
- [ ] Site accessible en ligne
- [ ] Images ajoutées (optionnel)
- [ ] Domaine personnalisé configuré (optionnel)

---

**Félicitations ! 🎉 Votre portfolio est en ligne !**

Partagez le lien : `https://seydina-kane.github.io/portfolio`

---

*Pour toute question, consultez la documentation officielle GitHub ou contactez le support.*
