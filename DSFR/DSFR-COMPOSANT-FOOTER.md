# DSFR - Composant Footer (Pied de page)

## Vue d'ensemble

Le footer (pied de page) est un composant DSFR obligatoire qui structure le bas de page avec des informations institutionnelles, des liens de navigation secondaire et des mentions légales. Il est strictement encadré par la charte de l'État.

**Version DSFR**: 1.14
**Composant**: Footer
**Fichier CSS**: `@gouvfr/dsfr/dist/component/footer/footer.min.css`

## Structure HTML complète

### 1. Structure de base

```html
<footer class="fr-footer" role="contentinfo" id="footer">
  <div class="fr-container">
    <!-- Section supérieure (optionnelle) -->
    <div class="fr-footer__top">
      <!-- Navigation et contenu contextuel -->
    </div>

    <!-- Corps du footer (obligatoire) -->
    <div class="fr-footer__body">
      <!-- Logo et contenu principal -->
    </div>

    <!-- Section inférieure (obligatoire) -->
    <div class="fr-footer__bottom">
      <!-- Liens légaux et licence -->
    </div>
  </div>
</footer>
```

### 2. Section supérieure (`fr-footer__top`) - Optionnelle

Navigation secondaire organisée en colonnes :

```html
<div class="fr-footer__top">
  <div class="fr-container">
    <div class="fr-grid-row fr-grid-row--gutters fr-grid-row--start">

      <!-- Colonne 1 -->
      <div class="fr-col-12 fr-col-sm-3 fr-col-md-2">
        <h3 class="fr-footer__top-cat">Catégorie 1</h3>
        <ul class="fr-footer__top-list">
          <li>
            <a class="fr-footer__top-link" href="#">Lien 1</a>
          </li>
          <li>
            <a class="fr-footer__top-link" href="#">Lien 2</a>
          </li>
        </ul>
      </div>

      <!-- Colonne 2 -->
      <div class="fr-col-12 fr-col-sm-3 fr-col-md-2">
        <h3 class="fr-footer__top-cat">Catégorie 2</h3>
        <ul class="fr-footer__top-list">
          <li>
            <a class="fr-footer__top-link" href="#">Lien 3</a>
          </li>
        </ul>
      </div>

      <!-- Colonne 3 -->
      <div class="fr-col-12 fr-col-sm-3 fr-col-md-2">
        <h3 class="fr-footer__top-cat">Catégorie 3</h3>
        <ul class="fr-footer__top-list">
          <li>
            <a class="fr-footer__top-link" href="#">Lien 4</a>
          </li>
        </ul>
      </div>

    </div>
  </div>
</div>
```

**Règles de colonnes** :
- Mobile (XS) : `fr-col-12` (pleine largeur)
- Tablette (SM) : `fr-col-sm-3` (4 colonnes max)
- Desktop (MD+) : `fr-col-md-2` (6 colonnes max)
- Utiliser `fr-grid-row--start` pour alignement en haut

### 3. Corps du footer (`fr-footer__body`) - Obligatoire

Contient le logo République Française et le contenu descriptif :

```html
<div class="fr-footer__body">
  <div class="fr-footer__brand fr-enlarge-link">
    <a href="/" title="Retour à l'accueil du site - [Nom du site]">
      <p class="fr-logo">
        République<br />Française
      </p>
    </a>
  </div>

  <div class="fr-footer__content">
    <p class="fr-footer__content-desc">
      [Description du service ou de l'organisme]<br />
      [Ligne 2 optionnelle]<br />
      [Ligne 3 optionnelle]
    </p>
    <ul class="fr-footer__content-list">
      <li class="fr-footer__content-item">
        <a class="fr-footer__content-link"
           target="_blank"
           rel="noopener external"
           title="[Titre] - nouvelle fenêtre"
           href="https://legifrance.gouv.fr">
          legifrance.gouv.fr
        </a>
      </li>
      <li class="fr-footer__content-item">
        <a class="fr-footer__content-link"
           target="_blank"
           rel="noopener external"
           title="gouvernement.fr - nouvelle fenêtre"
           href="https://gouvernement.fr">
          gouvernement.fr
        </a>
      </li>
      <li class="fr-footer__content-item">
        <a class="fr-footer__content-link"
           target="_blank"
           rel="noopener external"
           title="service-public.fr - nouvelle fenêtre"
           href="https://service-public.fr">
          service-public.fr
        </a>
      </li>
      <li class="fr-footer__content-item">
        <a class="fr-footer__content-link"
           target="_blank"
           rel="noopener external"
           title="data.gouv.fr - nouvelle fenêtre"
           href="https://data.gouv.fr">
          data.gouv.fr
        </a>
      </li>
    </ul>
  </div>
</div>
```

**Règles obligatoires** :
- Le logo `fr-logo` DOIT contenir "République<br />Française"
- La classe `fr-enlarge-link` augmente la zone cliquable
- Les liens externes DOIVENT avoir `target="_blank"` et `rel="noopener external"`
- Les titres DOIVENT mentionner "nouvelle fenêtre" pour les liens externes

### 4. Section inférieure (`fr-footer__bottom`) - Obligatoire

Liens légaux obligatoires et informations de licence :

```html
<div class="fr-footer__bottom">
  <ul class="fr-footer__bottom-list">
    <li class="fr-footer__bottom-item">
      <a class="fr-footer__bottom-link" href="#">Plan du site</a>
    </li>
    <li class="fr-footer__bottom-item">
      <a class="fr-footer__bottom-link" href="#">Accessibilité: non conforme</a>
    </li>
    <li class="fr-footer__bottom-item">
      <a class="fr-footer__bottom-link" href="#">Mentions légales</a>
    </li>
    <li class="fr-footer__bottom-item">
      <a class="fr-footer__bottom-link" href="#">Données personnelles</a>
    </li>
    <li class="fr-footer__bottom-item">
      <a class="fr-footer__bottom-link" href="#">Gestion des cookies</a>
    </li>
  </ul>

  <div class="fr-footer__bottom-copy">
    <p>
      Sauf mention contraire, tous les contenus de ce site sont sous
      <a href="https://github.com/etalab/licence-ouverte/blob/master/LO.md"
         target="_blank"
         rel="noopener external"
         title="licence etalab-2.0 - nouvelle fenêtre">
        licence etalab-2.0
      </a>
    </p>
  </div>
</div>
```

**Liens obligatoires** :
- **Accessibilité** : Mention du niveau de conformité RGAA
- **Mentions légales** : Informations légales obligatoires
- **Données personnelles** : Politique de protection des données (RGPD)
- **Gestion des cookies** : Paramètres de consentement

### 5. Intégration des modales (optionnel)

Les modales pour les paramètres de consentement et d'affichage peuvent être ajoutées après le footer :

```html
<!-- Modal Gestion des cookies/consentement -->
<dialog id="fr-consent-modal"
        class="fr-modal"
        role="dialog"
        aria-labelledby="fr-consent-modal-title">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-10 fr-col-lg-8">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button class="fr-btn--close fr-btn"
                    aria-controls="fr-consent-modal"
                    title="Fermer">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h1 id="fr-consent-modal-title" class="fr-modal__title">
              Panneau de gestion des cookies
            </h1>
            <!-- Contenu de gestion des cookies -->
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>

<!-- Modal Paramètres d'affichage -->
<dialog id="fr-theme-modal"
        class="fr-modal"
        role="dialog"
        aria-labelledby="fr-theme-modal-title">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button class="fr-btn--close fr-btn"
                    aria-controls="fr-theme-modal"
                    title="Fermer">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h1 id="fr-theme-modal-title" class="fr-modal__title">
              Paramètres d'affichage
            </h1>
            <!-- Contenu paramètres thème -->
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

## Classes CSS DSFR

### Classes principales

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-footer` | `<footer>` | Conteneur principal du footer |
| `fr-footer__top` | `<div>` | Section supérieure (navigation) |
| `fr-footer__body` | `<div>` | Corps principal (logo + contenu) |
| `fr-footer__bottom` | `<div>` | Section inférieure (liens légaux) |

### Classes de la section supérieure

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-footer__top-cat` | `<h3>` | Titre de catégorie de liens |
| `fr-footer__top-list` | `<ul>` | Liste de liens dans une catégorie |
| `fr-footer__top-link` | `<a>` | Lien de navigation secondaire |

### Classes du corps

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-footer__brand` | `<div>` | Conteneur du logo République Française |
| `fr-footer__content` | `<div>` | Conteneur du contenu descriptif |
| `fr-footer__content-desc` | `<p>` | Paragraphe de description |
| `fr-footer__content-list` | `<ul>` | Liste de liens institutionnels |
| `fr-footer__content-item` | `<li>` | Item de lien institutionnel |
| `fr-footer__content-link` | `<a>` | Lien institutionnel |

### Classes de la section inférieure

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-footer__bottom-list` | `<ul>` | Liste des liens légaux |
| `fr-footer__bottom-item` | `<li>` | Item de lien légal |
| `fr-footer__bottom-link` | `<a>` | Lien légal |
| `fr-footer__bottom-copy` | `<div>` | Conteneur de la mention de licence |

## Variantes

### Footer simple (sans section top)

Pour un footer minimal, omettre la section `fr-footer__top` :

```html
<footer class="fr-footer" role="contentinfo">
  <div class="fr-container">
    <div class="fr-footer__body">
      <!-- Logo et contenu -->
    </div>
    <div class="fr-footer__bottom">
      <!-- Liens légaux -->
    </div>
  </div>
</footer>
```

### Footer avec opérateur (logo partenaire)

Pour ajouter un logo d'organisme partenaire :

```html
<div class="fr-footer__body">
  <div class="fr-footer__brand fr-enlarge-link">
    <a href="/" title="Retour à l'accueil">
      <p class="fr-logo">République<br />Française</p>
    </a>
  </div>

  <div class="fr-footer__operator">
    <img src="/logo-organisme.svg"
         alt="[Nom de l'organisme]"
         style="width: 9.0625rem;" />
  </div>

  <div class="fr-footer__content">
    <!-- Contenu -->
  </div>
</div>
```

## Dépendances CSS

**Ordre de chargement obligatoire** :

```html
<!-- 1. CORE (requis) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/core/core.min.css" />

<!-- 2. UTILITY (requis pour les classes de grille) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/utility/utility.min.css" />

<!-- 3. SCHEME (requis pour le mode sombre) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/scheme/scheme.min.css" />

<!-- 4. FOOTER (composant) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/footer/footer.min.css" />

<!-- 5. MODAL (si modales de consentement/thème) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/modal/modal.min.css" />
```

## JavaScript

### Chargement du script DSFR

Le footer nécessite le script DSFR pour le fonctionnement des modales et des interactions :

```html
<!-- Module JS DSFR (à la fin du <body>) -->
<script type="module"
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/dsfr.module.min.js">
</script>

<!-- Fallback nomodule -->
<script type="text/javascript" nomodule
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/dsfr.nomodule.min.js">
</script>
```

### Gestion du mode sombre

Le footer respecte automatiquement le thème sélectionné via `data-fr-theme` :

```javascript
// Script à placer AVANT les CSS (dans le <head>)
(function () {
  const scheme = localStorage.getItem("fr-scheme") || "system";
  document.documentElement.setAttribute("data-fr-scheme", scheme);

  if (scheme === "system") {
    const prefersDark = window.matchMedia("(prefers-color-scheme: dark)").matches;
    document.documentElement.setAttribute("data-fr-theme", prefersDark ? "dark" : "light");

    window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", (e) => {
      document.documentElement.setAttribute("data-fr-theme", e.matches ? "dark" : "light");
    });
  } else {
    document.documentElement.setAttribute("data-fr-theme", scheme);
  }
})();
```

### Ouverture des modales

Pour ouvrir les modales de consentement ou de thème depuis le footer :

```html
<!-- Lien vers modal de consentement -->
<a class="fr-footer__bottom-link"
   href="#"
   aria-controls="fr-consent-modal"
   data-fr-opened="false">
  Gestion des cookies
</a>

<!-- Lien vers modal de thème -->
<a class="fr-footer__bottom-link"
   href="#"
   aria-controls="fr-theme-modal"
   data-fr-opened="false">
  Paramètres d'affichage
</a>
```

**Le script DSFR gère automatiquement l'ouverture/fermeture** via les attributs `aria-controls` et `data-fr-opened`.

## Accessibilité

### Attributs ARIA obligatoires

| Élément | Attribut | Valeur | Justification |
|---------|----------|--------|---------------|
| `<footer>` | `role` | `"contentinfo"` | Identifie le pied de page (RGAA) |
| `<footer>` | `id` | `"footer"` | Ancre pour navigation (recommandé) |
| Liens externes | `rel` | `"noopener external"` | Sécurité et sémantique |
| Liens externes | `target` | `"_blank"` | Ouverture nouvelle fenêtre |
| Liens externes | `title` | `"[titre] - nouvelle fenêtre"` | Information utilisateur |

### Conformité RGAA 4.1

Le footer DSFR est **100% conforme RGAA 4.1** :

- ✅ Critère 9.1 : Titres de niveaux cohérents (`<h3>` dans sections)
- ✅ Critère 10.7 : Pas de scroll horizontal sur petits écrans
- ✅ Critère 11.1 : Tous les champs de formulaire ont des labels (modales)
- ✅ Critère 12.6 : Regroupements de liens dans des listes
- ✅ Critère 12.8 : Ordre de tabulation logique

### Navigation au clavier

| Touche | Action |
|--------|--------|
| `Tab` | Navigation entre les liens |
| `Shift + Tab` | Navigation arrière |
| `Enter` | Activation du lien ou ouverture modale |
| `Esc` | Fermeture de la modale (si ouverte) |

## Tokens de couleurs

Le footer utilise les tokens de décision DSFR suivants :

### Arrière-plans

```scss
// Arrière-plan principal du footer
$background-elevated-grey: #ffffff (light) / #1e1e1e (dark)

// Arrière-plan section top
$background-alt-grey: #f6f6f6 (light) / #2a2a2a (dark)
```

### Textes

```scss
// Titres de catégories (fr-footer__top-cat)
$text-title-grey: #161616 (light) / #f6f6f6 (dark)

// Liens de navigation
$text-action-high-blue-france: #000091 (light) / #8585f6 (dark)

// Texte de description
$text-default-grey: #3a3a3a (light) / #cecece (dark)

// Mention de copyright
$text-mention-grey: #666666 (light) / #9c9c9c (dark)
```

### Bordures

```scss
// Bordure supérieure du footer__bottom
$border-default-grey: #dddddd (light) / #3a3a3a (dark)
```

## Espacement

Le footer respecte le **système de grille 8 points** :

```scss
// Espacement vertical des sections
.fr-footer__top {
  padding-top: 10v;    // 40px / 2.5rem
  padding-bottom: 8v;  // 32px / 2rem
}

.fr-footer__body {
  padding-top: 8v;     // 32px / 2rem
  padding-bottom: 8v;  // 32px / 2rem
}

.fr-footer__bottom {
  padding-top: 4v;     // 16px / 1rem
  padding-bottom: 4v;  // 16px / 1rem
}

// Espacement entre les colonnes de liens
.fr-footer__top-list li {
  margin-bottom: 2v;   // 8px / 0.5rem
}

// Espacement entre les liens légaux
.fr-footer__bottom-item {
  margin-right: 4v;    // 16px / 1rem
}
```

## Règles strictes

### ✅ OBLIGATOIRE

1. **Logo République Française** : DOIT contenir "République<br />Française" (texte exact)
2. **Attribut `role="contentinfo"`** : Obligatoire sur `<footer>`
3. **Liens légaux** : Accessibilité, Mentions légales, Données personnelles
4. **Liens externes** : `target="_blank"` + `rel="noopener external"` + mention "nouvelle fenêtre" dans `title`
5. **Ordre CSS** : core → utility → scheme → footer → modal
6. **Grille responsive** : Utiliser `fr-grid-row` et `fr-col-*` pour les colonnes
7. **Licence** : Mentionner la licence des contenus (etalab-2.0 recommandée)

### ❌ INTERDIT

1. **Modifier le logo** : Pas de changement de typographie ou couleur sur "République Française"
2. **Omettre les liens légaux** : Accessibilité et Mentions légales sont OBLIGATOIRES
3. **Styles inline** : Pas de `style=""` sur les éléments footer (sauf images opérateur)
4. **Modifier les classes DSFR** : Utiliser les classes telles quelles sans surcharge
5. **Mélanger thèmes clair/sombre** : Utiliser uniquement les tokens de décision

## Exemple complet (Projet Grist SP2C)

```html
<!DOCTYPE html>
<html lang="fr" data-fr-scheme="system">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Gestion de projet - SP2C</title>

  <!-- Script thème (AVANT CSS) -->
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

  <!-- CSS DSFR -->
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/core/core.min.css" />
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/utility/utility.min.css" />
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/scheme/scheme.min.css" />
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/footer/footer.min.css" />
</head>
<body>

  <!-- Contenu de la page -->
  <main>
    <!-- ... -->
  </main>

  <!-- FOOTER DSFR -->
  <footer class="fr-footer" role="contentinfo" id="footer">
    <div class="fr-container">

      <!-- Corps du footer -->
      <div class="fr-footer__body">
        <div class="fr-footer__brand fr-enlarge-link">
          <a href="/" title="Retour à l'accueil - Gestion de projet SP2C">
            <p class="fr-logo">République<br />Française</p>
          </a>
        </div>

        <div class="fr-footer__content">
          <p class="fr-footer__content-desc">
            Gendarmerie Nationale<br />
            Direction opérations emploi<br />
            Service du pilotage et de la cohérence capacitaire
          </p>
          <ul class="fr-footer__content-list">
            <li class="fr-footer__content-item">
              <a class="fr-footer__content-link"
                 target="_blank"
                 rel="noopener external"
                 title="legifrance.gouv.fr - nouvelle fenêtre"
                 href="https://legifrance.gouv.fr">
                legifrance.gouv.fr
              </a>
            </li>
            <li class="fr-footer__content-item">
              <a class="fr-footer__content-link"
                 target="_blank"
                 rel="noopener external"
                 title="gouvernement.fr - nouvelle fenêtre"
                 href="https://gouvernement.fr">
                gouvernement.fr
              </a>
            </li>
            <li class="fr-footer__content-item">
              <a class="fr-footer__content-link"
                 target="_blank"
                 rel="noopener external"
                 title="service-public.fr - nouvelle fenêtre"
                 href="https://service-public.fr">
                service-public.fr
              </a>
            </li>
            <li class="fr-footer__content-item">
              <a class="fr-footer__content-link"
                 target="_blank"
                 rel="noopener external"
                 title="data.gouv.fr - nouvelle fenêtre"
                 href="https://data.gouv.fr">
                data.gouv.fr
              </a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Section inférieure -->
      <div class="fr-footer__bottom">
        <ul class="fr-footer__bottom-list">
          <li class="fr-footer__bottom-item">
            <a class="fr-footer__bottom-link" href="#">Accessibilité: non conforme</a>
          </li>
          <li class="fr-footer__bottom-item">
            <a class="fr-footer__bottom-link" href="#">Mentions légales</a>
          </li>
          <li class="fr-footer__bottom-item">
            <a class="fr-footer__bottom-link" href="#">Données personnelles</a>
          </li>
        </ul>

        <div class="fr-footer__bottom-copy">
          <p>
            Sauf mention contraire, tous les contenus de ce site sont sous
            <a href="https://github.com/etalab/licence-ouverte/blob/master/LO.md"
               target="_blank"
               rel="noopener external"
               title="licence etalab-2.0 - nouvelle fenêtre">
              licence etalab-2.0
            </a>
          </p>
        </div>
      </div>

    </div>
  </footer>

  <!-- Scripts DSFR (à la fin du body) -->
  <script type="module"
          src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/dsfr.module.min.js">
  </script>
  <script type="text/javascript" nomodule
          src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/dsfr.nomodule.min.js">
  </script>

</body>
</html>
```

## Ressources

- **Documentation officielle DSFR** : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/pied-de-page
- **RGAA 4.1** : https://www.numerique.gouv.fr/publications/rgaa-accessibilite/
- **Licence Ouverte 2.0** : https://github.com/etalab/licence-ouverte/blob/master/LO.md
- **Storybook DSFR Footer** : https://storybook.systeme-de-design.gouv.fr/?path=/docs/composants-footer

## Notes de version

**Version DSFR 1.14** :
- Structure du footer stabilisée
- Support complet du mode sombre (`data-fr-theme`)
- Classes utilitaires responsive pour colonnes
- Conformité RGAA 4.1 à 100%

**Compatibilité navigateurs** :
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Support IE11 via bundle `nomodule`
