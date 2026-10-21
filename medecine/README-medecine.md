# Médecine

À lire avec le `README.md` racine. Ce fichier précise les consignes propres au secteur ; en cas de conflit, il l'emporte.

## Métiers

| Slug | État |
|---|---|
| `pharmacie` | 14 fichiers à ancien layout et 2 fichiers `a-classer`, tous à la racine du dossier métier, layouts à refaire |
| à venir | `medecin`, `kinesitherapeute`, `dentiste`, `infirmier`, `osteopathe` |

**Hors périmètre** : prise de rendez-vous en ligne, espace patient, vente en ligne de médicaments, toute collecte de données de santé.

## Action attendue du visiteur

- Savoir si l'établissement est ouvert maintenant, et à quelles heures.
- Appeler, ou trouver l'adresse et l'accès.

Statut du moment, horaires, téléphone et adresse sont visibles dès l'arrivée sur la page, sur mobile aussi.

## Ton et identité

- Sobre, clair, rassurant. Le site informe, il ne vend pas.
- Public large, dont des personnes âgées : texte lisible (corps 16 px minimum), contraste élevé, cibles tactiles larges, vocabulaire simple.
- Accessibilité renforcée : contraste AA minimum, navigation au clavier complète, pas d'information portée uniquement par la couleur.
- Pas de clip-art médical (stéthoscope, croix décorative répétée, silhouettes). Visuels réels : le lieu, l'équipe, avec leur accord.

## Éléments indispensables

### Tous les métiers

- Statut ouvert / fermé calculé depuis les horaires, avec un affichage statique de secours si le JavaScript est désactivé.
- Horaires par jour, fermetures exceptionnelles, jours fériés.
- Adresse, plan, accès, accessibilité PMR, stationnement.
- Téléphone cliquable.
- Bloc d'urgence : rappel du 15 (SAMU) et du 112 pour les situations urgentes, séparé du reste du contenu.
- Équipe : noms et fonctions des professionnels, photo réelle avec accord.
- Formulaire de contact avec avertissement visible : **ne pas transmettre d'informations médicales** par ce formulaire.
- Pages légales liées dans le footer.

### Pharmacie

- Garde : renvoi vers la source officielle (préfecture, ARS, Ordre) plutôt qu'un planning recopié qui devient faux.
- Services réellement proposés : ordonnances, orthopédie, matériel médical, vaccination, préparations... uniquement ceux du client.
- Titulaire et pharmaciens identifiés.

### Autres professions de santé

- Spécialités et actes pratiqués, sans promesse de résultat.
- Modalités pratiques : prise de rendez-vous par téléphone, conventionnement, moyens de paiement, si le client les renseigne.
- Informations d'ordre professionnel : titre, inscription à l'ordre ou à l'organisme concerné.

## Obligations à faire valider par le client

Rappel : ce ne sont pas des conseils juridiques. Les professions de santé sont encadrées par leur ordre professionnel : faire valider le contenu auprès de lui avant la mise en ligne.

- **Pharmacie** : la publicité en faveur des officines est encadrée par le code de la santé publique et la déontologie. Le site reste informatif : pas de promotion ni de prix ou remises sur les médicaments, pas de comparaison, pas d'argumentaire commercial. La création d'un site est à communiquer au Conseil régional de l'Ordre des pharmaciens. Sources : Ordre national des pharmaciens, ARS.
- **Vente de médicaments en ligne** : réservée aux officines autorisées par l'ARS, avec des règles techniques et des mentions spécifiques. Hors périmètre de ces templates.
- **Médecins et autres professions** : déontologie de l'ordre concerné (information claire et objective, pas de démarche commerciale). À vérifier profession par profession.
- **Données de santé** : un formulaire sur un hébergement standard n'est pas prévu pour recevoir des données de santé. D'où l'avertissement dans le formulaire et l'absence de rendez-vous en ligne.

## À éviter dans ce secteur

- Témoignages de patients, avant / après, promesses de guérison ou de résultat.
- Prix, promotions, « offres » sur des médicaments ou des actes.
- Logos, marques et visuels de laboratoires.
- Éléments clignotants ou animés autour de la croix ou du statut.
- Vocabulaire commercial : « offre », « profitez », « meilleur prix ».
- Planning de garde recopié à la main.

## Layouts recommandés

| Layout | Cas d'usage dans le secteur |
|---|---|
| `one-page` | Cabinet individuel : infos pratiques, équipe, contact |
| `hero-plein-ecran` | Pharmacie avec façade ou lieu à montrer, statut en évidence |
| `split-z` | Deux publics ou deux services (comptoir / orthopédie, cabinet / soins à domicile) |
| `portfolio-grille` | Peu pertinent : à réserver aux cabinets qui montrent un plateau technique |
| `corporate` | Cabinet pluridisciplinaire, maison de santé |

## Contenu du `_type`

Les 5 layouts neutres du secteur incluent : statut ouvert / fermé et horaires, bloc d'urgence, adresse et accès, équipe, services, formulaire de contact avec avertissement, footer légal. Textes en placeholders, aucun design propre à un métier.

## Pharmacie : fichiers existants

Les 14 fichiers existants croisent 4 anciens layouts (epure, cartes, hero, asymetrique) et 4 types de design (minimaliste, chaud, sombre, dynamique). Manquent `epure-minimaliste` et `asymetrique-dynamique`. Ils sont à la racine de `medecine/pharmacie/` car ces 4 layouts ne suivent pas le vocabulaire du README racine : ils sont à refaire dans les 5 dossiers de layout de référence. Deux autres fichiers, en `a-classer`, sont de type `naturel` (vert sauge et crème). Les designs existants restent utilisables comme base de palettes.
