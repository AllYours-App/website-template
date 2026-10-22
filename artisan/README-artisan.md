# Artisan

À lire avec le `README.md` racine. Ce fichier précise les consignes propres au secteur ; en cas de conflit, il l'emporte.

## Métiers

| Slug | État |
|---|---|
| `boulanger` | `boulanger/boulanger.html` |
| `macon` | `macon/macon.html` |
| `platrier` | `platrier/platrier.html` |
| à venir | `peintre`, `menuisier`, `electricien`, `plombier`, `couvreur` |

Deux familles dans le secteur : les **métiers du bâtiment** (maçon, plâtrier, peintre...), où le visiteur cherche un devis, et les **métiers de bouche** (boulanger...), où il cherche une adresse et des horaires. Les éléments indispensables diffèrent, voir plus bas.

## Action attendue du visiteur

- Bâtiment : appeler ou demander un devis.
- Boulanger : venir en boutique, ou commander par téléphone pour une fête ou un événement.

Le bouton d'action principal est visible dès l'écran d'arrivée, sur mobile aussi (téléphone cliquable avec `tel:`).

## Ton et identité

- Voix de l'artisan : « je » ou « nous », phrases directes, vocabulaire du métier expliqué en une phrase quand il est technique.
- Le design vient de la matière : pierre, enduit, bois, farine, peinture. Palette et textures prises dans le métier, pas dans un catalogue de couleurs.
- Les photos de chantiers réels et de gestes de travail valent mieux que n'importe quel visuel décoratif. Tant qu'elles manquent : `[PHOTO : ...]`.

## Éléments indispensables

### Tous les métiers

- Nom, métier et zone d'intervention (ville et communes desservies) dans le hero ou juste dessous.
- Téléphone cliquable dans le header.
- Coordonnées complètes et horaires pendant lesquels le client peut joindre l'artisan.
- Pages légales liées dans le footer.

### Bâtiment

- Liste précise des prestations (ce qui est fait, pas « tous travaux »).
- Réalisations avec photos, légendées : commune, type de travaux. Format avant / après quand c'est pertinent.
- Formulaire de devis court : nom, téléphone, commune, type de travaux, message.
- Preuves vérifiables : ancienneté réelle, avis Google réels, labels et qualifications uniquement s'ils sont détenus (RGE, Qualibat...).
- Assurance décennale : nom de l'assureur et zone couverte, si le client l'accepte (voir obligations).

### Boulanger

- Produits réels : pains, viennoiseries, spécialités, produit du jour si le client le met à jour.
- Horaires jour par jour, jours de fermeture, congés annuels.
- Adresse avec plan et accès.
- Commande par téléphone pour les événements, si le client la propose.

## Obligations à faire valider par le client

Rappel : ce ne sont pas des conseils juridiques. À confirmer avec le client et son interlocuteur habituel (chambre de métiers, expert-comptable).

- Mentions légales : identité de l'entreprise, SIRET, numéro au répertoire des métiers, adresse, hébergeur.
- Bâtiment : l'assurance décennale concerne les travaux concernés. L'indiquer sur le site est une bonne pratique, à confirmer.
- L'appellation « boulanger » / « boulangerie » est réglementée en France (fabrication sur place). Ne pas l'utiliser sans vérification auprès du client.
- Prix : si des prix sont affichés, ils sont TTC.

## À éviter dans ce secteur

- Photos de stock de chantier (casques jaunes, poignées de main).
- Promesses non tenables : « devis sous 24 h », « intervention le jour même », « prix imbattables ».
- Label, certification ou garantie non détenus.
- Galerie sans légende ni localisation.
- Vocabulaire de start-up : « solutions », « expertise », « accompagnement personnalisé ».

## Layouts recommandés

| Layout | Cas d'usage dans le secteur |
|---|---|
| `one-page` | Artisan solo du bâtiment, parcours devis simple |
| `hero-plein-ecran` | Boulanger : l'ambiance de la boutique en premier |
| `split-z` | Artisan avec deux publics (particuliers / professionnels) ou deux métiers |
| `portfolio-grille` | Métiers où les réalisations font la vente : peintre, plâtrier, maçon, menuisier |
| `corporate` | Entreprise avec plusieurs corps de métier ou plusieurs équipes |

## Templates types du secteur

Cinq fichiers à la racine de `artisan/`, un par layout de référence : `index_artisan.html` pour `one-page` (base par défaut du secteur) et `type-<layout>_artisan.html` pour les 4 autres. Ils restent neutres : libellés génériques, textes en placeholders, aucun contenu propre à un métier, habillage neutre (README racine, section 3).

Les 5 fichiers contiennent **les mêmes blocs de contenu**. Seuls l'ordre, la taille et la position changent : c'est ce qui met un élément différent en avant. Dans les tableaux, l'ordre cite les blocs mis en tête ; les autres blocs de la liste suivent. Chaque template reprend aussi le socle commun du `README.md` racine (section 15).

### Blocs communs aux 5 templates

1. **Hero** : nom, `[MÉTIER]`, zone d'intervention, phrase de promesse concrète, deux actions (appeler, demander un devis).
2. **Prestations** : 6 emplacements `[PRESTATION 1]` à `[PRESTATION 6]`, chacun avec une phrase. Pour un métier de bouche, ce bloc devient « Produits ».
3. **Réalisations** : 6 visuels légendés (commune, type de travaux), dont un emplacement avant / après.
4. **Preuves** : ancienneté `[ANNÉES]`, assurances et labels `[LABEL]` (seulement s'ils sont détenus), avis réels `[AVIS]`.
5. **L'artisan** : photo et trois phrases à la première personne.
6. **Zone d'intervention** : liste des communes `[COMMUNE]`.
7. **Devis** : formulaire de 5 champs (nom, téléphone, commune, type de travaux, message) et mention RGPD.
8. **Coordonnées et horaires** : téléphone, email, adresse, horaires jour par jour.

### Les 5 layouts

| Fichier | Ce qui domine | Ordre des sections |
|---|---|---|
| `index_artisan.html` | Les prestations, en liste pleine largeur, plus grande que le reste | Hero compact, prestations, réalisations, preuves, l'artisan, zone, devis, contact. Bouton d'appel fixe sur mobile |
| `type-hero-plein-ecran_artisan.html` | Une photo de chantier ou de réalisation plein écran, avec nom, métier et zone par-dessus | Hero, prestations (4 maximum), réalisations, preuves, devis, contact |
| `type-split-z_artisan.html` | Deux offres en blocs alternés texte / visuel (par exemple particuliers et professionnels, ou deux familles de travaux) | Hero compact, bloc offre A, bloc offre B, réalisations, preuves, zone, devis |
| `type-portfolio-grille_artisan.html` | Une grille de 6 à 9 visuels de tailles variées, juste sous un hero court | Hero court, réalisations en grille, prestations en liste compacte, preuves, devis |
| `type-corporate_artisan.html` | La crédibilité : accueil qui sert de sommaire d'un site multi-pages | Navigation à 5 entrées (Prestations, Réalisations, L'entreprise, Zone, Contact) vers des pages à créer, accueil avec chiffres `[CHIFFRE]`, équipe, labels, aperçus des pages |
