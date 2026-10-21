# Templates sites vitrines (Unbounded)

5 structures de page d'accueil en wireframe (gris neutres, aucune couleur), à ouvrir dans [Unbounded](https://wbf22.github.io/unbounded/Unbounded.html) puis à habiller selon le projet.

| Fichier | Structure |
|---|---|
| `template 1.html` | One-page service |
| `template 2.html` | Hero plein écran |
| `template 3.html` | Split-screen en Z |
| `template 4.html` | Portfolio en grille |
| `template 5.html` | Corporate multi-pages |

## 1. Choisir le template

| Le client est... | Template |
|---|---|
| Freelance, consultant, artisan solo, thérapeute, petit prestataire | 1 |
| Restaurant, hôtel, commerce, lieu physique, événement | 2 |
| Deux offres ou deux publics (particuliers / pros, produit / service) | 3 |
| Photographe, architecte, designer, agence créative | 4 |
| PME, cabinet, association, entreprise multi-services | 5 |

Si le client hésite entre deux templates, prends celui dont le **hero** correspond le mieux à son message principal. Les sections sont indépendantes : tu peux en copier une d'un template vers un autre.

## 2. Workflow

1. **Brief** : remplis la fiche du point 3 avec le client.
2. **Copie** : duplique le fichier template choisi et renomme-le (`nom-client.html`). Ne modifie jamais les originaux.
3. **Ouverture** : dans Unbounded, utilise « open file » sur ta copie.
4. **Contenu** : remplace les blocs gris `.placeholder` par les vrais visuels, et les textes d'exemple par les vrais textes.
5. **Structure** : supprime les sections inutiles, ajoute celles du point 4. Chaque zone est repérée par un commentaire `<!-- Zone : ... -->` et une classe `section_...`.
6. **Socle commun** : complète le point 3 sur toutes les pages.
7. **Style** : couleurs, typographies et espacements se règlent en CSS (onglet CSS d'Unbounded, ou onglet Classes pour appliquer un style à plusieurs éléments).
8. **Contrôle** : passe la checklist du point 6, puis exporte en HTML.

## 3. Socle commun (identique sur tous les sites)

### Infos à récupérer auprès du client

- [ ] Nom de l'entreprise et logo
- [ ] Message principal (une phrase) et action attendue du visiteur (appeler, réserver, demander un devis)
- [ ] Coordonnées : adresse, téléphone, email, horaires
- [ ] Statut juridique, SIREN/SIRET, adresse de l'éditeur, directeur de la publication
- [ ] Hébergeur du site : nom, adresse, contact
- [ ] Réseaux sociaux
- [ ] Textes et visuels fournis, ou à produire

### Éléments présents sur chaque page

- **Header** : logo, navigation, CTA principal.
- **Footer** : logo, liens, accès aux pages légales, crédit de conception.
- **Pages légales** : mentions légales, politique de confidentialité, politique cookies si cookies non essentiels (analytics, réseaux sociaux, publicité).
- **Formulaire de contact** : un court texte RGPD sous le formulaire, avec un lien vers la politique de confidentialité.
- **Balises techniques** : `lang="fr"`, `<title>`, meta description, favicon, balises Open Graph, viewport.
- **HTTPS** activé chez l'hébergeur.

### Crédit de conception (tes infos)

À compléter une fois pour toutes :

```
Nom / studio : [À COMPLÉTER]
Site / portfolio : [À COMPLÉTER]
Email / contact : [À COMPLÉTER]
Formulation du crédit : [À COMPLÉTER]  (ex. « Site réalisé par … »)
```

Les mentions légales décrivent le **client** (éditeur) et son hébergeur. Ton nom apparaît en crédit de conception, pas comme éditeur. Je ne suis pas juriste : valide le contenu des pages légales selon le statut du client et ton contrat.

## 4. Pages et sections à ajouter selon le besoin

Ces éléments ne sont pas inclus dans les 5 templates.

**Pages secondaires** : contact dédié, détail d'un service, tarifs, FAQ, article de blog, mentions légales, politique de confidentialité, 404.

**Sections** : tarifs, FAQ, logos clients, carte, newsletter, vidéo, carrousel.

Quand tu crées une section utile à plusieurs projets, enregistre-la comme composant (clic droit sur l'élément, « save as component »), puis exporte ta bibliothèque en `components.json` pour la réutiliser.

## 5. Limites d'Unbounded

- Pas de JavaScript généré : les boutons ne font que des liens.
- Pas d'hébergement : l'export HTML est à déposer chez l'hébergeur du client.
- Un formulaire qui envoie réellement un message demande un service tiers ou un développement à part.
- Hors périmètre de ces templates : e-commerce, réservation en ligne, espace membre, site multilingue.

## 6. Checklist avant livraison

- [ ] Plus aucun `.placeholder` ni texte d'exemple
- [ ] Un seul `<h1>` par page
- [ ] Textes alternatifs sur toutes les images
- [ ] Liens et CTA testés
- [ ] Rendu vérifié sur mobile, tablette et desktop
- [ ] Mentions légales et politique de confidentialité en ligne, liées depuis le footer
- [ ] Crédit de conception en place
- [ ] Title et meta description renseignés sur chaque page

## 7. Conventions de nommage (Client-First)

| Type | Exemple |
|---|---|
| Structure globale | `page-wrapper`, `padding-global`, `container-large` |
| Espacement de section | `padding-section-medium`, `padding-section-large` |
| Zone de page | `section_hero`, `section_services`, `section_contact` |
| Composant | `nav_component`, `footer_component`, `card` |
| Variante | `is-primary`, `is-reverse`, `is-overlay` |
| Texte | `heading-style-h1`, `text-size-medium`, `text-align-center` |
