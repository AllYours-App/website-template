# Sport

À lire avec le `README.md` racine. Ce fichier précise les consignes propres au secteur ; en cas de conflit, il l'emporte.

## Métiers

| Slug | État |
|---|---|
| `ecole-surf` | `ecole-surf/index_ecole-surf.html` et ses pages légales |
| à venir | `coach`, `salle-de-sport`, `club`, `yoga`, `ecole-de-voile` |

**Hors périmètre** : réservation en ligne intégrée, paiement, espace adhérent. La réservation passe par le téléphone, un message, ou un lien vers l'outil déjà utilisé par le client.

## Action attendue du visiteur

Réserver un cours, un stage ou une séance d'essai. Le moyen de réserver est visible dès l'écran d'arrivée, sur mobile aussi.

## Ton et identité

- Énergique mais précis : le visiteur veut savoir quoi, quand, où, pour qui, combien.
- Le design vient du lieu et de la pratique : l'eau, le sable, le gymnase, le matériel. Les couleurs et les textures sont celles de l'endroit réel.
- Photos d'activités réelles, prises sur place. Tant qu'elles manquent : `[PHOTO : ...]`. Pas de photos de sportifs professionnels génériques.
- Un hero vidéo en lecture automatique est autorisé seulement s'il est léger, muet, avec une image fixe de secours sur mobile.

## Éléments indispensables

- **Offres** : chaque activité avec niveau, durée, âge minimum, taille du groupe, prix TTC.
- **Ce qui est fourni** : matériel, combinaison, assurance... et ce que le client doit apporter.
- **Lieu de rendez-vous** : spot, plage, salle, avec plan et indications d'accès. Parking.
- **Horaires et saison** : jours et créneaux, période d'ouverture, dépendance aux conditions (météo, marées, houle).
- **Réservation et annulation** : comment réserver, conditions d'annulation et de report, notamment pour les conditions météo.
- **Encadrement** : prénoms, diplômes et qualifications des éducateurs, numéro de carte professionnelle (voir obligations).
- **FAQ** : niveau requis, âge, savoir nager, ce qu'il faut apporter, annulation.
- **Galerie** de photos réelles de séances.
- **Contact** : téléphone cliquable, formulaire, réseaux sociaux.
- Pages légales liées dans le footer.

## Obligations à faire valider par le client

Rappel : ce ne sont pas des conseils juridiques. À confirmer avec le client et la direction départementale concernée (service jeunesse et sports).

- Un éducateur sportif rémunéré doit être titulaire d'une qualification reconnue pour l'activité et se déclarer pour obtenir une carte professionnelle. Le surf relève des activités en « environnement spécifique ».
- Une copie du diplôme et de la carte professionnelle est à afficher dans l'établissement où se pratique l'activité. Reprendre ces informations sur le site est une bonne pratique à confirmer avec le client.
- Assurance : l'établissement doit être couvert. L'indiquer sur le site rassure, à valider avec le client.
- Prix affichés en TTC.
- Droit à l'image : autorisation écrite pour toute personne reconnaissable sur une photo, et accord des responsables légaux pour les mineurs.

## À éviter dans ce secteur

- Chiffres inventés : « 5 000 élèves formés », « école n°1 ».
- Superlatifs invérifiables.
- Promesse « sans risque » ou « tout le monde peut y arriver » : une pratique en milieu naturel comporte des risques.
- Photos de stock de sportifs, de vagues ou de salles qui ne sont pas celles du client.
- Couleurs fluo et effets « énergie » par défaut (halos, dégradés vifs, textes obliques partout).
- Tarifs sans mention de ce qu'ils incluent.

## Layouts recommandés

| Layout | Cas d'usage dans le secteur |
|---|---|
| `one-page` | Coach indépendant : offres, tarifs, contact |
| `hero-plein-ecran` | École de surf, de voile : le lieu et l'activité en grand |
| `split-z` | Deux publics (enfants / adultes) ou deux offres (cours / stages) |
| `portfolio-grille` | Galerie de séances et d'événements au centre |
| `corporate` | Club ou structure avec plusieurs activités, sections et équipes |

## Templates types du secteur

Cinq fichiers à la racine de `sport/`, un par layout de référence, nommés `type-<layout>_sport.html` (`type-one-page_sport.html` pour `one-page`, base par défaut du secteur). Ils restent neutres : libellés génériques, textes en placeholders, aucun contenu propre à un métier, habillage neutre (README racine, section 3).

Les 5 fichiers contiennent **les mêmes blocs de contenu**. Seuls l'ordre, la taille et la position changent : c'est ce qui met un élément différent en avant. Dans les tableaux, l'ordre cite les blocs mis en tête ; les autres blocs de la liste suivent. Chaque template reprend aussi le socle commun du `README.md` racine (section 15).

### Blocs communs aux 5 templates

1. **Hero** : `[ACTIVITÉ]`, lieu, moyen de réserver.
2. **Offres** : 4 emplacements `[ACTIVITÉ 1]` à `[ACTIVITÉ 4]`, chacun avec niveau, durée, âge minimum, taille du groupe, prix TTC et matériel fourni.
3. **Planning et saison** : jours, créneaux, période d'ouverture, dépendance aux conditions (météo, marées).
4. **Lieu de rendez-vous** : plan, accès, parking.
5. **Encadrement** : prénoms, diplômes `[DIPLÔME]`, numéro de carte professionnelle `[N° CARTE PRO]`.
6. **Réservation et annulation** : comment réserver `[LIEN RÉSERVATION]`, conditions d'annulation et de report.
7. **FAQ** : 5 questions (niveau requis, âge, savoir nager, quoi apporter, annulation).
8. **Galerie** : 6 photos de séances réelles, avec accord de droit à l'image.
9. **Contact** : téléphone, formulaire, réseaux sociaux. Mention de l'assurance `[ASSURANCE]` dans le footer.

### Les 5 layouts

| Fichier | Ce qui domine | Ordre des sections |
|---|---|---|
| `type-one-page_sport.html` | Les offres avec niveau et prix, en blocs de tailles différentes | Hero compact, offres, planning, encadrement, FAQ, lieu, contact. Bouton « Réserver » fixe sur mobile |
| `type-hero-plein-ecran_sport.html` | L'activité en situation, plein écran (image réelle, ou vidéo muette légère avec image fixe de secours sur mobile) | Hero, offres, planning, lieu, encadrement, galerie, FAQ |
| `type-split-z_sport.html` | Deux publics ou deux offres en blocs alternés (enfants et adultes, cours et stages) | Hero compact, offre A, offre B, planning, encadrement, réservation et annulation, FAQ |
| `type-portfolio-grille_sport.html` | Une galerie de séances en grille | Hero court, galerie, offres en liste compacte, encadrement, lieu, contact |
| `type-corporate_sport.html` | Un sommaire pour club ou structure multi-activités | Navigation à 5 entrées (Activités, Planning, Équipe, Tarifs, Contact) vers des pages à créer, un bloc par activité |
