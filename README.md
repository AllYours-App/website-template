# Bibliothèque de templates de sites vitrines

Templates HTML/CSS pour sites vitrines de petites entreprises locales. Quand un client arrive avec un métier, on part d'un template déjà structuré au lieu d'une page blanche.

Ce README fixe les règles communes à tous les templates. Chaque secteur a son propre README (`artisan/README-artisan.md`, `commerce/README-commerce.md`, `medecine/README-medecine.md`, `sport/README-sport.md`) avec les consignes et les éléments indispensables du métier. **Les deux se lisent avant de créer ou de modifier un template.** En cas de conflit, le README du secteur l'emporte.

Le workflow Unbounded des wireframes (socle commun, checklist client, conventions Client-First) est détaillé dans `README template type.md`.

---

## 1. Structure

```
website-template/
├── README.md
├── README template type.md
├── _docs/                  guides (déploiement, personnalisation)
├── _shared/                pages légales uniques, vercel.json
├── _archive/               anciennes versions, ne pas utiliser
└── <secteur>/              niveau 1 : artisan, commerce, medecine, sport
    ├── README-<secteur>.md consignes du secteur
    ├── _type/              niveau 2 : template type du secteur
    │   └── <layout>/       niveau 3 : un dossier par layout (5)
    │       └── <secteur>-type-<layout>.html
    └── <metier>/           niveau 2 : macon, pharmacie, coiffeur...
        ├── <layout>/       niveau 3 : mêmes 5 dossiers de layout
        │   └── <secteur>-<metier>-<layout>-<design>.html   niveau 4 : un fichier par design
        └── <secteur>-<metier>-a-classer-<design>.html      layout pas encore défini
```

| Niveau | Contenu | Rôle |
|---|---|---|
| 1 | Secteur | Regroupe les métiers qui partagent le même ton et les mêmes obligations |
| 2 | Métier ou `_type` | `_type` sert de repli quand le métier du client n'existe pas encore |
| 3 | Layout (dossier) | Organisation de la page : position, taille, hiérarchie des éléments |
| 4 | Design (fichier) | Habillage : couleurs, typographies, formes, ton visuel. Un fichier par design, dans le dossier de son layout |

**Les 5 dossiers de layout existent dans chaque `_type` et chaque métier, même vides.** Git ne conserve pas les dossiers vides : chacun contient un fichier `.gitkeep` (fichier vide).

Un fichier dont le layout n'est pas encore défini se pose directement dans le dossier du métier, avec `a-classer` à la place du layout. Il rejoint son dossier de layout quand il est classé.

**Layout et design sont deux axes distincts.** Test : si on retire les couleurs et les polices, deux layouts d'un même métier doivent encore se distinguer par la structure. Deux designs d'un même layout ont la même structure et un habillage différent.

---

## 2. Nommage

- Dossiers et fichiers en kebab-case, sans accents, sans espaces, sans majuscules (`medecine`, `ecole-surf`, `split-z`).
- Un fichier de template porte le chemin complet : `<secteur>-<metier>-<layout>-<design>.html`.
  Exemple : `medecine-pharmacie-cartes-sombre.html`.
- Template type : `<secteur>-type-<layout>.html`. Exemple : `artisan-type-hero-plein-ecran.html`.
- Le design est un **type générique** (`minimaliste`, `chaud`, `sombre`, `dynamique`, `naturel`), jamais un nom de client, de lieu ou de boutique.
- Si deux fichiers du même métier et du même layout ont le même type de design, le second prend le suffixe `-2` (puis `-3`). Le suffixe se retire quand les fichiers sont classés dans des layouts différents.
- Layout pas encore défini : `a-classer` dans le nom, fichier posé à la racine du dossier du métier.
- Au déploiement, le fichier est renommé `index.html`.

---

## 3. Layouts et types de design de référence

Chaque layout met en avant **un élément différent** par sa position, sa taille et son poids dans la page, pas par ses couleurs. Minimum **5 layouts** dans chaque `_type`. Un métier reprend le même vocabulaire.

| Slug | Structure | Élément mis en avant | Adapté à |
|---|---|---|---|
| `one-page` | Page unique, sections empilées | L'offre de services | Artisan solo, indépendant, petit prestataire |
| `hero-plein-ecran` | Visuel plein écran, contenu court dessous | L'ambiance, le lieu | Commerce, restaurant, lieu physique |
| `split-z` | Blocs en deux colonnes alternées | Deux offres ou deux publics | Particuliers / professionnels, produit / service |
| `portfolio-grille` | Grille de visuels dominante | Les réalisations | Chantiers, créations, avant / après |
| `corporate` | Multi-pages, navigation structurée | La crédibilité et l'étendue de l'offre | Cabinet, association, entreprise multi-services |

Ajouter un layout = l'ajouter à ce tableau, puis le décliner dans chaque `_type`.

### Types de design (niveau 4, nom de fichier)

Le type de design décrit l'habillage, indépendamment de la structure. Un même layout peut exister dans tous les types.

| Slug | Habillage |
|---|---|
| `minimaliste` | Fond blanc ou gris clair, texte noir, un seul accent, beaucoup d'espace |
| `chaud` | Crèmes, bruns, terre, accent orangé ou doré, titres en serif |
| `sombre` | Fond noir ou très foncé, texte clair, accent métallique ou froid |
| `dynamique` | Fond blanc franc, accent vif (bleu, orange, corail), typographies affirmées, contrastes forts |
| `naturel` | Vert sauge, crème, tons végétaux, ton doux |

Ajouter un type = l'ajouter à ce tableau, avec une description de l'habillage.

---

## 4. Règles de conception (tous secteurs)

L'objectif : un site qui ressemble au commerce du client, pas à un site généré. Test à appliquer à chaque page : **si on retire le logo, le site pourrait-il être celui de n'importe quel autre commerce ?** Si oui, il est à retravailler.

### Interdits visuels

- **Aucun emoji**, nulle part (titres, boutons, listes, cartes, footer). Les icônes sont des SVG inline ou du texte.
- Pas de dégradé violet / bleu / rose, pas de `radial-gradient` en hero, pas de `background-clip: text` sur les titres.
- Pas de glassmorphism (`backdrop-filter`, fonds translucides flous).
- Pas de `box-shadow` colorée, pas d'effet de halo ou de glow.
- Pas de `border-radius` énorme appliqué uniformément à tous les éléments.
- Pas de rangée de 3 cartes identiques (icône + titre + deux lignes) comme structure principale. Varier les tailles et le rythme.
- Pas de badge décoratif au-dessus du titre principal. Un statut (ouvert / fermé) est autorisé s'il a une fonction.
- Pas d'animation d'entrée sur chaque bloc. Une animation doit avoir une fonction.
- Pas de centrage systématique de tous les textes : alterner alignements et colonnes.

### Interdits de contenu

- Pas de formules génériques : « Bienvenue sur notre site », « Votre partenaire de confiance », « Solutions sur mesure », « Passion et savoir-faire », « Au cœur de... », « Plus qu'un X, un Y ».
- Pas de tirets cadratins en série, pas de construction « ni A ni B, mais C ». Phrases courtes et concrètes : noms de produits, gestes, quartiers, chiffres réels.
- Pas de chiffres inventés (« +500 clients », « 20 ans d'expérience ») : placeholder tant que le client n'a pas confirmé.
- Pas de faux avis, pas de faux prénoms (« Marie L. »), pas de logos de partenaires inventés.
- Pas d'images de stock cliché (poignée de main, ampoule, équipe souriante). Un emplacement photo est un bloc gris étiqueté `[PHOTO : devanture]`.

### Direction visuelle

- Une couleur d'accent maximum, plus des neutres. Contraste AA minimum.
- Deux familles de polices maximum, choisies selon le métier. Ne pas reprendre la même paire sur tous les templates.
- Le design s'appuie sur ce que le métier a de concret : matière, outil, produit, lieu.

---

## 5. Code

- HTML et CSS purs, **un seul fichier `.html`**, CSS dans `<style>`. JavaScript uniquement s'il a une fonction (menu mobile, statut ouvert / fermé).
- Nommage des classes en **Client-First (Finsweet)** : `page-wrapper`, `padding-global`, `container-large`, `section_hero`, `nav_component`, `heading-style-h1`, variantes en `is-...`. Table complète dans `README template type.md`, section 7.
- Couleurs, polices et espacements en variables CSS dans `:root`. Changer le design = modifier ce bloc.
- Mobile first. Vérifier à 375 px, 768 px et 1280 px.
- `lang="fr"`, un seul `<h1>`, `alt` sur toutes les images, focus visible, vrais `<button>` et `<a>`.
- Balises : `<title>`, meta description, Open Graph, viewport, favicon. Données structurées `LocalBusiness` (JSON-LD) avec placeholders.
- Aucune librairie externe. Polices : 2 familles maximum, `font-display: swap`. Images en `loading="lazy"` sauf celle du hero.
- Repères dans le code : `<!-- Zone : hero -->` avant chaque section, `<!-- À PERSONNALISER -->` sur chaque élément propre au client.
- Commentaires en français pour tout code non trivial.

Les templates existants avant cette convention utilisent des classes libres (`hero`, `sec`, `fi`). Ils sont à migrer en Client-First quand ils sont refaits.

---

## 6. Placeholders

| Type | Format |
|---|---|
| Texte client | `[NOM DE L'ENTREPRISE]`, `[VILLE]`, `[ADRESSE]`, `[TÉLÉPHONE]`, `[EMAIL]`, `[HORAIRES]`, `[SIRET]` |
| Contenu à produire | `[TEXTE : consigne]`, `[PHOTO : description]` |
| Valeur technique | `REMPLACER_ID_FORMSPREE`, `REMPLACER_URL_MAPS` |

Un template livré à un client ne doit contenir aucun crochet ni `REMPLACER`. Vérification : recherche de `[` et de `REMPLACER` dans le fichier.

---

## 7. Générer un nouveau template

1. **Cadrer** : secteur, métier, layout, design. Lire ce README et celui du secteur.
2. **Partir du bon point** :
   - métier existant : dupliquer un layout du même métier ;
   - métier absent : dupliquer `<secteur>/_type/<layout>/` et utiliser le dossier `<secteur>/<metier>/<layout>/` (il existe déjà) et y poser le fichier du design.
3. **Respecter le layout** : l'élément mis en avant (section 3) doit dominer visuellement. Les éléments indispensables du README secteur sont tous présents.
4. **Concevoir le design** : palette, polices et formes tirées du métier, avec les interdits de la section 4.
5. **Écrire le contenu en placeholders** réalistes : structure et longueur crédibles, aucun chiffre ni avis inventé.
6. **Nommer** le fichier selon la section 2.
7. **Passer la checklist** (section 8).
8. **Mettre à jour le catalogue** (section 12).

Un layout nouveau pour un métier doit exister dans le `_type` du secteur. Un design nouveau ne change pas la structure du layout.

---

## 8. Checklist avant livraison d'un template

- [ ] Aucun emoji, aucun élément de la liste d'interdits (section 4)
- [ ] Le test « sans le logo » est passé
- [ ] Tous les éléments indispensables du README secteur sont présents
- [ ] Nom de fichier conforme, dossier au bon niveau
- [ ] Classes Client-First, couleurs et polices dans `:root`
- [ ] Un seul `<h1>`, `alt` renseignés, contraste AA, focus visible
- [ ] Rendu vérifié à 375, 768 et 1280 px
- [ ] Title, meta description, Open Graph renseignés
- [ ] Liens des pages légales dans le footer
- [ ] Aucun texte, chiffre ou avis inventé présenté comme réel

---

## 9. Déploiement d'un site client

1. Créer un repo par client, ou utiliser ce repo marqué **Template repository** (« Use this template »).
2. Copier le fichier choisi, le renommer `index.html`, ajouter à côté `mentions-legales.html` et `confidentialite.html` (depuis `_shared/legal/`) et le dossier `images/`.
3. Remplacer tous les placeholders (section 6).
4. Vercel : « New Project », importer le repo. HTML pur, aucune configuration de build. `_shared/vercel.json` est optionnel.
5. Brancher le nom de domaine dans les réglages du projet Vercel.

---

## 10. Pages légales

`_shared/legal/` contient un seul jeu, avec le placeholder `[NOM DE L'ENTREPRISE]` :

- `mentions-legales.html` : obligatoire en France pour tout site professionnel, même sans vente en ligne.
- `confidentialite.html` : nécessaire dès que le formulaire de contact collecte des données personnelles.

Les passages `[À compléter]` (SIRET, durée de conservation, hébergeur...) se remplissent avec les informations réelles du client. Ce sont des bases de travail, pas un document validé juridiquement : faire relire la version finale par un professionnel pour une activité qui se lance.

Les mentions décrivent le client (éditeur) et son hébergeur. Le prestataire apparaît en crédit de conception, pas comme éditeur.

---

## 11. Formulaire de contact

Les formulaires des templates sont statiques. Deux options pour les rendre fonctionnels :

- **Formspree** (utilisé dans les templates pharmacie) : le client crée son compte, crée un formulaire, et fournit l'ID à mettre dans `action="https://formspree.io/f/REMPLACER_ID_FORMSPREE"`.
- **Supabase** : table `contacts` (`name`, `email`, `message`, `created_at`) alimentée par un appel API depuis le formulaire. Permet de proposer une liste des demandes reçues au client.

Sous chaque formulaire : courte mention RGPD avec lien vers la politique de confidentialité.

---

## 12. Catalogue

| Secteur | Métier | État |
|---|---|---|
| artisan | boulanger, macon, platrier | Fichiers `a-classer` à la racine des dossiers métier, layouts à définir |
| commerce | mode, coiffeur, fleuriste | Fichiers `a-classer` à la racine des dossiers métier, layouts à définir |
| medecine | pharmacie | 14 fichiers à la racine du dossier métier, avec les anciens layouts (epure, cartes, hero, asymetrique) à refaire selon la section 3 ; manquent `epure-minimaliste` et `asymetrique-dynamique`. 2 fichiers `a-classer` en `naturel` |
| sport | ecole-surf | Fichier `a-classer` à la racine du dossier métier, layout à définir |
| tous | `_type` | À créer : 5 layouts par secteur |

---

## 13. Montrer plusieurs designs à un client

Dupliquer le template choisi 2 ou 3 fois en changeant uniquement les variables du bloc `:root`, déployer chaque variante sur une URL de preview Vercel, envoyer les liens au client pour qu'il compare sur son téléphone.
