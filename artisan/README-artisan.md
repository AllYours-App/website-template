# Artisan

À lire avec le `README.md` racine. Ce fichier précise les consignes propres au secteur ; en cas de conflit, il l'emporte.

## Métiers

| Slug | État |
|---|---|
| `boulanger` | Fichiers existants en `a-classer` |
| `macon` | Fichier existant en `a-classer` |
| `platrier` | Fichier existant en `a-classer` |
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

## Contenu du `_type`

Les 5 layouts neutres du secteur incluent : hero avec métier, zone d'intervention et appel à l'action, prestations, réalisations, preuves de confiance, formulaire de devis, coordonnées et horaires, footer légal. Textes en placeholders, aucun design propre à un métier.
