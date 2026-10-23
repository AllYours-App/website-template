# Bibliothèque de templates de sites vitrines

Templates HTML/CSS pour sites vitrines de petites entreprises locales. Quand un client arrive avec un métier, on part d'un template déjà structuré au lieu d'une page blanche.

Ce README fixe les règles communes à tous les templates. Chaque secteur a son propre README (`artisan/README-artisan.md`, `commerce/README-commerce.md`, `medecine/README-medecine.md`, `sport/README-sport.md`) avec les consignes et les éléments indispensables du métier. **Les deux se lisent avant de créer ou de modifier un template.** En cas de conflit, le README du secteur l'emporte.

**Ce repo est public : aucun contenu de vrai client** (textes, photos, logo, identifiant de formulaire). Seuls des exemples fictifs y ont leur place.

---

## 1. Structure

```
website-template/
├── README.md
└── <secteur>/                          niveau 1 : artisan, commerce, medecine, sport
    ├── README-<secteur>.md             consignes du secteur
    ├── type-one-page_<secteur>.html    template type du layout one-page (base par défaut)
    ├── type-<layout>_<secteur>.html    4 autres templates types (un par layout)
    └── <metier>/                       niveau 2 : boulanger, pharmacie, coiffeur...
        └── <fichiers>.html             niveau 3 : templates du métier
```

| Niveau | Contenu | Rôle |
|---|---|---|
| 1 | Secteur | Regroupe les métiers qui partagent le même ton et les mêmes obligations. Contient la base du secteur et les templates types, sans personnalisation de métier : ils servent quand le métier du client n'a pas encore de dossier |
| 2 | Métier | Un dossier par métier, avec ses templates |
| 3 | Fichiers du métier | Un fichier par combinaison layout × design |

**Layout et design sont deux axes distincts.** Le layout est l'organisation de la page (position, taille, hiérarchie des éléments). Le design est l'habillage (couleurs, typographies, formes). Test : si on retire les couleurs et les polices, deux layouts d'un même métier doivent encore se distinguer par la structure. Deux designs d'un même layout ont la même structure et un habillage différent.

---

## 2. Nommage

- Dossiers et fichiers en kebab-case, sans accents, sans espaces, sans majuscules (`medecine`, `ecole-surf`, `split-z`).
- **Fichiers du secteur** : le nom du secteur est ajouté après un `_` : `type-one-page_artisan.html`, `type-hero-plein-ecran_artisan.html`.
- **Template unique d'un métier** : `<metier>.html`. Exemple : `boulanger/boulanger.html`.
- **Plusieurs variantes d'un métier** : `NN-<design>-<layout>.html`, avec `NN` le numéro d'ordre dans le dossier. Exemple : `06-chaud-cartes.html`.
- Le design est un **type générique** (section 3), jamais un nom de client, de lieu ou de boutique.
- Au déploiement, les suffixes `_<secteur>` disparaissent (section 9).

---

## 3. Layouts et types de design de référence

Chaque layout met en avant **un élément différent** par sa position, sa taille et son poids dans la page, pas par ses couleurs. **5 templates types** par secteur, un par layout, nommés `type-<layout>_<secteur>.html` (`type-one-page_<secteur>.html` pour `one-page`). Un métier reprend le même vocabulaire.

| Slug | Structure | Élément mis en avant | Adapté à |
|---|---|---|---|
| `one-page` | Page unique, sections empilées | L'offre de services | Freelance, consultant, artisan solo, thérapeute, petit prestataire |
| `hero-plein-ecran` | Visuel plein écran, contenu court dessous | L'ambiance, le lieu | Restaurant, hôtel, commerce, lieu physique, événement |
| `split-z` | Blocs en deux colonnes alternées | Deux offres ou deux publics | Deux offres ou deux publics (particuliers / professionnels, produit / service) |
| `portfolio-grille` | Grille de visuels dominante | Les réalisations | Photographe, architecte, designer, agence créative, chantiers avant / après |
| `corporate` | Multi-pages, navigation structurée | La crédibilité et l'étendue de l'offre | PME, cabinet, association, entreprise multi-services |

Ajouter un layout = l'ajouter à ce tableau et au tableau de choix ci-dessous, puis produire son template type dans chaque secteur.

### Choisir un layout selon la demande du client

On propose le layout au client, c'est lui qui dit ce qu'il veut mettre en avant. L'élément cité décide du template type.

| Le client veut mettre en avant | Layout | Fichier |
|---|---|---|
| Ses services, ses prix, ce qu'il propose | `one-page` | `type-one-page_<secteur>.html` |
| Son lieu, sa vue, son ambiance | `hero-plein-ecran` | `type-hero-plein-ecran_<secteur>.html` |
| Ses réalisations, ses photos avant / après | `portfolio-grille` | `type-portfolio-grille_<secteur>.html` |
| Deux offres ou deux publics distincts | `split-z` | `type-split-z_<secteur>.html` |
| Son sérieux, l'étendue de son offre, un site à plusieurs pages | `corporate` | `type-corporate_<secteur>.html` |

- **Plusieurs priorités** : le layout suit l'élément cité en premier, ou celui qui rapporte le plus au client. Les autres éléments passent dans les sections sous le hero.
- **Aucune priorité claire** : `one-page`, le layout le plus neutre.
- **Métier sans dossier** : partir du template type du secteur le plus proche. Les layouts se transfèrent d'un métier à l'autre, seul le vocabulaire change.
- **Nombre de layouts fixé à 5.** On n'en ajoute un que si un client ne rentre dans aucune case du tableau. Un layout jamais choisi se supprime.
- Quand le contenu d'un layout change dans un `README-<secteur>.md`, ce tableau est mis à jour.

Les 5 templates types d'un secteur contiennent les **mêmes blocs de contenu**. Seuls l'ordre, la taille et la position changent. La liste des blocs et le détail de chaque layout sont dans `README-<secteur>.md`, section « Templates types du secteur ».

**Habillage neutre des templates types** : fond blanc, gris clair et texte gris très foncé, un seul accent gris foncé, une seule famille de polices système, images remplacées par des blocs gris étiquetés `[PHOTO : ...]`. Tout l’habillage passe par les variables du bloc `:root`, pour qu'un design (section 3) se pose sans toucher à la structure.

### Types de design

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
- Nommage des classes en **Client-First (Finsweet)** : voir le tableau ci-dessous.
- Couleurs, polices et espacements en variables CSS dans `:root`. Changer le design = modifier ce bloc.
- Mobile first. Vérifier à 375 px, 768 px et 1280 px.
- `lang="fr"`, un seul `<h1>`, `alt` sur toutes les images, focus visible, vrais `<button>` et `<a>`.
- Balises : `<title>`, meta description, Open Graph, viewport, favicon. Données structurées `LocalBusiness` (JSON-LD) avec placeholders.
- Aucune librairie externe. Polices : 2 familles maximum, `font-display: swap`. Images en `loading="lazy"` sauf celle du hero.
- Repères dans le code : `<!-- Zone : hero -->` avant chaque section, `<!-- À PERSONNALISER -->` sur chaque élément propre au client.
- Commentaires en français pour tout code non trivial.

| Classe | Usage |
|---|---|
| `page-wrapper` | Enveloppe de la page |
| `padding-global` | Marges latérales de chaque section |
| `container-large` | Largeur maximale du contenu |
| `padding-section-medium` | Espacement vertical d'une section |
| `section_<nom>` | Section (`section_hero`) |
| `<nom>_component`, `<nom>_<element>` | Composant et ses éléments (`nav_component`, `hero_heading`) |
| `heading-style-h1` à `h6` | Styles de titres |
| `text-size-large`, `text-size-medium`, `text-align-center` | Tailles et alignement du texte |
| `button`, `is-primary`, `is-secondary`, `is-reverse`, `is-overlay` | Bouton et variantes (préfixe `is-` pour toute variante) |

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

1. **Cadrer** : secteur, métier, layout, design. Lire ce README et celui du secteur. Pour un site client, remplir le brief (section 14).
2. **Partir du bon point** :
   - métier existant : dupliquer un fichier de son dossier ;
   - métier absent : dupliquer le template type du layout voulu : `type-<layout>_<secteur>.html` et créer le dossier `<secteur>/<metier>/`.
3. **Respecter le layout** : l'élément mis en avant (section 3) doit dominer visuellement. Les éléments indispensables du README secteur sont tous présents.
4. **Concevoir le design** : palette, polices et formes tirées du métier, avec les interdits de la section 4.
5. **Écrire le contenu en placeholders** réalistes : structure et longueur crédibles, aucun chiffre ni avis inventé.
6. **Nommer** le fichier selon la section 2.
7. **Passer la checklist** (section 8).
8. **Mettre à jour le catalogue** (section 12).

Un design nouveau ne change pas la structure du layout.

---

## 8. Checklists

### Pour un template de la bibliothèque

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

### Avant livraison à un client

- [ ] Plus aucun placeholder, ni texte d'exemple (section 6)
- [ ] Liens et boutons d'action testés
- [ ] Rendu vérifié sur mobile, tablette et ordinateur
- [ ] Mentions légales et politique de confidentialité en ligne, liées depuis le footer
- [ ] Crédit de conception en place (section 16)
- [ ] `<title>` et meta description renseignés sur chaque page
- [ ] HTTPS activé chez l'hébergeur

---

## 9. Déploiement d'un site client

1. Créer un repo par client, ou utiliser ce repo marqué **Template repository** (« Use this template »).
2. Copier le fichier choisi et le renommer `index.html`.
3. Créer les pages légales du client, `mentions-legales.html` et `confidentialite.html`, en suivant la section 10. Les liens des templates pointent vers ces noms.
4. Ajouter le dossier `images/` à côté.
5. Remplacer tous les placeholders (section 6).
6. Vercel : « New Project », importer le repo. HTML pur, aucune configuration de build.
7. Brancher le nom de domaine dans les réglages du projet Vercel.

---

## 10. Pages légales

Il n'y a pas de pages légales préparées dans le repo : elles se créent pour chaque client, à partir des consignes ci-dessous. Les lignes propres au métier (numéro d'inscription, ordre, carte professionnelle, assurance) sont dans `README-<secteur>.md`.

Deux pages sont nécessaires, `mentions-legales.html` et `confidentialite.html`, liées depuis le footer.

**Mentions légales** : obligatoires en France pour tout site professionnel, même sans vente en ligne.

- **Éditeur** : nom de l'entreprise, forme juridique, adresse, SIRET, téléphone, email, responsable de publication, plus les lignes propres au métier.
- **Hébergement** : Vercel Inc., 340 S Lemon Ave #4133, Walnut, CA 91789, États-Unis. Vérifier l'adresse sur vercel.com/legal et remplacer le bloc si l'hébergeur change.
- **Propriété intellectuelle** et **liens hypertextes**.
- **Contact** pour toute question sur les mentions.

**Politique de confidentialité** : nécessaire dès que le formulaire de contact collecte des données personnelles.

- Responsable du traitement, données collectées (nom, email, message), finalité et base légale (consentement donné en envoyant le formulaire).
- Destinataires : le client et le service branché sur le formulaire (section 11), avec le lieu d'hébergement des données. Un sous-traitant hors Union européenne se mentionne avec l'encadrement du transfert.
- Durée de conservation, fixée avec le client (par exemple 12 mois après le dernier contact).
- Droits RGPD (accès, rectification, effacement, opposition), réclamation possible auprès de la CNIL.
- Cookies et services tiers : Google Fonts peut transférer l'adresse IP vers Google au chargement de la page.
- Secteur médecine : demander de ne pas indiquer d'informations de santé détaillées dans le formulaire.

Les mentions décrivent le client (éditeur) et son hébergeur. Le prestataire apparaît en crédit de conception, pas comme éditeur. Ce README n'est pas un avis juridique : faire relire la version finale par un professionnel pour une activité qui se lance.

---

## 11. Formulaire de contact

Les formulaires des templates sont statiques. Deux options pour les rendre fonctionnels :

- **Formspree** (utilisé dans les templates pharmacie) : le client crée son compte, crée un formulaire, et fournit l'ID à mettre dans `action="https://formspree.io/f/REMPLACER_ID_FORMSPREE"`.
- **Supabase** : table `contacts` (`name`, `email`, `message`, `created_at`) alimentée par un appel API depuis le formulaire. Permet de proposer une liste des demandes reçues au client.

Sous chaque formulaire : courte mention RGPD avec lien vers la politique de confidentialité.

---

## 12. Catalogue

| Secteur | Contenu actuel | À faire |
|---|---|---|
| artisan | 5 templates types (`type-one-page_artisan.html` et 4 `type-<layout>_artisan.html`), `boulanger/boulanger.html`, `macon/macon.html`, `platrier/platrier.html` | Aucun |
| commerce | 5 templates types (`type-one-page_commerce.html` et 4 `type-<layout>_commerce.html`), `coiffeur/coiffeur.html`, `fleuriste/fleuriste.html`, `mode/` (6 fichiers aux noms d'origine) | Fichiers `mode/` à renommer en `NN-design-layout` |
| medecine | `index_medecine.html` (pharmacie, design naturel), `pharmacie/` : 14 fichiers `NN-design-layout`, `Site Pharmacie/index.html`, 3 versions de test (`V2`, `V3`, `V4`) | `index_medecine.html` à rendre neutre et à renommer `type-one-page_medecine.html`, 4 `type-<layout>_medecine.html` à créer ; layouts de la pharmacie à refaire selon la section 3 ; manquent `01-minimaliste-epure` et `asymetrique-dynamique` ; versions de test à supprimer ou à intégrer ; `Site Pharmacie/` à renommer |
| sport | `ecole-surf/index_ecole-surf.html` | Emplacement de la base à décider, 5 `type-<layout>_sport.html` à créer |

---

## 13. Montrer plusieurs designs à un client

Dupliquer le template choisi 2 ou 3 fois en changeant uniquement les variables du bloc `:root`, déployer chaque variante sur une URL de preview Vercel, envoyer les liens au client pour qu'il compare sur son téléphone.

---

## 14. Brief client

À récupérer avant de personnaliser un template :

- [ ] Nom de l'entreprise et logo
- [ ] Message principal (une phrase) et action attendue du visiteur (appeler, réserver, demander un devis)
- [ ] Coordonnées : adresse, téléphone, email, horaires
- [ ] Statut juridique, SIREN / SIRET, adresse de l'éditeur, directeur de la publication
- [ ] Hébergeur du site : nom, adresse, contact
- [ ] Réseaux sociaux
- [ ] Textes et visuels fournis, ou à produire

Si le client hésite entre deux layouts, choisir celui dont le hero correspond le mieux à son message principal. Les sections sont indépendantes : on peut en copier une d'un layout vers un autre.

---

## 15. Socle commun (identique sur tous les sites)

- **Header** : logo, navigation, action principale.
- **Footer** : logo, liens, accès aux pages légales, crédit de conception.
- **Pages légales** : mentions légales, politique de confidentialité, et politique cookies si le site dépose des cookies non essentiels (statistiques, réseaux sociaux, publicité).
- **Formulaire de contact** : court texte RGPD sous le formulaire, avec lien vers la politique de confidentialité (section 11).
- **Balises techniques** : section 5.
- **HTTPS** activé chez l'hébergeur.

---

## 16. Crédit de conception

À compléter une fois pour toutes :

```
Nom / studio : [À COMPLÉTER]
Site / portfolio : [À COMPLÉTER]
Email / contact : [À COMPLÉTER]
Formulation du crédit : [À COMPLÉTER]  (ex. « Site réalisé par ... »)
```

Les mentions légales décrivent le **client** (éditeur) et son hébergeur. Le nom du prestataire apparaît en crédit de conception, pas comme éditeur. Ce README n'est pas un avis juridique : valider le contenu des pages légales selon le statut du client et le contrat.

---

## 17. Pages, sections et périmètre

**Pages secondaires à ajouter selon le besoin** : contact dédié, détail d'un service, tarifs, FAQ, article de blog, mentions légales, politique de confidentialité, 404.

**Sections à ajouter selon le besoin** : tarifs, FAQ, logos clients, carte, newsletter, vidéo, carrousel.

**Hors périmètre des templates** : e-commerce, réservation en ligne, espace membre, site multilingue. Un formulaire qui envoie réellement un message demande un service tiers (section 11).

