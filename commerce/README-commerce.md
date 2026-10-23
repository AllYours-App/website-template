# Commerce

À lire avec le `README.md` racine. Ce fichier précise les consignes propres au secteur ; en cas de conflit, il l'emporte.

## Métiers

| Slug | État |
|---|---|
| `mode` | 6 fichiers dans `mode/`, aux noms d'origine, dont une boutique prêt-à-porter basque |
| `coiffeur` | `coiffeur/coiffeur.html` |
| `fleuriste` | `fleuriste/fleuriste.html` |
| à venir | `epicerie`, `caviste`, `librairie`, `restaurant` |

**Hors périmètre : la vente en ligne.** Ce sont des sites vitrines. Pas de panier, pas de bouton « Ajouter au panier » factice, pas de tunnel de commande.

## Action attendue du visiteur

- Mode, épicerie, caviste : venir en boutique.
- Coiffeur : appeler ou réserver. La réservation passe par le téléphone ou un lien vers l'outil déjà utilisé par le client, pas par un système intégré.
- Fleuriste : commander par téléphone, ou venir en boutique.

L'adresse, les horaires et le téléphone sont accessibles sans défiler sur mobile.

## Ton et identité

- Le site est la vitrine de la boutique : il montre le lieu, les produits, la personne derrière le comptoir.
- L'identité visuelle vient de la boutique elle-même : enseigne, matières, produits, lumière. Les 5 designs `mode` existants (nordique épuré, éditorial chaud, sombre premium, asymétrique blanc, minimaliste gris) servent de base de comparaison pour garder des designs vraiment différents.
- Ton propre au commerce : éditorial pour la mode, direct et chaleureux pour le coiffeur et le fleuriste. Pas de voix de marque générique.

## Éléments indispensables

### Tous les métiers

- Adresse, plan, accès (parking, transports, accessibilité).
- Horaires par jour, fermetures exceptionnelles et jours fériés.
- Téléphone cliquable.
- Photos réelles de la boutique, de la devanture, de l'équipe.
- Lien vers le compte Instagram ou Facebook du commerce, s'il existe.
- Pages légales liées dans le footer.

### Mode

- Collection ou sélection de saison avec visuels fournis par le client.
- Marques distribuées : seulement celles que la boutique vend, et seulement avec l'accord de la marque pour l'usage du nom ou du logo.
- Univers de la boutique : le lieu, le conseil, les services (retouches, cartes cadeaux) s'ils existent.

### Coiffeur

- Grille tarifaire complète, claire, par prestation.
- Prestations : coupe, couleur, soin, barbe, selon le salon.
- Équipe avec prénoms et spécialités.
- Moyen de réservation concret (téléphone, lien vers l'outil du salon).
- Réalisations (photos de coiffures) avec accord des personnes photographiées.

### Fleuriste

- Gammes de bouquets avec prix « à partir de », saisonnalité.
- Occasions : naissance, mariage, deuil, abonnement, selon ce que le client propose.
- Commande par téléphone, délais, livraison **uniquement si elle existe** (zones et conditions précisées).

## Obligations à faire valider par le client

Rappel : ce ne sont pas des conseils juridiques.

- Prix affichés en TTC.
- Coiffure : les prix des prestations sont à afficher en salon, le site doit reprendre les mêmes. Vérifier la règle en vigueur avec le client.
- Photos de personnes : autorisation du droit à l'image.
- Logos et noms de marques : usage soumis à l'accord des marques.

## À éviter dans ce secteur

- Faux urgence commerciale : « stock limité », « -30 % aujourd'hui » sans promotion réelle.
- Boutique en ligne factice (panier, paiement) sur un site vitrine.
- Galerie produits sans prix quand le prix est un critère de décision.
- Visuels de mannequins ou de bouquets de banque d'images présentés comme ceux de la boutique.
- Wall of logos de marques non autorisées.

## Layouts recommandés

| Layout | Cas d'usage dans le secteur |
|---|---|
| `one-page` | Petit commerce de proximité, informations pratiques en priorité |
| `hero-plein-ecran` | Mode, fleuriste : l'ambiance et les visuels d'abord |
| `split-z` | Boutique avec deux univers (femme / homme, boutique / atelier) |
| `portfolio-grille` | Coiffeur (réalisations), fleuriste (créations), mode (lookbook) |
| `corporate` | Commerce à plusieurs points de vente ou plusieurs activités |

## Templates types du secteur

Cinq fichiers à la racine de `commerce/`, un par layout de référence, nommés `type-<layout>_commerce.html` (`type-one-page_commerce.html` pour `one-page`, base par défaut du secteur). Ils restent neutres : libellés génériques, textes en placeholders, aucun contenu propre à un métier, habillage neutre (README racine, section 3).

Les 5 fichiers contiennent **les mêmes blocs de contenu**. Seuls l'ordre, la taille et la position changent : c'est ce qui met un élément différent en avant. Dans les tableaux, l'ordre cite les blocs mis en tête ; les autres blocs de la liste suivent. Chaque template reprend aussi le socle commun du `README.md` racine (section 15).

### Blocs communs aux 5 templates

1. **Hero** : devanture ou ambiance, nom `[NOM BOUTIQUE]`, adresse, horaires du jour.
2. **Produits ou prestations** : 6 emplacements `[PRODUIT 1]` à `[PRODUIT 6]` avec prix `[PRIX]` en TTC ou « à partir de ». Aucun panier.
3. **Univers de la boutique** : le lieu, la personne, trois phrases.
4. **Galerie** : 6 photos réelles (boutique, produits, équipe).
5. **Équipe** : prénoms `[PRÉNOM]` et spécialités.
6. **Horaires** : jour par jour, fermetures exceptionnelles.
7. **Accès** : adresse, plan, parking et transports, accessibilité.
8. **Contact et réservation** : téléphone, lien de réservation `[LIEN RÉSERVATION]` vers l'outil déjà utilisé par le client, réseau social.

### Les 5 layouts

| Fichier | Ce qui domine | Ordre des sections |
|---|---|---|
| `type-one-page_commerce.html` | Les informations pratiques et l'offre, compactes | Hero compact, produits avec prix, univers, horaires et accès, contact. Barre fixe mobile (adresse, horaires, appel) |
| `type-hero-plein-ecran_commerce.html` | L'ambiance de la boutique plein écran, adresse et horaires en bandeau sur le hero | Hero, sélection de produits en grandes images, univers, galerie, accès |
| `type-split-z_commerce.html` | Deux univers en blocs alternés (femme / homme, boutique / atelier, produits / services) | Hero compact, univers A, univers B, équipe, horaires et accès |
| `type-portfolio-grille_commerce.html` | Une grille de visuels pleine largeur (lookbook, créations, réalisations) | Hero court, grille, produits et prix en liste sous la grille, accès |
| `type-corporate_commerce.html` | Un sommaire pour commerce à plusieurs points de vente ou plusieurs activités | Navigation à 5 entrées (Boutiques, Activités, Équipe, Actualités, Contact) vers des pages à créer, un bloc adresse et horaires par point de vente |
