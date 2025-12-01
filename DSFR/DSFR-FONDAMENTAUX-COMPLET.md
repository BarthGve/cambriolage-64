# Fondamentaux du DSFR (Système de Design de l'État Français)

**Guide de Référence Complet - Version Projet Grist SP2C**

---

## 📖 Table des Matières

1. [Introduction au DSFR](#introduction-au-dsfr)
2. [Philosophie DSFR](#philosophie-dsfr)
3. [Installation et Configuration](#installation-et-configuration)
4. [Typographie](#typographie)
5. [Système de Couleurs](#système-de-couleurs)
6. [Système d'Espacement (8 Point Grid)](#système-despacement-8-point-grid)
7. [Grid System (Système de Grille)](#grid-system-système-de-grille)
8. [Composants Essentiels](#composants-essentiels)
9. [Accessibilité](#accessibilité)
10. [Mode Sombre](#mode-sombre)
11. [Règles Strictes & Contraintes](#règles-strictes--contraintes)

---

## 📘 Introduction au DSFR

### Qu'est-ce que le DSFR ?

Le **DSFR (Système de Design de l'État Français)** est le framework officiel de design pour tous les sites web et applications de l'administration française.

**Objectifs** :
- Harmoniser l'expérience utilisateur sur tous les services publics numériques
- Garantir l'accessibilité RGAA 4.1 (100% sur composants officiels)
- Renforcer l'identité visuelle de l'État
- Accélérer le développement grâce à des composants prêts à l'emploi

**Version actuelle** : 1.14
**Site officiel** : https://www.systeme-de-design.gouv.fr/

### Pourquoi utiliser le DSFR ?

- ✅ **Conformité légale** : Obligation pour les sites de l'État français
- ✅ **Accessibilité garantie** : RGAA 4.1 respecté à 100%
- ✅ **Maintenance simplifiée** : Mises à jour centralisées
- ✅ **Design cohérent** : Identité visuelle unifiée
- ✅ **Performance** : CSS optimisé et modulaire

---

## 🧭 Philosophie DSFR

### Principe Fondamental : "All or Nothing"

**L'implémentation du DSFR doit TOUJOURS être complète.**

#### ❌ INTERDIT

- Modifier les composants DSFR (détournement)
- Ajouter des overlays graphiques personnalisés
- Utiliser partiellement le DSFR (ressemblance partielle)
- Utiliser des couleurs en dehors de la palette officielle
- Utiliser des polices autres que Marianne® et Spectral
- Mélanger les couleurs du thème clair et sombre

#### ✅ REQUIS

- Utiliser les **fondamentaux DSFR** (couleurs, typo, espacements, grille) - **OBLIGATOIRE**
- Utiliser les **composants DSFR existants** quand disponibles - **OBLIGATOIRE**
- Créer des composants personnalisés **UNIQUEMENT** s'ils n'existent pas dans la bibliothèque DSFR
- Partager les composants personnalisés avec la communauté si utiles

### Exigence Légale : Fond Blanc Obligatoire

**Loi du 29 juillet 1881, Article 15, Chapitre III** :
> Seules les affiches émanant de l'autorité administrative peuvent être imprimées sur papier blanc.

**Conséquences** :
- **Le fond par défaut DOIT être blanc** (`$background-default-grey`)
- Les fonds colorés alternatifs sont autorisés **UNIQUEMENT pour les sections**
- Les fonds alternatifs doivent :
  - Couvrir toute la largeur de la section
  - Contenir TOUS les éléments de la section
  - Être entourés de blanc (pas deux fonds alternatifs adjacents)
  - Ne PAS contenir de composants interactifs chevauchant deux fonds

---

## 🔧 Installation et Configuration

### 1. Structure HTML de Base

```html
<!DOCTYPE html>
<html lang="fr" data-fr-scheme="system" data-fr-theme="light">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="theme-color" content="#000091" />
    <title>Titre de la Page</title>

    <!-- Script de gestion du thème (AVANT CSS) -->
    <script>
      (function () {
        const scheme = localStorage.getItem("fr-scheme") || "system";
        document.documentElement.setAttribute("data-fr-scheme", scheme);
        if (scheme === "system") {
          const prefersDark = window.matchMedia("(prefers-color-scheme: dark)").matches;
          document.documentElement.setAttribute("data-fr-theme", prefersDark ? "dark" : "light");
          window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", (e) => {
            document.documentElement.setAttribute("data-fr-theme", e.matches ? "dark" : "light");
          });
        }
      })();
    </script>

    <!-- Chargement CSS dans l'ordre STRICT -->
    <!-- Voir section suivante -->
  </head>
  <body>
    <!-- Contenu -->
  </body>
</html>
```

### 2. Ordre de Chargement CSS (CRITIQUE)

**Cet ordre est OBLIGATOIRE et ne DOIT PAS être modifié** :

```html
<!-- 1. THEME SCRIPT (AVANT CSS) -->
<script>
  (function () {
    const scheme = localStorage.getItem("fr-scheme") || "system";
    document.documentElement.setAttribute("data-fr-scheme", scheme);
    if (scheme === "system") {
      const prefersDark = window.matchMedia("(prefers-color-scheme: dark)").matches;
      document.documentElement.setAttribute("data-fr-theme", prefersDark ? "dark" : "light");
      window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", (e) => {
        document.documentElement.setAttribute("data-fr-theme", e.matches ? "dark" : "light");
      });
    }
  })();
</script>

<!-- 2. CORE (requis en premier) -->
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/core/core.min.css" rel="stylesheet" />

<!-- 3. UTILITY (classes utilitaires) -->
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/utility/utility.min.css" rel="stylesheet" />

<!-- 4. ICONS (pictogrammes) -->
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/utility/icons/icons.min.css" rel="stylesheet" />

<!-- 5. SCHEME (mode sombre - CRITIQUE) -->
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/scheme/scheme.min.css" rel="stylesheet" />

<!-- 6. COMPONENTS (ordre alphabétique recommandé) -->
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/accordion/accordion.min.css" rel="stylesheet" />
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/badge/badge.min.css" rel="stylesheet" />
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/button/button.min.css" rel="stylesheet" />
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/card/card.min.css" rel="stylesheet" />
<!-- etc. selon besoins -->
```

**⚠️ Pourquoi cet ordre est critique** :
- **CORE** doit être chargé en premier (variables CSS, reset)
- **SCHEME** doit venir après utility mais avant components (gestion thème)
- Les composants dépendent des tokens définis dans core/utility/scheme

---

## 🔤 Typographie

### Polices Autorisées

**UNIQUEMENT ces deux polices** :

1. **Marianne®** (corps de texte)
   - Graisses : Light (300), Regular (400), Bold (700)
   - Variantes : Normal, Italic
   - Substitution web-safe : **Arial**

2. **Spectral** (titres alternatifs)
   - Graisses : Regular (400), Extra-Bold (800)
   - Substitution web-safe : **Georgia**

### Taille de Base

```css
:root {
  font-size: 16px; /* 1rem = 16px */
}

body {
  margin: 0;
  padding: 0;
  font-family: Marianne, Arial, sans-serif;
  background-color: var(--background-default-grey);
  color: var(--text-default-grey);
}
```

### Hiérarchie Typographique

| Élément | Classe DSFR | Taille Desktop | Taille Mobile |
|---------|-------------|----------------|---------------|
| **Display XL** | `fr-display--xl` | 64px (4rem) | 40px (2.5rem) |
| **Display L** | `fr-display--lg` | 56px (3.5rem) | 36px (2.25rem) |
| **Display M** | `fr-display--md` | 48px (3rem) | 32px (2rem) |
| **Display S** | `fr-display--sm` | 40px (2.5rem) | 28px (1.75rem) |
| **Display XS** | `fr-display--xs` | 32px (2rem) | 24px (1.5rem) |
| **H1** | `fr-h1` | 40px (2.5rem) | 28px (1.75rem) |
| **H2** | `fr-h2` | 32px (2rem) | 24px (1.5rem) |
| **H3** | `fr-h3` | 28px (1.75rem) | 22px (1.375rem) |
| **H4** | `fr-h4` | 24px (1.5rem) | 20px (1.25rem) |
| **H5** | `fr-h5` | 22px (1.375rem) | 18px (1.125rem) |
| **H6** | `fr-h6` | 20px (1.25rem) | 16px (1rem) |
| **Body LG** | `fr-text--lg` | 20px (1.25rem) | 18px (1.125rem) |
| **Body MD** | `fr-text--md` | 18px (1.125rem) | 16px (1rem) |
| **Body SM** | `fr-text--sm` | 16px (1rem) | 14px (0.875rem) |
| **Body XS** | `fr-text--xs` | 14px (0.875rem) | 12px (0.75rem) |

### Espacements Typographiques

**Marges par défaut** :

```css
/* Titres H1-H6 */
h1, h2, h3, h4, h5, h6 {
  margin-bottom: 6v; /* 24px / 1.5rem */
}

/* Titres alternatifs (Display) */
.fr-display--xl, .fr-display--lg, .fr-display--md {
  margin-bottom: 8v; /* 32px / 2rem */
}

/* Paragraphes */
p {
  margin-bottom: 6v; /* 24px / 1.5rem */
}
```

### Utilisation

```html
<!-- Titre principal de page -->
<h1 class="fr-h1">Titre de la Page</h1>

<!-- Titre de section -->
<h2 class="fr-h2">Section</h2>

<!-- Texte corps standard -->
<p>Lorem ipsum dolor sit amet...</p>

<!-- Texte avec taille spécifique -->
<p class="fr-text--lg">Texte large</p>

<!-- Display pour mise en avant -->
<h1 class="fr-display--md">Mise en Avant</h1>
```

---

## 🎨 Système de Couleurs

### Principe : Decision Tokens UNIQUEMENT

**❌ NE JAMAIS utiliser les couleurs d'options directement**

**✅ TOUJOURS utiliser les Decision Tokens**

### Format des Decision Tokens

```
CONTEXTE - USAGE - VARIANT - COULEUR
```

**Exemple** : `$background-action-low-blue-france`
- **CONTEXTE** : background (fond)
- **USAGE** : action (interactif)
- **VARIANT** : low (importance faible)
- **COULEUR** : blue-france (bleu de l'État)

---

### Tokens de Fond (Background)

| Token | Usage | Valeurs Clair/Sombre |
|-------|-------|----------------------|
| `$background-default-grey` | Fond par défaut page/composant | Blanc / G50 |
| `$background-alt-grey` | Fond alternatif sections | G975 / G75 |
| `$background-alt-blue-france` | Sections avec branding État | BF975 / BF75 |
| `$background-action-high-blue-france` | Boutons primaires | BF-sun-113 / BF625 |
| `$background-action-low-blue-france` | Éléments cliquables secondaires | BF925 / BF125 |
| `$background-elevated-grey` | Header, dropdowns | G1000 / G75 |
| `$background-contrast-grey` | Formulaires, mise en avant | G950 / G100 |
| `$background-disabled-grey` | État désactivé | G925 / G125 |
| `$background-flat-error` | Fonds alertes erreur | Rouge clair |
| `$background-flat-warning` | Fonds alertes avertissement | Orange clair |
| `$background-flat-success` | Fonds alertes succès | Vert clair |
| `$background-flat-info` | Fonds alertes info | Bleu clair |

---

### Tokens de Texte (Text)

| Token | Usage | Valeurs Clair/Sombre |
|-------|-------|----------------------|
| `$text-title-grey` | Titres | G50 / G1000 |
| `$text-title-blue-france` | Titres avec branding État | BF-sun-113 / BF625 |
| `$text-default-grey` | Texte corps | G200 / G850 |
| `$text-mention-grey` | Texte secondaire, mentions | G425 / G625 |
| `$text-label-grey` | Labels formulaires | G50 / G1000 |
| `$text-action-high-blue-france` | Texte cliquable (liens) | BF-sun-113 / BF625 |
| `$text-inverted-blue-france` | Texte sur boutons primaires | BF975 / BF113 |
| `$text-active-blue-france` | État actif | BF-sun-113 / BF625 |
| `$text-disabled-grey` | État désactivé | G625 / G425 |
| `$text-default-error` | Texte erreur | Rouge |
| `$text-default-success` | Texte succès | Vert |

---

### Tokens d'Illustration (Artwork)

| Token | Usage | Proportion |
|-------|-------|------------|
| `$artwork-major-blue-france` | Couleur dominante (60%) | BF-sun-113 / BF625 |
| `$artwork-minor-blue-france` | Couleur secondaire (30%) | BF-main-525 / BF-main-525 |
| `$artwork-background` | Fond illustration (10%) | Blanc / G50 |

---

### Accentuation (Composants Spécifiques UNIQUEMENT)

**Accentuation autorisée UNIQUEMENT sur** :
- Badge (fond, texte)
- Card (fond blanc/gris)
- Citation (icône)
- Mise en avant (fond, bordure)
- Mise en exergue (bordure)
- Table (fond, bordure)
- Tag (fond, texte, icône)
- Tuile (fond blanc/gris)

**Couleurs d'accentuation** :
- Bleu France (défaut)
- Vert (success)
- Rouge (error)
- Orange (warning)
- Info (bleu clair)

---

### Utilisation en CSS/HTML

```html
<!-- Via classes utilitaires DSFR -->
<div class="fr-background-alt--grey">Fond alternatif</div>
<p class="fr-text--mention">Texte secondaire</p>

<!-- Via CSS custom (dans <style> si nécessaire) -->
<style>
  :root {
    --bleu-france-sun-113: #000091;
    --bleu-france-sun-113-hover: #1212ff;
    --grey-950: #f6f6f6;
    --grey-975: #fdfdfd;
    --success-425: #18753c;
    --success-950: #b8fec9;
    --warning-425: #b34000;
    --warning-950: #ffe9e6;
    --error-425: #ce0500;
    --error-950: #ffe9e9;
  }

  .custom-element {
    background-color: var(--background-default-grey);
    color: var(--text-default-grey);
  }
</style>
```

**⚠️ Règle d'or** : **JAMAIS de styles inline** (`style="color: #000091"`) → Toujours utiliser classes utilitaires ou tokens CSS.

---

## 📐 Système d'Espacement (8 Point Grid)

### Principe

Le DSFR utilise un **système d'espacement basé sur la grille de 8 points** :
- Toutes les valeurs sont des **multiples de 4px**
- Quelques valeurs spéciales : -6px, -2px, 2px, 6px
- Unité : **`v`** (valeur DSFR)

### Table de Conversion

```
0v = 0px       8v = 32px      16v = 64px     24v = 96px
1v = 4px       9v = 36px      17v = 68px     25v = 100px
2v = 8px      10v = 40px      18v = 72px     26v = 104px
3v = 12px     11v = 44px      19v = 76px     27v = 108px
4v = 16px     12v = 48px      20v = 80px     28v = 112px
5v = 20px     13v = 52px      21v = 84px     29v = 116px
6v = 24px     14v = 56px      22v = 88px     30v = 120px
7v = 28px     15v = 60px      23v = 92px     31v = 124px
```

---

### Classes d'Espacement

#### Marges (Margin)

**Syntaxe** : `fr-m{direction}-{valeur}v`

**Directions** :
- `t` : top (haut)
- `b` : bottom (bas)
- `l` : left (gauche)
- `r` : right (droite)
- `x` : horizontal (gauche + droite)
- `y` : vertical (haut + bas)

**Exemples** :

```html
<!-- Marge top 4v (16px) -->
<div class="fr-mt-4v">Contenu</div>

<!-- Marge bottom 6v (24px) -->
<div class="fr-mb-6v">Contenu</div>

<!-- Marge horizontale (left + right) 8v (32px) -->
<div class="fr-mx-8v">Contenu</div>

<!-- Marge verticale (top + bottom) 2v (8px) -->
<div class="fr-my-2v">Contenu</div>

<!-- Marge négative (pour ajustements fins) -->
<div class="fr-mt-n2v">Contenu décalé vers le haut</div>

<!-- Pas de marge -->
<div class="fr-m-0">Sans marge</div>

<!-- Marge auto (centrage horizontal) -->
<div class="fr-mx-auto">Centré</div>
```

---

#### Responsive Margins

**Syntaxe** : `fr-m{direction}-{breakpoint}-{valeur}v`

**Breakpoints** : `md`, `lg`, `xl`

**Exemples** :

```html
<!-- Marge top 2v sur mobile, 4v à partir de MD (768px) -->
<div class="fr-mt-2v fr-mt-md-4v">Contenu</div>

<!-- Marge bottom 4v sur mobile, 8v à partir de LG (992px) -->
<div class="fr-mb-4v fr-mb-lg-8v">Contenu</div>
```

---

#### Padding (Rembourrage)

**Syntaxe** : `fr-p{direction}-{valeur}v`

**Exemples** :

```html
<!-- Padding top 4v (16px) -->
<div class="fr-pt-4v">Contenu</div>

<!-- Padding horizontal 6v (24px) -->
<div class="fr-px-6v">Contenu</div>

<!-- Padding vertical 8v (32px) -->
<div class="fr-py-8v">Contenu</div>

<!-- Padding uniforme 4v -->
<div class="fr-p-4v">Contenu</div>

<!-- Pas de padding -->
<div class="fr-p-0">Sans padding</div>
```

---

### Espacements Standards Recommandés

| Usage | Espacement |
|-------|------------|
| Entre deux paragraphes | `6v` (24px) |
| Entre section et contenu | `8v` (32px) |
| Padding interne card/tile | `4v` (16px) |
| Espacement entre boutons | `2v` (8px) |
| Marge autour d'un formulaire | `6v` (24px) |
| Padding container global | `4v` mobile, `6v` desktop |

---

## 🏗️ Grid System (Système de Grille)

### Principe

Le DSFR utilise une **grille à 12 colonnes** basée sur Flexbox.

### Structure Obligatoire (Hiérarchie)

```html
<div class="fr-container">          <!-- Conteneur principal -->
  <div class="fr-grid-row">         <!-- Ligne -->
    <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">  <!-- Colonne -->
      Contenu
    </div>
  </div>
</div>
```

**⚠️ Cette hiérarchie est OBLIGATOIRE** : `fr-container` → `fr-grid-row` → `fr-col-*`

---

### Conteneurs (Containers)

| Classe | Largeur max | Usage |
|--------|-------------|-------|
| `fr-container` | 1200px (XL) | Conteneur centré standard |
| `fr-container--fluid` | 100% | Pleine largeur |

**Exemple** :

```html
<!-- Conteneur standard (max 1200px) -->
<div class="fr-container">
  <p>Contenu centré</p>
</div>

<!-- Conteneur pleine largeur -->
<div class="fr-container--fluid">
  <p>Contenu pleine largeur</p>
</div>
```

---

### Breakpoints

| Breakpoint | Écran | Design | Gutters |
|------------|-------|--------|---------|
| **XS** | 0-575px | 320px | 16px |
| **SM** | 576-767px | 576px | 16px |
| **MD** | 768-991px | 768px | 16px |
| **LG** | 992-1247px | 992px | 24px |
| **XL** | ≥1248px | 1440px (max 1200px contenu) | 24px |

---

### Colonnes

#### Classes de Base

| Classe | Largeur | Usage |
|--------|---------|-------|
| `fr-col` | Auto (flex) | Largeur automatique |
| `fr-col-{n}` | n/12 | 1 à 12 colonnes |
| `fr-col-{breakpoint}-{n}` | n/12 à partir breakpoint | Responsive |

**Exemples** :

```html
<!-- 3 colonnes égales sur toutes tailles -->
<div class="fr-grid-row">
  <div class="fr-col-4">Colonne 1</div>
  <div class="fr-col-4">Colonne 2</div>
  <div class="fr-col-4">Colonne 3</div>
</div>

<!-- Responsive : 12 colonnes mobile, 6 à partir MD, 4 à partir LG -->
<div class="fr-grid-row">
  <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">Colonne responsive</div>
</div>

<!-- Auto-width (flex) -->
<div class="fr-grid-row">
  <div class="fr-col">Colonne 1 (auto)</div>
  <div class="fr-col">Colonne 2 (auto)</div>
</div>
```

---

#### Offsets (Décalages)

| Classe | Usage |
|--------|-------|
| `fr-col-offset-{n}` | Décalage gauche de n colonnes |
| `fr-col-offset-{n}--right` | Décalage droite de n colonnes |

**Exemples** :

```html
<!-- Colonne 6 décalée de 3 colonnes à gauche -->
<div class="fr-grid-row">
  <div class="fr-col-6 fr-col-offset-3">Centré</div>
</div>

<!-- Décalage droite -->
<div class="fr-grid-row">
  <div class="fr-col-6 fr-col-offset-3--right">Décalé à droite</div>
</div>
```

---

### Modificateurs de Ligne (Grid Row)

#### Alignement Horizontal

| Classe | Effet |
|--------|-------|
| `fr-grid-row--left` | Alignement à gauche |
| `fr-grid-row--center` | Centrage horizontal |
| `fr-grid-row--right` | Alignement à droite |

#### Alignement Vertical

| Classe | Effet |
|--------|-------|
| `fr-grid-row--top` | Alignement en haut |
| `fr-grid-row--middle` | Centrage vertical |
| `fr-grid-row--bottom` | Alignement en bas |

#### Gutters (Gouttières)

| Classe | Effet |
|--------|-------|
| `fr-grid-row--gutters` | Active les gouttières (espaces entre colonnes) |
| `fr-grid-row--no-gutters` | Supprime les gouttières |

**Exemples** :

```html
<!-- Ligne avec colonnes centrées horizontalement et verticalement -->
<div class="fr-grid-row fr-grid-row--center fr-grid-row--middle">
  <div class="fr-col-6">Centré H & V</div>
</div>

<!-- Ligne avec gouttières -->
<div class="fr-grid-row fr-grid-row--gutters">
  <div class="fr-col-4">Colonne avec espace</div>
  <div class="fr-col-4">Colonne avec espace</div>
  <div class="fr-col-4">Colonne avec espace</div>
</div>
```

---

### Exemple Complet Responsive

```html
<div class="fr-container">
  <div class="fr-grid-row fr-grid-row--gutters">
    <!-- Mobile: 12 cols, Tablette: 6 cols, Desktop: 4 cols -->
    <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">
      <div class="fr-card">Carte 1</div>
    </div>
    <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">
      <div class="fr-card">Carte 2</div>
    </div>
    <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">
      <div class="fr-card">Carte 3</div>
    </div>
  </div>
</div>
```

---

## 🧩 Composants Essentiels

### Boutons (Buttons)

**⚠️ RÈGLE CRITIQUE** : Les boutons DOIVENT avoir des **labels texte visibles** (pas juste des icônes).

#### Variantes de Boutons

| Classe | Usage |
|--------|-------|
| `fr-btn` | Bouton primaire |
| `fr-btn--secondary` | Bouton secondaire |
| `fr-btn--tertiary` | Bouton tertiaire (sans fond) |
| `fr-btn--tertiary-no-outline` | Tertiaire sans bordure |

#### Tailles

| Classe | Taille |
|--------|--------|
| `fr-btn--sm` | Petit |
| `fr-btn` | Normal (défaut) |
| `fr-btn--lg` | Grand |

#### Boutons avec Icônes

**❌ INTERDIT** :
```html
<button class="fr-btn fr-icon-edit-line" title="Modifier"></button>
```

**✅ CORRECT** :
```html
<div class="fr-btns-group fr-btns-group--icon-left">
  <button class="fr-btn fr-icon-edit-line fr-btn--secondary">
    Modifier
  </button>
</div>
```

**⚠️ Points clés** :
- L'icône (`fr-icon-xxx`) doit venir **AVANT** `fr-btn--secondary`
- Le groupe DOIT avoir `fr-btns-group--icon-left` (ou `--icon-right`)
- **NE PAS** utiliser `fr-btn--icon-left` directement sur le bouton

#### Groupes de Boutons

```html
<div class="fr-btns-group fr-btns-group--inline-sm">
  <button class="fr-btn fr-btn--sm">Valider</button>
  <button class="fr-btn fr-btn--secondary fr-btn--sm">Annuler</button>
</div>
```

**Exemple complet groupe avec icônes** :
```html
<div class="fr-btns-group fr-btns-group--inline-sm fr-btns-group--icon-left">
  <button class="fr-btn fr-icon-add-line fr-btn--secondary" onclick="action()">
    Ajouter
  </button>
  <button class="fr-btn fr-icon-check-line fr-btn--secondary" onclick="action()">
    Valider
  </button>
</div>
```

---

### Icônes (Icons)

**Bibliothèque** : Remix Icons (intégrée DSFR)

#### Tailles

| Classe | Taille | Usage |
|--------|--------|-------|
| `fr-icon--sm` | 16px | Avec texte XS/SM |
| `fr-icon` | 24px | Défaut, avec texte MD |
| `fr-icon--lg` | 32px | Avec texte LG |

#### Utilisation

```html
<!-- Avec texte visible -->
<a href="#" class="fr-link">
  <span aria-hidden="true" class="fr-icon-file-pdf-line"></span>
  Télécharger le PDF
</a>

<!-- Icône seule (éviter si possible) -->
<a href="#" title="Imprimer" aria-label="Imprimer">
  <span aria-hidden="true" class="fr-icon-printer-line"></span>
  <span class="sr-only">Imprimer</span>
</a>
```

**Liste icônes** : https://www.systeme-de-design.gouv.fr/elements-d-interface/fondamentaux-de-l-identite-de-l-etat/icone

---

### Alertes (Alerts)

**❌ INTERDIT** : `alert()`, `confirm()`, `prompt()` natifs JavaScript

**✅ REQUIS** : Composant DSFR `fr-alert`

#### Types d'Alertes

| Classe | Type |
|--------|------|
| `fr-alert--info` | Information |
| `fr-alert--success` | Succès |
| `fr-alert--warning` | Avertissement |
| `fr-alert--error` | Erreur |

#### Structure

```html
<div class="fr-alert fr-alert--success fr-alert--sm fr-mb-2w">
  <p class="fr-alert__title">Opération réussie</p>
  <p>Votre demande a été enregistrée.</p>
</div>
```

#### Notification JavaScript Standardisée (Projet Grist)

```javascript
function showNotification(message, type = 'success') {
  const container = document.getElementById('notifications-container');
  const notif = document.createElement('div');
  notif.className = `fr-alert fr-alert--${type} fr-alert--sm fr-mb-2w`;
  notif.innerHTML = `<p class="fr-alert__title">${message}</p>`;
  notif.style.animation = 'slideInRight 0.3s ease';
  container.appendChild(notif);

  // Auto-dismiss après 4s
  setTimeout(() => {
    notif.style.animation = 'slideOutRight 0.3s ease';
    setTimeout(() => notif.remove(), 300);
  }, 4000);
}

// Utilisation
showNotification('Données enregistrées', 'success');
showNotification('Erreur de validation', 'error');
showNotification('Attention : champ requis', 'warning');
showNotification('Information mise à jour', 'info');
```

**Conteneur requis** :
```html
<div id="notifications-container"
     style="position: fixed; top: 20px; right: 20px; z-index: 9999; max-width: 400px;">
</div>
```

---

### Cards (Cartes)

```html
<div class="fr-card">
  <div class="fr-card__body">
    <div class="fr-card__content">
      <h3 class="fr-card__title">
        <a href="#">Titre de la carte</a>
      </h3>
      <p class="fr-card__desc">Description de la carte.</p>
    </div>
  </div>
  <div class="fr-card__header">
    <div class="fr-card__img">
      <img src="image.jpg" class="fr-responsive-img" alt="Description" />
    </div>
  </div>
</div>
```

---

### Badges

```html
<!-- Badge info (défaut) -->
<p class="fr-badge">Info</p>

<!-- Badge success -->
<p class="fr-badge fr-badge--success">Validé</p>

<!-- Badge error -->
<p class="fr-badge fr-badge--error">Erreur</p>

<!-- Badge avec icône -->
<p class="fr-badge fr-badge--success">
  <span class="fr-icon-check-line" aria-hidden="true"></span>
  Succès
</p>

<!-- Badge sans icône explicite -->
<p class="fr-badge fr-badge--no-icon">Badge simple</p>

<!-- Badge taille SM -->
<p class="fr-badge fr-badge--sm fr-badge--info">Info compacte</p>
```

---

### Formulaires

```html
<div class="fr-input-group">
  <label class="fr-label" for="text-input">
    Label du champ
    <span class="fr-hint-text">Texte d'aide optionnel</span>
  </label>
  <input class="fr-input"
         type="text"
         id="text-input"
         name="text-input"
         aria-label="Label accessible" />
</div>

<!-- Champ avec erreur -->
<div class="fr-input-group fr-input-group--error">
  <label class="fr-label" for="text-error">Champ requis</label>
  <input class="fr-input fr-input--error"
         type="text"
         id="text-error"
         aria-describedby="text-error-desc" />
  <p id="text-error-desc" class="fr-error-text">Ce champ est obligatoire</p>
</div>

<!-- Select / Liste déroulante -->
<div class="fr-select-group">
  <label class="fr-label" for="select">Label</label>
  <select class="fr-select" id="select" name="select">
    <option value="" selected disabled hidden>Sélectionner une option</option>
    <option value="1">Option 1</option>
    <option value="2">Option 2</option>
  </select>
</div>
```

---

## ♿ Accessibilité

### Conformité RGAA 4.1

**Le DSFR garantit 100% de conformité RGAA 4.1** sur tous ses composants officiels.

### Attributs ARIA Obligatoires

#### Sur les Formulaires

```html
<!-- Label explicite -->
<label class="fr-label" for="email">Email</label>
<input class="fr-input"
       type="email"
       id="email"
       name="email"
       aria-label="Adresse email"
       aria-required="true" />
```

#### Sur les Boutons

```html
<!-- Bouton avec texte visible (préféré) -->
<button class="fr-btn">Enregistrer</button>

<!-- Bouton icône seule (si vraiment nécessaire) -->
<button class="fr-btn" aria-label="Fermer" title="Fermer">
  <span class="fr-icon-close-line" aria-hidden="true"></span>
</button>
```

#### Sur les Régions de Page

```html
<!-- Header -->
<header role="banner" class="fr-header">...</header>

<!-- Navigation principale -->
<nav role="navigation" aria-label="Menu principal">...</nav>

<!-- Contenu principal -->
<main id="content" role="main">...</main>

<!-- Footer -->
<footer role="contentinfo" class="fr-footer">...</footer>
```

### Navigation Clavier

**Tous les composants DSFR sont navigables au clavier** :
- `Tab` : Navigation entre éléments
- `Enter` / `Space` : Activation boutons/liens
- `Esc` : Fermeture modales/dropdowns
- Flèches : Navigation dans menus/accordéons

### Contrastes

**Contrastes WCAG 2.1 AA garantis** :
- Texte normal : ≥4.5:1
- Texte large : ≥3:1
- Composants UI : ≥3:1

**Outils de vérification** :
- Stark (plugin Figma/Sketch)
- Cluse (outil en ligne)
- Chrome DevTools (Accessibility panel)

---

## 🌓 Mode Sombre

### Principe

Le DSFR supporte **nativement le mode sombre** via un système de tokens qui s'adaptent automatiquement.

### Configuration

#### Script de Gestion du Thème (OBLIGATOIRE)

**Ce script DOIT être placé AVANT le chargement CSS** :

```html
<script>
  (function () {
    const scheme = localStorage.getItem("fr-scheme") || "system";
    document.documentElement.setAttribute("data-fr-scheme", scheme);

    if (scheme === "system") {
      const prefersDark = window.matchMedia("(prefers-color-scheme: dark)").matches;
      document.documentElement.setAttribute("data-fr-theme", prefersDark ? "dark" : "light");

      // Écoute changements préférence système
      window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", (e) => {
        if (localStorage.getItem("fr-scheme") === "system") {
          document.documentElement.setAttribute("data-fr-theme", e.matches ? "dark" : "light");
        }
      });
    } else {
      document.documentElement.setAttribute("data-fr-theme", scheme);
    }
  })();
</script>
```

### Basculer le Thème

```javascript
// Forcer mode clair
localStorage.setItem("fr-scheme", "light");
document.documentElement.setAttribute("data-fr-scheme", "light");
document.documentElement.setAttribute("data-fr-theme", "light");

// Forcer mode sombre
localStorage.setItem("fr-scheme", "dark");
document.documentElement.setAttribute("data-fr-scheme", "dark");
document.documentElement.setAttribute("data-fr-theme", "dark");

// Mode système (défaut)
localStorage.setItem("fr-scheme", "system");
document.documentElement.setAttribute("data-fr-scheme", "system");
const prefersDark = window.matchMedia("(prefers-color-scheme: dark)").matches;
document.documentElement.setAttribute("data-fr-theme", prefersDark ? "dark" : "light");
```

### Composant Switch Thème (Optionnel)

```html
<div class="fr-toggle">
  <input type="checkbox"
         class="fr-toggle__input"
         id="theme-toggle"
         onclick="toggleTheme()" />
  <label class="fr-toggle__label" for="theme-toggle" data-fr-checked-label="Mode sombre" data-fr-unchecked-label="Mode clair"></label>
</div>

<script>
function toggleTheme() {
  const currentScheme = localStorage.getItem("fr-scheme") || "light";
  const newScheme = currentScheme === "dark" ? "light" : "dark";
  localStorage.setItem("fr-scheme", newScheme);
  document.documentElement.setAttribute("data-fr-scheme", newScheme);
  document.documentElement.setAttribute("data-fr-theme", newScheme);
}
</script>
```

---

## 🚫 Règles Strictes & Contraintes

### ❌ INTERDIT (Violations Graves)

1. **Modifier l'ordre de chargement CSS** → Cause bugs thème/composants
2. **Ajouter des `style=""` inline** → Utiliser classes utilitaires DSFR
3. **Utiliser `alert()`, `confirm()`, `prompt()`** → Composant `fr-alert`
4. **Créer boutons sans texte** → Labels texte obligatoires
5. **Utiliser couleurs hors palette DSFR** → Decision tokens uniquement
6. **Utiliser polices non autorisées** → Marianne® et Spectral uniquement
7. **Mélanger couleurs clair/sombre** → Respect mode thème strict
8. **Modifier composants DSFR** → Utiliser as-is ou créer composant custom
9. **Deux fonds alternatifs adjacents** → Toujours séparer par fond blanc
10. **Composants interactifs sur deux fonds** → Rester dans une zone de fond

---

### ✅ OBLIGATOIRE (Conformité)

1. **Inclure `aria-label` sur inputs dynamiques** → Accessibilité
2. **Tester mode sombre** → Vérifier `data-fr-theme="dark"`
3. **Utiliser decision tokens** → Jamais options directes
4. **Respecter hiérarchie grille** → `fr-container` → `fr-grid-row` → `fr-col`
5. **Utiliser tokens espacement** → Pas de valeurs arbitraires (`margin: 17px` ❌)
6. **Fond blanc par défaut** → Exigence légale
7. **Implémentation DSFR complète** → All or nothing

---

## 📚 Ressources & Documentation

### Liens Officiels

- **Site DSFR** : https://www.systeme-de-design.gouv.fr/
- **Documentation technique** : https://www.systeme-de-design.gouv.fr/developpeurs
- **Composants** : https://www.systeme-de-design.gouv.fr/composants-et-modeles
- **GitHub DSFR** : https://github.com/GouvernementFR/dsfr
- **NPM Package** : `@gouvfr/dsfr`

### Outils

- **Figma DSFR** : https://www.figma.com/@designgouv
- **Vérificateur accessibilité** : https://www.cluse.fr/
- **RGAA 4.1** : https://accessibilite.numerique.gouv.fr/

### Support

- **Forum DSFR** : https://github.com/GouvernementFR/dsfr/discussions
- **Issues GitHub** : https://github.com/GouvernementFR/dsfr/issues

---

## 📝 Checklist de Conformité DSFR

Avant de valider votre implémentation, vérifiez :

- [ ] **CSS chargé dans l'ordre correct** (core → utility → icons → scheme → components)
- [ ] **Script thème présent AVANT CSS**
- [ ] **Aucun style inline** (`style=""`)
- [ ] **Tous les boutons ont des labels texte visibles**
- [ ] **Pas d'`alert()` JavaScript natif** → `fr-alert` DSFR
- [ ] **Uniquement decision tokens couleur** (pas d'options directes)
- [ ] **Uniquement polices Marianne® et Spectral**
- [ ] **Grille respectée** (`fr-container` → `fr-grid-row` → `fr-col`)
- [ ] **Espacements via tokens DSFR** (classes `fr-m*`, `fr-p*`)
- [ ] **Fond par défaut blanc** (`$background-default-grey`)
- [ ] **Attributs ARIA présents** (`aria-label`, `role`, etc.)
- [ ] **Mode sombre testé** (`data-fr-theme="dark"`)
- [ ] **Navigation clavier fonctionnelle**
- [ ] **Contrastes WCAG 2.1 AA respectés**

---

**Document créé le** : 2025-10-09
**Version DSFR** : 1.14
**Projet** : Grist SP2C - Gendarmerie Nationale
**Dernière mise à jour** : 2025-10-09
