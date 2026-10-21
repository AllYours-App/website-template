# Template Site Internet — Pharmacie

Template de site internet moderne et minimaliste pour pharmacies. Facilement personnalisable pour n'importe quelle pharmacie.

## 🚀 Démarrage Rapide

1. **Personnalisez le site** en remplaçant les placeholders dans `index.html`
   - Consultez le [GUIDE-PERSONNALISATION.md](GUIDE-PERSONNALISATION.md) pour la liste complète des placeholders
   - Utilisez la fonction "Rechercher et remplacer" de votre éditeur

2. **Configurez le formulaire de contact**
   - Le propriétaire de la pharmacie crée un compte Formspree: https://formspree.io
   - Remplacez `REMPLACER_PAR_VOTRE_ID` dans `index.html` ligne 248 par l'ID Formspree

3. **Déployez sur Vercel**
   - Consultez le [GUIDE-DEPLOIEMENT.md](GUIDE-DEPLOIEMENT.md) pour les instructions détaillées

## 📋 Prérequis avant le déploiement

1. **Compte Formspree** (pour le formulaire de contact)
   - ⚠️ Le propriétaire de la pharmacie doit créer son propre compte Formspree
   - Le propriétaire crée un compte sur https://formspree.io
   - Crée un nouveau formulaire
   - Copie l'ID du formulaire (ex: https://formspree.io/f/abcd1234)
   - Fournit cet ID au développeur pour remplacer `REMPLACER_PAR_VOTRE_ID` dans `index.html` ligne 248

2. **Informations à personnaliser**
   - Remplacez tous les placeholders dans `index.html` (voir GUIDE-PERSONNALISATION.md)
   - SIRET réel de la pharmacie
   - Adresse exacte
   - Numéro de téléphone
   - Nom du responsable de publication

3. **Nom de domaine** (optionnel mais recommandé)
   - Achetez un nom de domaine (ex: pharmacie-bois-belin.fr)
   - Coût: ~10-15€/an chez OVH, Gandi, Namecheap

## 🚀 Déploiement sur Vercel

### Option 1: Via GitHub (recommandé)

1. **Créer un dépôt GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   # Créez un dépôt sur github.com, puis:
   git remote add origin https://github.com/VOTRE_USERNAME/pharmacie-bois-belin.git
   git branch -M main
   git push -u origin main
   ```

2. **Connecter GitHub à Vercel**
   - Allez sur https://vercel.com
   - Connectez-vous avec GitHub
   - Cliquez sur "Add New Project"
   - Sélectionnez votre dépôt GitHub
   - Cliquez sur "Deploy"

3. **Connecter votre nom de domaine** (si vous en avez un)
   - Dans Vercel, allez dans Settings > Domains
   - Ajoutez votre nom de domaine
   - Suivez les instructions DNS fournies par Vercel

### Option 2: Déploiement direct via Vercel CLI

1. **Installer Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Déployer**
   ```bash
   vercel
   # Suivez les instructions
   ```

## 📝 Après le déploiement

1. **Google Search Console**
   - Ajoutez votre site à https://search.google.com/search-console
   - Soumettez le sitemap (si vous en créez un)

2. **Google My Business**
   - Mettez à jour votre fiche Google Maps avec le lien vers votre site

3. **Testez le formulaire**
   - Envoyez un message via le formulaire pour vérifier qu'il fonctionne

## 📁 Structure du projet

```
.
├── index.html          # Page principale (à renommer depuis 01-minimaliste-epure.html)
├── vercel.json         # Configuration Vercel
├── .gitignore          # Fichiers à ignorer par Git
└── README.md           # Ce fichier
```

## 🔧 Personnalisation

- **Couleurs**: Modifiez les variables CSS dans `:root` (lignes 11-17)
- **Textes**: Modifiez directement le contenu HTML
- **Images**: Ajoutez des images dans le dossier et référencez-les dans le HTML

## 💡 Coûts

- **Hébergement Vercel**: Gratuit (plan Hobby)
- **Nom de domaine**: ~10-15€/an (optionnel)
- **Formspree**: Gratuit jusqu'à 50 soumissions/mois
- **Total**: 0€ si vous utilisez l'URL vercel.app, ou ~10-15€/an avec nom de domaine personnalisé

## 📞 Support

Pour toute question sur le déploiement, consultez la documentation Vercel: https://vercel.com/docs
