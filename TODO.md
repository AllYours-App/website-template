# À faire

Liste des tâches restantes de la bibliothèque. Cocher au fur et à mesure et tenir le catalogue du `README.md` (section 12) à jour à chaque ajout.

---

## 1. Nettoyage du repo

- [ ] Supprimer `artisan/Peintre irazoqui/` : contenu d'un vrai client, contraire à la règle du README (aucun vrai client dans le repo).
- [ ] Remplacer `README.md` et les 4 `README-<secteur>.md` par les dernières versions.
- [ ] Activer **Template repository** dans les réglages GitHub du repo (le README suppose « Use this template »).

---

## 2. Terminer l'architecture

Structure cible : `<secteur>/` contient `README-<secteur>.md`, `index_<secteur>.html`, 4 fichiers `type-<layout>_<secteur>.html` en plus de l'index, et un dossier par métier. Pas de pages légales préparées : elles se créent par client (`README.md`, section 10).

- [x] Créer `commerce/index_commerce.html` (layout `one-page`, neutre).
- [ ] Sport : décider de l'emplacement de la base du secteur (aujourd'hui dans `sport/ecole-surf/`, alors qu'artisan et medecine l'ont à la racine du secteur) et créer `sport/index_sport.html` si elle remonte.
- [ ] Rendre `index_artisan.html`, `index_medecine.html` et celui du sport neutres (layout `one-page`) : aujourd'hui `index_artisan.html` est une boulangerie, `index_medecine.html` une pharmacie, celui du sport une école de surf. Aucun design ni contenu propre à un métier.

---

## 3. Créer les templates types (4 `type-<layout>` par secteur, en plus de `index_<secteur>.html`)

Un fichier par layout de référence, à la racine du secteur (le layout `one-page` est `index_<secteur>.html`), sans personnalisation de métier, en placeholders. Pour chaque secteur, les blocs à inclure et ce qui domine dans chaque layout sont détaillés dans `README-<secteur>.md`, section « Templates types du secteur ». Règles générales : `README.md` sections 3 à 6.

**Nombre de layouts fixé à 5**, chacun mettant en avant un élément différent (tableau de choix : `README.md`, section 3). Ajout d'un layout seulement si un client ne rentre dans aucune case.

**Ordre de priorité de production**, dans chaque secteur :

1. `one-page` : layout par défaut, base des 4 autres. Existe déjà, à rendre neutre (section 2).
2. `hero-plein-ecran` : « mon lieu, ma vue, mon ambiance », demande la plus courante des commerces et lieux physiques.
3. `portfolio-grille` : « mes réalisations parlent d'elles-mêmes », fréquent chez les artisans, très différent de `one-page`.
4. `split-z` : seulement quand il y a deux offres ou deux publics.
5. `corporate` : le plus lourd (pages à créer) et le moins demandé pour une vitrine de petit client.

Ordre à ajuster si la clientèle réelle change (beaucoup d'artisans : `portfolio-grille` peut passer devant `hero-plein-ecran`).

Conseil : faire un secteur complet d'abord en commençant par les layouts 1 à 3, vérifier que les layouts sont vraiment différents et ne ressemblent pas à du contenu généré, puis dupliquer la méthode sur les 3 autres secteurs et finir par `split-z` et `corporate`.

### Artisan

- [ ] `artisan/type-hero-plein-ecran_artisan.html`
- [ ] `artisan/type-portfolio-grille_artisan.html`
- [ ] `artisan/type-split-z_artisan.html`
- [ ] `artisan/type-corporate_artisan.html`

### Commerce

- [ ] `commerce/type-hero-plein-ecran_commerce.html`
- [ ] `commerce/type-portfolio-grille_commerce.html`
- [ ] `commerce/type-split-z_commerce.html`
- [ ] `commerce/type-corporate_commerce.html`

### Médecine

- [ ] `medecine/type-hero-plein-ecran_medecine.html`
- [ ] `medecine/type-portfolio-grille_medecine.html`
- [ ] `medecine/type-split-z_medecine.html`
- [ ] `medecine/type-corporate_medecine.html`

### Sport

- [ ] `sport/type-hero-plein-ecran_sport.html`
- [ ] `sport/type-portfolio-grille_sport.html`
- [ ] `sport/type-split-z_sport.html`
- [ ] `sport/type-corporate_sport.html`

---

## 4. Mettre l'existant aux règles du README

Passer les templates actuels à la checklist (`README.md`, section 8) :

- [ ] `artisan/boulanger/boulanger.html`
- [ ] `artisan/macon/macon.html`
- [ ] `artisan/platrier/platrier.html`
- [ ] `commerce/coiffeur/coiffeur.html`
- [ ] `commerce/fleuriste/fleuriste.html`

Points à contrôler sur chacun :

- [ ] Aucun emoji, aucun élément de la liste d'interdits (dégradés, glassmorphism, ombres colorées, `radial-gradient` en hero, `background-clip: text`).
- [ ] Classes en Client-First (les anciens templates utilisent des classes libres).
- [ ] Placeholders harmonisés : les Formspree sont écrits `VOTRE`, `XXXXXXXX` ou `REMPLACER`, la convention est `REMPLACER_ID_FORMSPREE`.
- [ ] Noms de démo remplacés par des placeholders (`[NOM DE L'ENTREPRISE]`, `[VILLE]`...).
- [ ] Éléments indispensables du README du secteur présents.

---

## 5. Décliner les designs

Une fois les layouts stabilisés : plusieurs designs par layout et par métier, au minimum 2. Types disponibles : `minimaliste`, `chaud`, `sombre`, `dynamique`, `naturel`.

- [ ] Choisir les métiers prioritaires.
- [ ] Décliner chaque layout de référence en au moins 2 designs pour ces métiers.

---

## 6. Plus tard : pharmacie et mode

À traiter en temps voulu.

### Pharmacie

- [ ] Refaire les 4 anciens layouts (epure, cartes, hero, asymetrique) sur les 5 layouts de référence.
- [ ] Nettoyer les versions de test `01-minimaliste-epure V2-onglets`, `V3-alterne`, `V4-tests animations` : récupérer les idées de layout (onglets, sections alternées), puis supprimer. Leur nom dit `minimaliste` alors que V2 est sombre et V3 / V4 sont chauds.
- [ ] Décider du sort de `Site Pharmacie/index.html` : même palette vert sauge que `index_medecine.html` (design `naturel`), le renommer ou l'intégrer.
- [ ] Combler les cases manquantes de la matrice : `01-minimaliste-epure` et `asymetrique-dynamique`.
- [ ] Décider si les guides supprimés (`GUIDE-DEPLOIEMENT.md`, `GUIDE-PERSONNALISATION.md`, `vercel.json`, récupérables dans l'historique Git) doivent être réintégrés. Le README racine couvre déjà le déploiement.

### Mode

- [ ] Renommer les 6 fichiers de `commerce/mode/` en `NN-design-layout.html` (aujourd'hui : `mode-01-epure-nordic`, `mode-02-chaud-editorial`, `mode-03-sombre-premium`, `mode-04-asymetrique-blanc`, `mode-05-minimaliste-gris`, `boutique-basque`).
- [ ] Décider des layouts de référence de chacun.

---

## 7. Nouveaux métiers

À créer selon les clients rencontrés. Chaque métier reprend le même vocabulaire de layouts et de designs, en partant d'un template type du secteur.

- [ ] Artisan : `peintre` (à refaire en exemple fictif), `menuisier`, `electricien`, `plombier`, `couvreur`
- [ ] Commerce : `epicerie`, `caviste`, `librairie`, `restaurant`
- [ ] Médecine : `medecin`, `kinesitherapeute`, `dentiste`, `infirmier`, `osteopathe`
- [ ] Sport : `coach`, `salle-de-sport`, `club`, `yoga`, `ecole-de-voile`

---

## 8. Documentation et validation

- [ ] Compléter le crédit de conception (`README.md`, section 16) avec les informations du studio.
- [ ] Faire valider les points réglementaires des 4 README de secteur, marqués « à faire valider » : appellation « boulanger » et assurance décennale (artisan), affichage des prix en coiffure (commerce), publicité et déontologie en pharmacie et professions de santé (médecine), carte professionnelle et affichage des diplômes (sport).
- [ ] Dire si Unbounded est toujours utilisé pour produire les templates. Si oui, réintégrer son workflow dans le `README.md`.
- [ ] Mettre à jour le catalogue (`README.md`, section 12) à chaque nouveau fichier.
