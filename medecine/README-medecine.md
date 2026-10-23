# Médecine

À lire avec le `README.md` racine. Ce fichier précise les consignes propres au secteur ; en cas de conflit, il l'emporte.

## Métiers

| Slug | État |
|---|---|
| `pharmacie` | `pharmacie/` : 14 fichiers `NN-design-layout`, `Site Pharmacie/index.html`, 3 versions de test (V2, V3, V4), layouts à refaire |
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

## Templates types du secteur

Cinq fichiers à la racine de `medecine/`, un par layout de référence, nommés `type-<layout>_medecine.html` (`type-one-page_medecine.html` pour `one-page`, base par défaut du secteur). Ils restent neutres : libellés génériques, textes en placeholders, aucun contenu propre à un métier, habillage neutre (README racine, section 3).

Les 5 fichiers contiennent **les mêmes blocs de contenu**. Seuls l'ordre, la taille et la position changent : c'est ce qui met un élément différent en avant. Dans les tableaux, l'ordre cite les blocs mis en tête ; les autres blocs de la liste suivent. Chaque template reprend aussi le socle commun du `README.md` racine (section 15).

### Blocs communs aux 5 templates

1. **Bandeau de statut** : ouvert / fermé calculé depuis les horaires, avec un affichage statique de secours sans JavaScript.
2. **Hero sobre** : `[NOM DE L'ÉTABLISSEMENT]`, `[PROFESSION]`, adresse, deux actions (appeler, itinéraire).
3. **Bloc d'urgence** : rappel du 15 et du 112, séparé du reste du contenu.
4. **Services** : 6 emplacements `[SERVICE 1]` à `[SERVICE 6]`, uniquement des services réellement proposés.
5. **Équipe** : noms, fonctions, photos réelles avec accord.
6. **Horaires** : jour par jour, fermetures, renvoi vers la source officielle de garde `[LIEN GARDE]`.
7. **Accès** : adresse, plan, accessibilité PMR, stationnement.
8. **Contact** : formulaire avec avertissement visible « ne pas transmettre d'informations médicales » et mention RGPD.
9. **Footer** : pages légales et mentions d'ordre `[N° ORDRE]`.

Contraintes communes : corps de texte de 16 px minimum, contraste élevé, aucun dégradé ni texte sur une image sans fond plein derrière.

### Les 5 layouts

| Fichier | Ce qui domine | Ordre des sections |
|---|---|---|
| `type-one-page_medecine.html` | Les informations pratiques : statut, horaires, téléphone et adresse dans le premier écran | Statut, hero compact, urgence, services, équipe, accès, contact |
| `type-hero-plein-ecran_medecine.html` | Une photo réelle du lieu plein écran, avec le statut ouvert / fermé en évidence | Hero, urgence, services, équipe, horaires, accès, contact |
| `type-split-z_medecine.html` | Deux services ou deux publics en blocs alternés (comptoir et orthopédie, cabinet et soins à domicile) | Statut, hero compact, service A, service B, équipe, horaires et accès, contact |
| `type-portfolio-grille_medecine.html` | Le lieu et l'équipe en images, dans une grille (pas de réalisations ni d'avant / après) | Statut, hero court, grille lieu et équipe, services en liste, horaires et accès, contact |
| `type-corporate_medecine.html` | Un sommaire pour cabinet pluridisciplinaire ou maison de santé | Navigation à 5 entrées (Praticiens, Services, Horaires, Accès, Contact) vers des pages à créer, une fiche par praticien |

## Pharmacie : fichiers existants

Les 14 fichiers `NN-design-layout.html` (02 à 15) croisent 4 anciens layouts (epure, cartes, hero, asymetrique) et 4 types de design (minimaliste, chaud, sombre, dynamique). Manquent `01-minimaliste-epure` et `asymetrique-dynamique`. Ces 4 layouts ne suivent pas le vocabulaire du README racine : ils sont à refaire sur les 5 layouts de référence. Les designs existants restent utilisables comme base de palettes.

Trois fichiers sont à part :

- `Site Pharmacie/index.html` et `index_medecine.html` : même palette vert sauge et crème (design `naturel`). Le premier est plus complet (formulaire Formspree).
- Les versions de test `01-minimaliste-epure V2-onglets`, `V3-alterne` et `V4-tests animations` : V2 est un design sombre, V3 et V4 sont chauds, malgré le nom `minimaliste`. Leurs idées de layout (onglets, sections alternées) sont à réutiliser, puis les fichiers sont à supprimer.
