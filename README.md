# Templates de sites vitrine — trame réutilisable

Trois bases prêtes à l'emploi pour démarrer un site client rapidement. Même logique de structure pour les trois (header → hero → contenu → contact), mais identité visuelle propre à chaque secteur.

- `artisan/index.html` → boulangers, artisans, producteurs locaux (ton chaleureux, tons bois/blé)
- `medical/index.html` → pharmacies, professions médicales (ton sobre/rassurant, statut ouvert/fermé en avant)
- `sport/index.html` → écoles de sport, coachs, clubs (ton énergique, orienté réservation)

## Comment personnaliser un template pour un nouveau client

1. **Copie le dossier du secteur concerné** dans un nouveau repo GitHub.
2. **Cherche les commentaires `<!-- À PERSONNALISER -->`** dans le fichier HTML — ils marquent les endroits où remplacer nom, adresse, téléphone, horaires.
3. **Remplace les `photo-placeholder`** par de vraies photos (balise `<img src="...">` à la place du `<div class="photo-placeholder">`).
4. **Ajuste les couleurs** si besoin dans le bloc `:root{ }` en haut du fichier — tout le reste du design suit automatiquement ces variables.
5. **Intègre une vraie carte** à la place du `map-placeholder` : Google Maps propose un code `<iframe>` à coller (Partager → Intégrer une carte, sur n'importe quelle fiche Google Maps).

## Déployer sur Vercel

1. Pousse le dossier sur un nouveau repo GitHub (un repo par client, ou un seul repo "template" que tu marques comme **Template repository** dans les paramètres GitHub, pour cliquer "Use this template" à chaque nouveau client).
2. Sur vercel.com → "New Project" → importe le repo. Comme c'est du HTML pur, aucune configuration de build n'est nécessaire.
3. Une fois déployé, tu peux brancher un nom de domaine personnalisé dans les réglages du projet Vercel.

## Pour montrer plusieurs designs à un client

Duplique le template choisi 2-3 fois en changeant juste les couleurs dans `:root{ }`, déploie chaque variante sur une URL Vercel de preview, et envoie les liens au client pour qu'il compare en vrai sur son téléphone.

## Pages légales incluses

Chaque dossier contient maintenant deux pages supplémentaires, liées en pied de page :

- `mentions-legales.html` — obligatoire en France pour tout site professionnel (loi LCEN), même sans vente en ligne.
- `confidentialite.html` — politique de confidentialité / RGPD, nécessaire car le formulaire de contact collecte des données personnelles (nom, email, message).

**Important** : ces deux pages contiennent des passages `[À compléter]` (SIRET, durée de conservation, etc.) à remplir avec les vraies informations du client avant mise en ligne définitive. Ce sont des bases de travail, pas un document validé juridiquement — pour un commerce qui se lance réellement, ça vaut le coup de faire relire la version finale par un professionnel (expert-comptable ou avocat), surtout si l'activité grandit.

## Aller plus loin : connecter le formulaire de contact

Les formulaires de contact sont pour l'instant statiques (`alert()` au clic). Comme tu utilises déjà Supabase, tu peux les connecter pour stocker les messages reçus :
- crée une table `contacts` (colonnes : `name`, `email`, `message`, `created_at`),
- remplace le `onsubmit` du formulaire par un appel à l'API Supabase (`supabase.from('contacts').insert(...)`),
- ça te permet de proposer une vraie fonctionnalité "demandes reçues" au client, sans dépendre d'un service tiers payant.
