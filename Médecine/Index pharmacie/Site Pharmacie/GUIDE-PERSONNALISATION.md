# Guide de Personnalisation — Template Site Pharmacie

Ce template permet de créer rapidement un site internet pour n'importe quelle pharmacie en remplaçant les placeholders par vos informations.

---

## 📋 Liste des Placeholders à Remplacer

### Informations générales

| Placeholder | Description | Exemple |
|-------------|-------------|---------|
| `[NOM DE LA PHARMACIE]` | Nom officiel de la pharmacie | Pharmacie de la République |
| `[VILLE]` | Ville où se trouve la pharmacie | Paris |
| `[ADRESSE COURTE]` | Adresse courte pour la meta description | 12 rue de la Paix, Paris |
| `[ADRESSE COMPLÈTE]` | Adresse complète pour les mentions légales | 12 rue de la Paix, 75001 Paris |
| `[ADRESSE DÉTAILLÉE]` | Adresse avec détails pour la section "Pourquoi nous" | 12 rue de la Paix, Paris 1er, près de l'Opéra |
| `[CODE POSTAL]` | Code postal | 75001 |
| `[NUMÉRO DE TÉLÉPHONE]` | Numéro de téléphone formaté | 01 23 45 67 89 |
| `[NUMERO_TELEPHONE_SANS_ESPACES]` | Numéro pour les liens tel: | 0123456789 |

### Horaires

| Placeholder | Description | Exemple |
|-------------|-------------|---------|
| `[STATUT D'OUVERTURE]` | Statut d'ouverture (hero) | Ouverte du lundi au samedi |
| `[HEURE_OUVERTURE]` | Heure d'ouverture (stats) | 8h30 |
| `[HEURE_FERMETURE]` | Heure de fermeture (stats) | 20h00 |
| `[JOURS_OUVERTURE]` | Jours d'ouverture (stats) | 6j/7 |
| `[JOURS_OUVERTURES_TEXTE]` | Texte des jours (stats) | Du lundi au samedi |
| `[HORAIRES DÉTAILLÉS]` | Horaires détaillés (section pourquoi) | Ouvert jusqu'à 20h du lundi au vendredi, et le samedi jusqu'à 16h30 |
| `[JOURS_SEMAINE]` | Jours de la semaine (tableau) | Lundi – Vendredi |
| `[HORAIRES_SEMAINE]` | Horaires semaine (tableau) | 8h30 – 20h00 |
| `[JOURS_SAMEDI]` | Samedi (tableau) | Samedi |
| `[HORAIRES_SAMEDI]` | Horaires samedi (tableau) | 9h00 – 16h30 |
| `[JOURS_DIMANCHE]` | Dimanche (tableau) | Dimanche |
| `[HORAIRES_DIMANCHE]` | Horaires dimanche (tableau) | Fermé |

### Informations légales

| Placeholder | Description | Exemple |
|-------------|-------------|---------|
| `[ANNÉE]` | Année en cours | 2026 |
| `[FORME JURIDIQUE]` | Forme juridique (SELARL, SARL, etc.) | SELARL |
| `[NUMÉRO SIRET]` | Numéro SIRET | 123 456 789 00012 |
| `[VILLE TRIBUNAL]` | Ville du tribunal de commerce | Paris |
| `[RESPONSABLE PUBLICATION]` | Responsable de publication | M. Jean Dupont |

### Autres informations

| Placeholder | Description | Exemple |
|-------------|-------------|---------|
| `[LANGUES PARLÉES]` | Langues parlées par l'équipe | francophone et anglophone |
| `[GOOGLE_MAPS_EMBED_URL]` | URL d'intégration Google Maps | https://www.google.com/maps/embed?pb=... |

---

## 🔧 Comment Personnaliser

### Méthode 1: Recherche et remplacement (recommandé)

1. Ouvrez `index.html` dans un éditeur de texte (VS Code, Notepad++, etc.)
2. Utilisez la fonction "Rechercher et remplacer" (Ctrl+H ou Cmd+H)
3. Remplacez chaque placeholder par votre information
4. Sauvegardez le fichier

### Méthode 2: Édition manuelle

1. Ouvrez `index.html` dans un éditeur de texte
2. Recherchez manuellement chaque placeholder (ex: `[NOM DE LA PHARMACIE]`)
3. Remplacez-le par votre information
4. Répétez pour tous les placeholders
5. Sauvegardez le fichier

---

## 🗺️ Obtenir l'URL Google Maps Embed

1. Allez sur Google Maps
2. Recherchez votre pharmacie
3. Cliquez sur "Partager" → "Intégrer une carte"
4. Copiez l'URL fournie (elle commence par `https://www.google.com/maps/embed?pb=...`)
5. Remplacez `[GOOGLE_MAPS_EMBED_URL]` dans le fichier

---

## 📝 Exemple de Personnalisation

**Avant:**
```html
<title>[NOM DE LA PHARMACIE] — [VILLE]</title>
```

**Après:**
```html
<title>Pharmacie de la République — Paris</title>
```

**Avant:**
```html
<p><strong>[ADRESSE COMPLÈTE]<br>[CODE POSTAL] [VILLE]</strong></p>
```

**Après:**
```html
<p><strong>12 rue de la Paix<br>75001 Paris</strong></p>
```

---

## ✅ Checklist de Personnalisation

- [ ] Nom de la pharmacie
- [ ] Ville
- [ ] Adresse (courte et complète)
- [ ] Code postal
- [ ] Numéro de téléphone (formaté et sans espaces)
- [ ] Horaires (tous les placeholders)
- [ ] Statut d'ouverture
- [ ] Langues parlées
- [ ] URL Google Maps
- [ ] Forme juridique
- [ ] Numéro SIRET
- [ ] Ville du tribunal
- [ ] Responsable de publication
- [ ] Année en cours

---

## 🚀 Après la Personnalisation

Une fois tous les placeholders remplacés:

1. **Testez le site** en ouvrant `index.html` dans votre navigateur
2. **Vérifiez** que toutes les informations sont correctes
3. **Configurez Formspree** (voir GUIDE-DEPLOIEMENT.md)
4. **Déployez** sur Vercel (voir GUIDE-DEPLOIEMENT.md)

---

## 💡 Conseils

- **Conservez une copie** du fichier original avant de le modifier
- **Utilisez la recherche et remplacement** pour gagner du temps
- **Vérifiez les liens** (téléphone, Google Maps) après modification
- **Testez sur mobile** pour vérifier l'affichage

---

## 🆘 Problèmes Courants

### Le numéro de téléphone ne fonctionne pas
- Vérifiez que `[NUMERO_TELEPHONE_SANS_ESPACES]` ne contient ni espaces ni points
- Exemple correct: `0123456789`
- Exemple incorrect: `01 23 45 67 89` ou `01.23.45.67.89`

### La carte Google Maps ne s'affiche pas
- Vérifiez que l'URL commence par `https://www.google.com/maps/embed?pb=...`
- Assurez-vous que l'URL est complète et non tronquée

### Les horaires ne s'affichent pas correctement
- Vérifiez que vous avez remplacé tous les placeholders d'horaires
- Assurez-vous de respecter le format (ex: `8h30 – 20h00`)

---

Pour toute question sur le déploiement, consultez le GUIDE-DEPLOIEMENT.md
