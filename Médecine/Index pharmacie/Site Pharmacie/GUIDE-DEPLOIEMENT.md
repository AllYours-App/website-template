# Guide de Déploiement — Pharmacie Bois Belin

Guide étape par étape pour lancer votre site internet.

---

## ÉTAPE 1: Préparer le fichier HTML

Avant de déployer, vous devez finaliser le fichier HTML:

1. **Renommez le fichier principal**
   - Actuellement: `01-minimaliste-epure.html`
   - Renommez-le en: `index.html`
   - (C'est important pour que Vercel reconnaisse la page d'accueil)

2. **Configurez Formspree** (formulaire de contact)
   - ⚠️ **Important**: Le propriétaire de la pharmacie doit créer son propre compte Formspree
   - Le propriétaire va sur https://formspree.io
   - Crée un compte gratuit
   - Clique sur "New Form"
   - Donne un nom (ex: "Contact Pharmacie")
   - Copie l'URL fournie (ex: https://formspree.io/f/abcd1234)
   - Cette URL sera fournie au développeur pour remplacer dans le code
   - Dans `index.html` ligne 248, remplacez `https://formspree.io/f/REMPLACER_PAR_VOTRE_ID` par l'URL Formspree du propriétaire

3. **Vérifiez les informations légales**
   - Ligne 289: Vérifiez le numéro SIRET
   - Ligne 288: Vérifiez l'adresse exacte
   - Ligne 291: Vérifiez le responsable de publication

---

## ÉTAPE 2: Créer un dépôt GitHub

Si vous n'avez jamais utilisé Git, voici comment faire:

### Option A: Via l'interface web GitHub (plus simple pour débuter)

1. Allez sur https://github.com et connectez-vous
2. Cliquez sur le **+** en haut à droite → **New repository**
3. Remplissez:
   - **Repository name**: `pharmacie-bois-belin` (ou autre nom)
   - **Description**: Site internet de la Pharmacie Bois Belin
   - Laissez **Public** ou **Private** (Private est plus sûr)
4. Cliquez sur **Create repository**
5. Sur la page suivante, cliquez sur **uploading an existing file**
6. Glissez-déposez vos fichiers:
   - `index.html` (le fichier renommé)
   - `vercel.json`
   - `.gitignore`
   - `README.md`
7. Cliquez sur **Commit changes**

### Option B: Via la ligne de commande (plus avancé)

1. Installez Git: https://git-scm.com/downloads
2. Ouvrez un terminal dans le dossier du projet
3. Exécutez:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/VOTRE_USERNAME/pharmacie-bois-belin.git
   git push -u origin main
   ```

---

## ÉTAPE 3: Déployer sur Vercel

1. Allez sur https://vercel.com
2. Cliquez sur **Sign Up** (ou **Log In** si vous avez déjà un compte)
3. Connectez-vous avec votre compte GitHub
4. Cliquez sur **Add New...** → **Project**
5. Vous verrez la liste de vos dépôts GitHub
6. Cliquez sur **Import** à côté de votre dépôt `pharmacie-bois-belin`
7. Vercel analysera automatiquement votre projet
8. Cliquez sur **Deploy**
9. Attendez quelques secondes...
10. **Félicitations !** Votre site est en ligne !

Vous aurez une URL du type: `https://pharmacie-bois-belin.vercel.app`

---

## ÉTAPE 4: Connecter un nom de domaine (optionnel mais recommandé)

Si vous voulez un nom de domaine professionnel (ex: `pharmacie-bois-belin.fr`):

### 1. Acheter un nom de domaine

- **OVH**: https://www.ovh.com
- **Gandi**: https://www.gandi.net
- **Namecheap**: https://www.namecheap.com

Coût: ~10-15€/an pour un .fr

### 2. Connecter le domaine à Vercel

1. Dans Vercel, allez sur votre projet
2. Cliquez sur **Settings** → **Domains**
3. Cliquez sur **Add Domain**
4. Entrez votre nom de domaine (ex: pharmacie-bois-belin.fr)
5. Vercel vous donnera des instructions DNS:
   - Soit un enregistrement CNAME
   - Soit des enregistrements A
6. Allez chez votre registrar (OVH, Gandi, etc.)
7. Ajoutez les enregistrements DNS fournis par Vercel
8. Attendez quelques minutes à quelques heures (propagation DNS)

---

## ÉTAPE 5: Vérifier et tester

1. **Testez le formulaire de contact**
   - Allez sur votre site
   - Remplissez le formulaire
   - Vérifiez que vous recevez l'email via Formspree

2. **Testez sur mobile**
   - Ouvrez votre site sur un smartphone
   - Vérifiez que tout s'affiche correctement

3. **Vérifiez les liens**
   - Google Maps
   - Téléphone
   - Navigation entre les pages

---

## ÉTAPE 6: SEO (Référencement Google)

Pour que votre site apparaisse dans Google:

1. **Google Search Console**
   - Allez sur https://search.google.com/search-console
   - Ajoutez votre site
   - Vérifiez la propriété (via un fichier HTML ou DNS)
   - Soumettez votre sitemap (optionnel pour un site simple)

2. **Google My Business**
   - Mettez à jour votre fiche Google Maps
   - Ajoutez le lien vers votre site web
   - Ajoutez des photos de la pharmacie

3. **Mots-clés**
   - Votre site contient déjà des mots-clés pertinents:
     - "Pharmacie Anglet"
     - "Vaccination"
     - "Tests rapides"
     - "Livraison à domicile"

---

## Coût total

- **Hébergement Vercel**: 0€ (gratuit)
- **Formspree**: 0€ (gratuit jusqu'à 50 messages/mois)
- **Nom de domaine**: 10-15€/an (optionnel)
- **Total**: 0€ sans nom de domaine, ou ~10-15€/an avec nom de domaine

---

## Maintenance

Une fois le site en ligne:

- **Mettre à jour les horaires** si nécessaire
- **Modifier les services** si vous en ajoutez
- **Mettre à jour les mentions légales** si des changements

Pour faire une mise à jour:
1. Modifiez le fichier `index.html`
2. Poussez les changements sur GitHub
3. Vercel déploiera automatiquement la nouvelle version

---

## Problèmes fréquents

### Le formulaire ne fonctionne pas
- Vérifiez que vous avez bien remplacé l'ID Formspree
- Vérifiez que Formspree est activé

### Le site ne se met pas à jour
- Vérifiez que vous avez bien poussé les changements sur GitHub
- Allez sur Vercel et vérifiez les déploiements récents

### Le nom de domaine ne fonctionne pas
- Attendez la propagation DNS (peut prendre jusqu'à 24h)
- Vérifiez les enregistrements DNS chez votre registrar

---

## Besoin d'aide ?

- **Documentation Vercel**: https://vercel.com/docs
- **Documentation GitHub**: https://docs.github.com
- **Documentation Formspree**: https://formspree.io/docs

---

Bon déploiement ! 🚀
