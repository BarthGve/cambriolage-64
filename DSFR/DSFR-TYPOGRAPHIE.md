# Typographie DSFR - Documentation Complète

## Vue d'Ensemble

Les typographies **Marianne®** et **Spectral** sont les typographies officielles de la charte de l'État français. Leur usage crée une cohérence entre les interfaces et offre une expérience positive à l'utilisateur.

## Polices Officielles

### Polices Principales

- **Marianne®** (light, regular, bold) + versions italiques (light italic, regular italic, bold italic)
- **Spectral** (regular, extra-bold)

### Polices de Substitution

- **Arial** → substitut pour Marianne
- **Georgia** → substitut pour Spectral

### Sources

Les typographies en format web sont incluses dans le DSFR. Versions desktop et PDF disponibles sur :
https://www.info.gouv.fr/marque-de-letat/la-typographie

## Conversion et Responsive

- **Base de calcul** : 1rem = 16px
- **Points de rupture** : Les tailles changent au point de rupture MD
  - **Mobile** : jusqu'au point de rupture MD
  - **Desktop** : au-delà du point MD

## Hiérarchie des Titres (H1-H6)

### H1 - Titre Principal

**Usage** : Titre principal de la page (1 seul par page)

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 40px (2.5rem) | 32px (2rem) |
| Line-height | 48px | 40px |
| Margin-bottom | 24px | 24px |
| Couleur (fond clair) | G800 | G800 |
| Couleur (fond foncé) | White | White |

**HTML** : `<h1>`

### H2 - Titre de Section

**Usage** : Second niveau de titre de section/paragraphes (nombre illimité)

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 32px (2rem) | 28px (1.75rem) |
| Line-height | 40px | 36px |
| Margin-bottom | 24px | 24px |
| Couleur (fond clair) | G800 | G800 |
| Couleur (fond foncé) | White | White |

**HTML** : `<h2>`

### H3 - Sous-Titre de Section

**Usage** : Troisième niveau (nombre illimité)

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 28px (1.75rem) | 24px (1.5rem) |
| Line-height | 36px | 32px |
| Margin-bottom | 24px | 24px |
| Couleur (fond clair) | G800 | G800 |
| Couleur (fond foncé) | White | White |

**HTML** : `<h3>`

### H4 - Quatrième Niveau

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 24px (1.5rem) | 22px (1.375rem) |
| Line-height | 32px | 28px |
| Margin-bottom | 24px | 24px |
| Couleur (fond clair) | G800 | G800 |
| Couleur (fond foncé) | White | White |

**HTML** : `<h4>`

### H5 - Cinquième Niveau

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 22px (1.375rem) | 20px (1.25rem) |
| Line-height | 28px | 28px |
| Margin-bottom | 24px | 24px |
| Couleur (fond clair) | G800 | G800 |
| Couleur (fond foncé) | White | White |

**HTML** : `<h5>`

### H6 - Sixième Niveau

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 20px (1.25rem) | 18px (1.125rem) |
| Line-height | 28px | 24px |
| Margin-bottom | 24px | 24px |
| Couleur (fond clair) | G800 | G800 |
| Couleur (fond foncé) | White | White |

**HTML** : `<h6>`

## Titres Alternatifs (Display)

Les titres alternatifs offrent une liberté éditoriale sans nuire à la hiérarchie SEO.

### Display XL - `fr-display--xl`

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 80px (5rem) | 72px (4.5rem) |
| Line-height | 88px | 80px |
| Margin-bottom | 32px | 32px |
| Couleur (fond clair) | G800 | G800 |
| Couleur (fond foncé) | White | White |

**Usage** : Bannières principales, hero sections

### Display LG - `fr-display--lg`

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 72px (4.5rem) | 64px (4rem) |
| Line-height | 80px | 72px |
| Margin-bottom | 32px | 32px |

**Usage** : Mises en avant importantes

### Display MD - `fr-display--md`

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 64px (4rem) | 56px (3.5rem) |
| Line-height | 72px | 64px |
| Margin-bottom | 32px | 32px |

### Display SM - `fr-display--sm`

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 56px (3.5rem) | 48px (3rem) |
| Line-height | 64px | 56px |
| Margin-bottom | 32px | 32px |

### Display XS - `fr-display--xs`

| Attribut | Desktop | Mobile |
|----------|---------|--------|
| Taille | 48px (3rem) | 40px (2.5rem) |
| Line-height | 56px | 48px |
| Margin-bottom | 32px | 32px |

## Corps de Texte (Body)

### XL - Texte Chapô - `fr-text--lead`

**Usage** : Introductions, accroches

| Attribut | Valeur |
|----------|--------|
| Taille | 20px (1.25rem) |
| Line-height | 32px |
| Margin-bottom | 24px |
| Couleur (fond clair) | G700 |
| Couleur (fond foncé) | G200 |

### LG - Texte Article - `fr-text--lg`

**Usage** : Corps de texte éditorial (actualités, blog)

| Attribut | Valeur |
|----------|--------|
| Taille | 18px (1.125rem) |
| Line-height | 28px |
| Margin-bottom | 24px |
| Couleur (fond clair) | G700 |
| Couleur (fond foncé) | G200 |

### MD - Texte Standard - `fr-text`

**Usage** : Texte courant par défaut (style par défaut `<p>`)

| Attribut | Valeur |
|----------|--------|
| Taille | 16px (1rem) |
| Line-height | 24px |
| Margin-bottom | 24px |
| Couleur (fond clair) | G700 |
| Couleur (fond foncé) | G200 |

### SM - Texte Détail - `fr-text--sm`

**Usage** : Corps de texte au sein de certains composants

| Attribut | Valeur |
|----------|--------|
| Taille | 14px (0.875rem) |
| Line-height | 24px |
| Margin-bottom | 24px |
| Couleur (fond clair) | G700 |
| Couleur (fond foncé) | G200 |

### XS - Texte Mention - `fr-text--xs`

**Usage** : Mentions, légendes, informations mineures

| Attribut | Valeur |
|----------|--------|
| Taille | 12px (0.75rem) |
| Line-height | 20px |
| Margin-bottom | 24px |
| Couleur (fond clair) | G600 |
| Couleur (fond foncé) | G300 |

## Spectral Alternative

Tous les styles de texte (LG, MD, SM, XS) sont disponibles avec la typographie Spectral via la classe `fr-text--alt`.

**⚠️ Usage Limité** : Informations secondaires, mineures ou à distinguer uniquement.

## Listes

### Liste Ordonnée

```html
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>
```

### Liste Non Ordonnée

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

## Personnalisation des Titres

### Classes de Style

Les développeurs peuvent utiliser les classes `fr-h1`, `fr-h2`, `fr-h3`, `fr-h4`, `fr-h5`, `fr-h6` pour personnaliser l'apparence tout en préservant la sémantique HTML.

**Exemple** :
```html
<!-- H3 sémantique avec apparence H1 -->
<h3 class="fr-h1">Titre principal visuel</h3>
```

### Combinaisons Display + Heading

Les titres alternatifs peuvent être associés à n'importe quelle balise `<h1>` à `<h4>` selon le besoin :

```html
<h2 class="fr-display--lg">Grande mise en avant</h2>
<h1 class="fr-display--md">Hero banner</h1>
```

## Règles d'Utilisation

### Hiérarchisation de l'Information

1. **Limiter les niveaux** : Ne pas utiliser plus de 4 niveaux de titres sur une même page
2. **Cohérence** : Créer des récurrences typographiques au sein du site
3. **Équilibre** : Usage uniforme des graisses et tailles
4. **H1 unique** : Un seul H1 par page (SEO)

### Longueur du Texte Courant

#### Desktop
- **Recommandation** : 45-75 caractères par ligne
- **Conteneur** : Maximum 8 colonnes de grille DSFR

#### Mobile
- **Recommandation** : 35-40 caractères par ligne
- **Tailles S/XS** : Utiliser conteneur plus étroit

### Conteneur Recommandé

```html
<div class="fr-container">
  <div class="fr-grid-row">
    <div class="fr-col-12 fr-col-md-8">
      <!-- Contenu textuel principal -->
      <p>Texte courant...</p>
    </div>
  </div>
</div>
```

## Exemples de Code

### Structure Typographique Standard

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14.0/dist/dsfr.min.css" />
</head>
<body>
  <div class="fr-container">
    <h1>Titre Principal de la Page</h1>

    <p class="fr-text--lead">
      Chapô introductif avec texte mis en avant pour accrocher le lecteur.
    </p>

    <h2>Section Principale</h2>

    <p>
      Texte courant standard utilisant le style par défaut fr-text (16px).
      Ce paragraphe illustre la taille recommandée pour le contenu principal.
    </p>

    <h3>Sous-Section</h3>

    <p class="fr-text--sm">
      Texte de détail plus petit pour informations complémentaires.
    </p>

    <p class="fr-text--xs">
      Mention légale ou information mineure en très petite taille.
    </p>
  </div>
</body>
</html>
```

### Mise en Avant avec Display

```html
<div class="fr-container">
  <!-- Hero banner -->
  <h1 class="fr-display--lg">
    Bienvenue sur le Portail Gouvernemental
  </h1>

  <!-- Section mise en avant -->
  <h2 class="fr-display--sm">
    Actualités Principales
  </h2>

  <!-- Contenu standard -->
  <h2 class="fr-h2">
    Informations Complémentaires
  </h2>
</div>
```

### Texte Spectral Alternatif

```html
<p class="fr-text--lg fr-text--alt">
  Citation ou extrait mis en avant avec la typographie Spectral.
</p>

<p class="fr-text--xs fr-text--alt">
  Information secondaire en Spectral pour la distinguer.
</p>
```

## Checklist de Conformité

Avant validation d'une interface :

- [ ] Marianne utilisée comme typographie principale
- [ ] Spectral réservée aux informations secondaires
- [ ] Maximum 4 niveaux de titres utilisés
- [ ] Un seul H1 par page
- [ ] Conteneur de texte ≤ 8 colonnes
- [ ] Longueur de ligne : 45-75 caractères (desktop)
- [ ] Hiérarchie visuelle claire et cohérente
- [ ] Classes DSFR utilisées (pas de styles custom)
- [ ] Contraste respecté (G800/White pour titres, G700/G200 pour texte)
- [ ] Responsive : tailles adaptées mobile/desktop

## Ressources

- **Documentation officielle** : https://www.systeme-de-design.gouv.fr/elements-d-interface/fondamentaux-de-l-identite-de-l-etat/typographie
- **Téléchargement polices** : https://www.info.gouv.fr/marque-de-letat/la-typographie
- **DSFR GitHub** : https://github.com/GouvernementFR/dsfr
