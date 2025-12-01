# DSFR - Composant Modale (Modal)

## Vue d'ensemble

La modale est un composant DSFR de mise en forme permettant de concentrer l'attention de l'usager exclusivement sur une tâche ou un élément d'information, sans perdre le contexte de la page en cours. Elle s'affiche en overlay plein écran.

**Version DSFR**: 1.14
**Composant**: Modal
**Fichier CSS**: `@gouvfr/dsfr/dist/component/modal/modal.min.css`
**JavaScript**: **OBLIGATOIRE**

## Caractéristiques

- **Usage** : Focus sur une tâche ou information importante
- **Affichage** : Overlay plein écran avec fond semi-transparent
- **Interaction** : Bloque l'interaction avec la page sous-jacente
- **Fermeture** : Bouton, clic sur fond (optionnel), touche Esc
- **Accessibilité** : Piège le focus, RGAA 4.1 conforme

## Structure HTML complète

### 1. Structure de base

```html
<!-- Bouton d'ouverture -->
<button data-fr-opened="false"
        aria-controls="modal-id"
        type="button"
        class="fr-btn">
  Ouvrir la modale
</button>

<!-- Modale -->
<dialog id="modal-id"
        class="fr-modal"
        aria-labelledby="modal-title"
        aria-modal="true">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
        <div class="fr-modal__body">

          <!-- Entête (obligatoire) -->
          <div class="fr-modal__header">
            <button aria-controls="modal-id"
                    title="Fermer"
                    type="button"
                    class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>

          <!-- Contenu (obligatoire) -->
          <div class="fr-modal__content">
            <h2 id="modal-title" class="fr-modal__title">
              <span class="fr-icon-arrow-right-line fr-icon--lg" aria-hidden="true"></span>
              Titre de la modale
            </h2>
            <p>
              Contenu de la modale. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </p>
          </div>

        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Éléments obligatoires** :
- Bouton d'ouverture avec `aria-controls` et `data-fr-opened`
- `<dialog>` avec `id`, `aria-labelledby`, `aria-modal`
- `fr-modal__header` avec bouton de fermeture
- `fr-modal__content` avec titre (`fr-modal__title`)

**Éléments optionnels** :
- `fr-modal__footer` : zone d'actions (boutons)
- Icône dans le titre

### 2. Anatomie détaillée

#### Le bouton d'ouverture

```html
<button data-fr-opened="false"
        aria-controls="modal-id"
        type="button"
        class="fr-btn">
  Ouvrir la modale
</button>
```

**Attributs obligatoires** :
- `type="button"` : évite la soumission de formulaire
- `aria-controls` : référence l'ID de la modale
- `data-fr-opened` : état de la modale (`"false"` par défaut)
- `class="fr-btn"` : style bouton DSFR

**Valeurs de `data-fr-opened`** :
- `"false"` : modale fermée
- `"true"` : modale ouverte (géré automatiquement par le JS)

#### La modale `<dialog>`

```html
<dialog id="modal-id"
        class="fr-modal"
        aria-labelledby="modal-title"
        aria-modal="true">
  <!-- Contenu -->
</dialog>
```

**Attributs obligatoires** :
- `id` : identifiant unique (lié au bouton via `aria-controls`)
- `class="fr-modal"` : classe de style
- `aria-labelledby` : référence l'ID du titre
- `aria-modal="true"` : indique que c'est une modale

**Attributs optionnels** :
- `data-fr-concealing-backdrop="false"` : désactive la fermeture au clic sur le fond
- `data-fr-js-modal="true"` : ajouté automatiquement par le JS

**Classes modificatrices** :
- `fr-modal--top` : zone d'action en haut (mobile)

#### La structure de grille

```html
<div class="fr-container fr-container--fluid fr-container-md">
  <div class="fr-grid-row fr-grid-row--center">
    <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
      <!-- Corps de la modale -->
    </div>
  </div>
</div>
```

**Rôle** : Centre la modale et définit sa largeur.

**Tailles de modale** (modifier les classes de colonne) :
- **SM** : `fr-col-12 fr-col-md-6 fr-col-lg-4`
- **MD** (défaut) : `fr-col-12 fr-col-md-8 fr-col-lg-6`
- **LG** : `fr-col-12 fr-col-md-10 fr-col-lg-8`

#### Le corps de la modale `fr-modal__body`

```html
<div class="fr-modal__body">
  <div class="fr-modal__header"><!-- Entête --></div>
  <div class="fr-modal__content"><!-- Contenu --></div>
  <div class="fr-modal__footer"><!-- Pied (optionnel) --></div>
</div>
```

**Structure obligatoire** : header → content (→ footer optionnel)

#### L'entête `fr-modal__header`

```html
<div class="fr-modal__header">
  <button aria-controls="modal-id"
          title="Fermer"
          type="button"
          class="fr-btn--close fr-btn">
    Fermer
  </button>
</div>
```

**Caractéristiques** :
- **OBLIGATOIRE**
- Contient uniquement le bouton de fermeture
- Le bouton **DOIT** avoir `aria-controls` référençant la modale
- Le bouton **DOIT** avoir `type="button"`

#### Le contenu `fr-modal__content`

```html
<div class="fr-modal__content">
  <h2 id="modal-title" class="fr-modal__title">
    <span class="fr-icon-arrow-right-line fr-icon--lg" aria-hidden="true"></span>
    Titre de la modale
  </h2>
  <p>Contenu libre de la modale.</p>
</div>
```

**Caractéristiques** :
- **OBLIGATOIRE**
- Doit contenir un titre avec `id` (référencé par `aria-labelledby`)
- Le titre peut être un `<h1>` à `<h6>` ou un `<p>` avec `fr-modal__title`
- Le contenu est libre mais doit utiliser des balises sémantiques
- Si le contenu est trop long, un scroll apparaît automatiquement

#### Le pied de page `fr-modal__footer`

```html
<div class="fr-modal__footer">
  <ul class="fr-btns-group fr-btns-group--right fr-btns-group--inline-reverse fr-btns-group--inline-lg fr-btns-group--icon-left">
    <li>
      <button type="button" class="fr-btn fr-icon-checkbox-circle-line fr-btn--icon-left">
        Action principale
      </button>
    </li>
    <li>
      <button type="button" class="fr-btn fr-btn--secondary">
        Annuler
      </button>
    </li>
  </ul>
</div>
```

**Caractéristiques** :
- **OPTIONNEL**
- Contient un groupe de boutons d'action
- Classes recommandées : `fr-btns-group--right`, `fr-btns-group--inline-reverse`
- Peut contenir un seul bouton primaire ou un groupe hiérarchisé

## Classes CSS DSFR

### Classes principales

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-modal` | `<dialog>` | Conteneur principal de la modale |
| `fr-modal__body` | `<div>` | Corps de la modale |
| `fr-modal__header` | `<div>` | Entête avec bouton fermeture (obligatoire) |
| `fr-modal__content` | `<div>` | Zone de contenu (obligatoire) |
| `fr-modal__title` | `<hx>` ou `<p>` | Titre de la modale (obligatoire) |
| `fr-modal__footer` | `<div>` | Pied de page avec actions (optionnel) |

### Modificateurs

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-modal--top` | `<dialog>` | Zone d'action en haut (mobile uniquement) |

### Tailles de modale

**Modifier les classes de colonne** :

| Taille | Classes de colonne |
|--------|--------------------|
| SM (petite) | `fr-col-12 fr-col-md-6 fr-col-lg-4` |
| MD (moyenne, défaut) | `fr-col-12 fr-col-md-8 fr-col-lg-6` |
| LG (grande) | `fr-col-12 fr-col-md-10 fr-col-lg-8` |

## Variantes

### 1. Modale simple

```html
<button data-fr-opened="false" aria-controls="modal-simple" type="button" class="fr-btn">
  Modale simple
</button>

<dialog id="modal-simple" class="fr-modal" aria-labelledby="modal-simple-title" aria-modal="true">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button aria-controls="modal-simple" title="Fermer" type="button" class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h2 id="modal-simple-title" class="fr-modal__title">
              Information importante
            </h2>
            <p>
              Cette modale contient une information importante que l'utilisateur doit lire.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Usage** : Affichage d'information sans action requise.

### 2. Modale avec zone d'action

```html
<button data-fr-opened="false" aria-controls="modal-action" type="button" class="fr-btn">
  Modale avec actions
</button>

<dialog id="modal-action" class="fr-modal" aria-labelledby="modal-action-title" aria-modal="true">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button aria-controls="modal-action" title="Fermer" type="button" class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h2 id="modal-action-title" class="fr-modal__title">
              Confirmer la suppression
            </h2>
            <p>
              Êtes-vous sûr de vouloir supprimer cet élément ? Cette action est irréversible.
            </p>
          </div>
          <div class="fr-modal__footer">
            <ul class="fr-btns-group fr-btns-group--right fr-btns-group--inline-reverse fr-btns-group--inline-lg">
              <li>
                <button type="button" class="fr-btn" onclick="confirmDelete()">
                  Confirmer
                </button>
              </li>
              <li>
                <button type="button" class="fr-btn fr-btn--secondary" aria-controls="modal-action">
                  Annuler
                </button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Usage** : Confirmation d'action, choix utilisateur.

### 3. Modale avec zone d'action en haut (mobile)

```html
<button data-fr-opened="false" aria-controls="modal-top" type="button" class="fr-btn">
  Modale actions en haut
</button>

<dialog id="modal-top" class="fr-modal fr-modal--top" aria-labelledby="modal-top-title" aria-modal="true">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button aria-controls="modal-top" title="Fermer" type="button" class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h2 id="modal-top-title" class="fr-modal__title">
              Formulaire long
            </h2>
            <p>Contenu très long nécessitant un scroll...</p>
          </div>
          <div class="fr-modal__footer">
            <ul class="fr-btns-group fr-btns-group--right fr-btns-group--inline-lg">
              <li>
                <button type="submit" class="fr-btn">Enregistrer</button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Usage** : Contenu long, boutons d'action visibles en haut sur mobile.
**Modificateur** : `fr-modal--top`

### 4. Modale non refermable au clic sur le fond

```html
<button data-fr-opened="false" aria-controls="modal-no-backdrop" type="button" class="fr-btn">
  Modale critique
</button>

<dialog id="modal-no-backdrop"
        class="fr-modal"
        aria-labelledby="modal-no-backdrop-title"
        aria-modal="true"
        data-fr-concealing-backdrop="false">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button aria-controls="modal-no-backdrop" title="Fermer" type="button" class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h2 id="modal-no-backdrop-title" class="fr-modal__title">
              Action requise
            </h2>
            <p>
              Vous devez obligatoirement répondre à cette demande avant de continuer.
            </p>
          </div>
          <div class="fr-modal__footer">
            <ul class="fr-btns-group fr-btns-group--right">
              <li>
                <button type="button" class="fr-btn" onclick="handleCriticalAction()">
                  Valider
                </button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Usage** : Action critique obligatoire.
**Attribut** : `data-fr-concealing-backdrop="false"`

### 5. Modale avec icône dans le titre

```html
<dialog id="modal-icon" class="fr-modal" aria-labelledby="modal-icon-title" aria-modal="true">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button aria-controls="modal-icon" title="Fermer" type="button" class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h2 id="modal-icon-title" class="fr-modal__title">
              <span class="fr-icon-success-line fr-icon--lg" aria-hidden="true"></span>
              Opération réussie
            </h2>
            <p>Les modifications ont été enregistrées avec succès.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Usage** : Feedback visuel avec icône (succès, erreur, info).

### 6. Modale grande taille (LG)

```html
<dialog id="modal-lg" class="fr-modal" aria-labelledby="modal-lg-title" aria-modal="true">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <!-- Grande taille : 8 col LG, 10 col MD -->
      <div class="fr-col-12 fr-col-md-10 fr-col-lg-8">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button aria-controls="modal-lg" title="Fermer" type="button" class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h2 id="modal-lg-title" class="fr-modal__title">
              Contenu volumineux
            </h2>
            <p>Cette modale affiche un contenu nécessitant plus d'espace.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Usage** : Contenu large (tableaux, formulaires complexes).

### 7. Modale avec formulaire

```html
<dialog id="modal-form" class="fr-modal" aria-labelledby="modal-form-title" aria-modal="true">
  <div class="fr-container fr-container--fluid fr-container-md">
    <div class="fr-grid-row fr-grid-row--center">
      <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
        <div class="fr-modal__body">
          <div class="fr-modal__header">
            <button aria-controls="modal-form" title="Fermer" type="button" class="fr-btn--close fr-btn">
              Fermer
            </button>
          </div>
          <div class="fr-modal__content">
            <h2 id="modal-form-title" class="fr-modal__title">
              Ajouter un commentaire
            </h2>
            <form id="comment-form">
              <div class="fr-input-group">
                <label class="fr-label" for="comment-text">Votre commentaire</label>
                <textarea class="fr-input" id="comment-text" name="comment-text" rows="4" required></textarea>
              </div>
            </form>
          </div>
          <div class="fr-modal__footer">
            <ul class="fr-btns-group fr-btns-group--right fr-btns-group--inline-reverse fr-btns-group--inline-lg">
              <li>
                <button type="submit" form="comment-form" class="fr-btn">
                  Envoyer
                </button>
              </li>
              <li>
                <button type="button" class="fr-btn fr-btn--secondary" aria-controls="modal-form">
                  Annuler
                </button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</dialog>
```

**Usage** : Saisie d'informations dans une modale.

## Dépendances CSS et JavaScript

### CSS

**Ordre de chargement obligatoire** :

```html
<!-- 1. CORE (requis) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/core/core.min.css" />

<!-- 2. UTILITY (recommandé) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/utility/utility.min.css" />

<!-- 3. SCHEME (requis pour le mode sombre) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/scheme/scheme.min.css" />

<!-- 4. BUTTON (requis) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/button/button.min.css" />

<!-- 5. MODAL (requis) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/modal/modal.min.css" />
```

### JavaScript (OBLIGATOIRE)

**Le composant modale nécessite JavaScript** pour fonctionner :

```html
<!-- À la fin du <body>, avant </body> -->

<!-- Module JS DSFR -->
<script type="module"
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/core/core.module.min.js">
</script>
<script type="module"
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/modal/modal.module.min.js">
</script>

<!-- Fallback nomodule (IE11) -->
<script type="text/javascript" nomodule
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/legacy/legacy.nomodule.min.js">
</script>
<script type="text/javascript" nomodule
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/core/core.nomodule.min.js">
</script>
<script type="text/javascript" nomodule
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/modal/modal.nomodule.min.js">
</script>
```

**Alternative** : Charger le JS global du DSFR :

```html
<script type="module"
        src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/dsfr.module.min.js">
</script>
```

## JavaScript - API

### Initialisation automatique

Le JS DSFR initialise automatiquement les modales. Aucune configuration manuelle requise.

**Instances créées** :
- `fr-modal` : instance de la modale
- Bouton d'ouverture (via `aria-controls`)

**Attributs ajoutés automatiquement** :
- `data-fr-js-modal="true"` sur `<dialog>`
- `data-fr-js-modal-button="true"` sur le bouton

### API JavaScript

Accès à l'API via `window.dsfr(element)` :

```javascript
const modalElement = document.getElementById('modal-id');
const modalInstance = dsfr(modalElement).modal;
```

#### Propriétés et méthodes

**`modal.disclose()`** : Ouvrir la modale

```javascript
const modalElement = document.getElementById('modal-action');
dsfr(modalElement).modal.disclose();
```

**`modal.conceal()`** : Fermer la modale

```javascript
const modalElement = document.getElementById('modal-action');
dsfr(modalElement).modal.conceal();
```

**`modal.isDisclosed`** : Vérifier si la modale est ouverte

```javascript
const modalElement = document.getElementById('modal-action');
if (dsfr(modalElement).modal.isDisclosed) {
  console.log('La modale est ouverte');
}
```

**`modal.isEnabled`** : Activer/désactiver le fonctionnement de la modale

```javascript
const modalElement = document.getElementById('modal-action');
dsfr(modalElement).modal.isEnabled = false; // Désactiver
dsfr(modalElement).modal.isEnabled = true;  // Activer
```

**`modal.node`** : Accéder au nœud DOM

```javascript
const modalElement = document.getElementById('modal-action');
const domNode = dsfr(modalElement).modal.node;
console.log(domNode); // <dialog id="modal-action">...</dialog>
```

**`modalButton.focus()`** : Replacer le focus sur le bouton

```javascript
const buttonElement = document.querySelector('[aria-controls="modal-action"]');
dsfr(buttonElement).modalButton.focus();
```

**`modalButton.parent`** : Accéder à l'instance de la modale parente

```javascript
const buttonElement = document.querySelector('[aria-controls="modal-action"]');
const parentModal = dsfr(buttonElement).modalButton.parent;
```

### Événements personnalisés

Le DSFR émet des événements lors des actions sur la modale :

| Événement | Action | Élément | Attribut |
|-----------|--------|---------|----------|
| `dsfr.disclose` | Ouverture de la modale | `<dialog>` | `data-fr-js-modal` |
| `dsfr.conceal` | Fermeture de la modale | `<dialog>` | `data-fr-js-modal` |
| `dsfr.click` | Clic sur le bouton d'ouverture | `<button>` | `data-fr-js-modal-button` |

**Écouter les événements** :

```javascript
const modalElement = document.getElementById('modal-action');

// Événement d'ouverture
modalElement.addEventListener('dsfr.disclose', function(e) {
  console.log('Modale ouverte', e.target);
});

// Événement de fermeture
modalElement.addEventListener('dsfr.conceal', function(e) {
  console.log('Modale fermée', e.target);
});
```

### Exemples d'utilisation avancée

#### Ouvrir une modale programmatiquement

```javascript
// Ouvrir une modale au chargement de la page
window.addEventListener('DOMContentLoaded', function() {
  const modalElement = document.getElementById('modal-welcome');
  dsfr(modalElement).modal.disclose();
});
```

#### Confirmation avant fermeture

```javascript
const modalElement = document.getElementById('modal-form');

modalElement.addEventListener('dsfr.conceal', function(e) {
  const form = this.querySelector('form');

  if (form && form.querySelector('input, textarea').value) {
    const confirmClose = confirm('Des données non enregistrées seront perdues. Continuer ?');

    if (!confirmClose) {
      e.preventDefault(); // Empêcher la fermeture
      dsfr(modalElement).modal.disclose(); // Réouvrir
    }
  }
});
```

#### Charger du contenu dynamique

```javascript
async function openModalWithContent(modalId, contentUrl) {
  const modalElement = document.getElementById(modalId);
  const contentContainer = modalElement.querySelector('.fr-modal__content');

  try {
    const response = await fetch(contentUrl);
    const html = await response.text();

    contentContainer.innerHTML = html;
    dsfr(modalElement).modal.disclose();

  } catch (error) {
    console.error('Erreur lors du chargement du contenu', error);
  }
}

// Usage
openModalWithContent('modal-dynamic', '/api/content/123');
```

## Accessibilité

### Attributs ARIA obligatoires

| Élément | Attribut | Valeur | Justification |
|---------|----------|--------|---------------|
| `<dialog>` | `id` | Identifiant unique | Lié au bouton via `aria-controls` |
| `<dialog>` | `aria-labelledby` | ID du titre | Lie la modale à son titre |
| `<dialog>` | `aria-modal` | `"true"` | Indique que c'est une modale |
| Bouton ouverture | `aria-controls` | ID de la modale | Lie le bouton à la modale |
| Bouton ouverture | `data-fr-opened` | `"true"` / `"false"` | État de la modale |
| Bouton fermeture | `aria-controls` | ID de la modale | Lie le bouton à la modale |
| Icône (si présente) | `aria-hidden` | `"true"` | Masque l'icône décorative |

### Conformité RGAA 4.1

Le composant Modale DSFR est **100% conforme RGAA 4.1** :

- ✅ Critère 7.1 : Contrôle au clavier complet (Tab, Esc)
- ✅ Critère 7.3 : Focus piégé dans la modale (pas de sortie involontaire)
- ✅ Critère 10.7 : Navigation au clavier fluide
- ✅ Critère 12.7 : Titre de la modale identifiable (`aria-labelledby`)
- ✅ Critère 13.1 : Information accessible (titre explicite)

### Gestion du focus

**Séquence du focus** :
1. **Ouverture** : Le focus est automatiquement placé sur le premier élément focusable (bouton de fermeture)
2. **Navigation** : Le focus est piégé dans la modale (ne peut pas sortir)
3. **Fermeture** : Le focus retourne sur le bouton d'ouverture

### Navigation au clavier

| Touche | Action |
|--------|--------|
| `Tab` | Naviguer entre les éléments focusables de la modale |
| `Shift + Tab` | Navigation arrière |
| `Esc` | Fermer la modale |
| `Enter` / `Space` | Activer un bouton |

### Lecteurs d'écran

- Le titre de la modale est annoncé à l'ouverture
- Le rôle "modal" est identifié
- Les boutons d'action sont annoncés clairement
- La fermeture au clic sur le fond est annoncée (si activée)

### Bonnes pratiques

1. **Titre explicite** : Le titre doit clairement décrire le contenu/action
2. **Focus initial** : Laisser le focus sur le bouton de fermeture (par défaut)
3. **Contenu concis** : Éviter les modales trop longues
4. **Actions claires** : Boutons explicites ("Confirmer", "Annuler", pas juste "OK")
5. **Éviter les modales multiples** : Ne pas ouvrir une modale depuis une autre modale
6. **Retour du focus** : S'assurer que le focus retourne au bon endroit après fermeture

## Tokens de couleurs

### Fond de la modale

```scss
// Fond semi-transparent (backdrop)
$background-overlap-grey: rgba(0, 0, 0, 0.5) (light/dark)

// Arrière-plan du corps de la modale
$background-default-grey: #ffffff (light) / #1e1e1e (dark)
```

### Titre et contenu

```scss
// Titre
$text-title-grey: #161616 (light) / #f6f6f6 (dark)

// Contenu
$text-default-grey: #3a3a3a (light) / #cecece (dark)
```

### Bouton de fermeture

```scss
// Icône du bouton
$text-action-high-grey: #161616 (light) / #f6f6f6 (dark)

// Survol
$background-action-low-grey--hover: #eeeeee (light) / #2a2a2a (dark)
```

## Espacement

Le composant respecte le **système de grille 8 points** :

```scss
// Padding du corps de la modale
.fr-modal__body {
  padding: 6v;  // 24px / 1.5rem
}

// Espacement de l'entête
.fr-modal__header {
  margin-bottom: 4v;  // 16px / 1rem
}

// Espacement du titre
.fr-modal__title {
  margin-bottom: 4v;  // 16px / 1rem
}

// Espacement du pied de page
.fr-modal__footer {
  margin-top: 6v;  // 24px / 1.5rem
}
```

## Règles strictes

### ✅ OBLIGATOIRE

1. **JavaScript obligatoire** : Le composant ne fonctionne pas sans JS
2. **Entête obligatoire** : `fr-modal__header` avec bouton de fermeture
3. **Titre obligatoire** : `fr-modal__title` avec `id` pour `aria-labelledby`
4. **Bouton type** : `type="button"` sur tous les boutons
5. **Attribut `aria-controls`** : Sur boutons d'ouverture et de fermeture
6. **Attribut `aria-modal="true"`** : Sur la modale
7. **Attribut `data-fr-opened`** : Sur le bouton d'ouverture
8. **Placement `<dialog>`** : Recommandé comme enfant direct de `<body>`

### ❌ INTERDIT

1. **Omission de l'entête** : Le bouton de fermeture est obligatoire
2. **Omission du titre** : La modale doit avoir un titre identifiable
3. **Modale imbriquée** : Ne pas ouvrir une modale depuis une autre modale
4. **Styles inline** : Pas de `style=""` sur les éléments
5. **Contenu non-sémantique** : Toujours utiliser des balises appropriées
6. **Fermeture sans action** : Si action critique, désactiver `data-fr-concealing-backdrop`
7. **Focus non-géré** : Ne pas manipuler le focus manuellement (le JS le gère)

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
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/button/button.min.css" />
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/modal/modal.min.css" />
</head>
<body>

  <div class="fr-container fr-my-6w">
    <h1 class="fr-h2">Gestion des projets</h1>

    <!-- Bouton d'ouverture de la modale -->
    <button data-fr-opened="false"
            aria-controls="modal-delete-project"
            type="button"
            class="fr-btn fr-btn--secondary">
      Supprimer le projet
    </button>
  </div>

  <!-- Modale de confirmation de suppression -->
  <dialog id="modal-delete-project"
          class="fr-modal"
          aria-labelledby="modal-delete-title"
          aria-modal="true">
    <div class="fr-container fr-container--fluid fr-container-md">
      <div class="fr-grid-row fr-grid-row--center">
        <div class="fr-col-12 fr-col-md-8 fr-col-lg-6">
          <div class="fr-modal__body">

            <!-- Entête avec bouton de fermeture -->
            <div class="fr-modal__header">
              <button aria-controls="modal-delete-project"
                      title="Fermer"
                      type="button"
                      class="fr-btn--close fr-btn">
                Fermer
              </button>
            </div>

            <!-- Contenu -->
            <div class="fr-modal__content">
              <h2 id="modal-delete-title" class="fr-modal__title">
                <span class="fr-icon-warning-line fr-icon--lg" aria-hidden="true"></span>
                Confirmer la suppression du projet
              </h2>
              <p>
                Êtes-vous sûr de vouloir supprimer le projet
                <strong>"Modernisation SI"</strong> ?
              </p>
              <p>
                Cette action est <strong>irréversible</strong> et supprimera
                toutes les données associées (tâches, documents, historique).
              </p>
            </div>

            <!-- Zone d'action -->
            <div class="fr-modal__footer">
              <ul class="fr-btns-group fr-btns-group--right fr-btns-group--inline-reverse fr-btns-group--inline-lg">
                <li>
                  <button type="button"
                          class="fr-btn"
                          onclick="deleteProject('PROJ-123')">
                    Confirmer la suppression
                  </button>
                </li>
                <li>
                  <button type="button"
                          class="fr-btn fr-btn--secondary"
                          aria-controls="modal-delete-project">
                    Annuler
                  </button>
                </li>
              </ul>
            </div>

          </div>
        </div>
      </div>
    </div>
  </dialog>

  <!-- Scripts DSFR (à la fin du body) -->
  <script type="module"
          src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/core/core.module.min.js">
  </script>
  <script type="module"
          src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/modal/modal.module.min.js">
  </script>

  <!-- JavaScript de gestion de la suppression -->
  <script>
    async function deleteProject(projectId) {
      const modalElement = document.getElementById('modal-delete-project');

      try {
        // Appel API pour supprimer le projet
        const response = await fetch(`/api/projects/${projectId}`, {
          method: 'DELETE'
        });

        if (!response.ok) {
          throw new Error('Erreur lors de la suppression');
        }

        // Fermer la modale
        dsfr(modalElement).modal.conceal();

        // Afficher une notification de succès (composant Notice)
        showSuccessNotification('Le projet a été supprimé avec succès');

        // Rediriger après 2 secondes
        setTimeout(() => {
          window.location.href = '/projets';
        }, 2000);

      } catch (error) {
        console.error('Erreur de suppression:', error);
        alert('Une erreur est survenue lors de la suppression du projet.');
      }
    }

    // Écouter l'événement d'ouverture pour des actions personnalisées
    document.getElementById('modal-delete-project').addEventListener('dsfr.disclose', function() {
      console.log('Modale de suppression ouverte');
    });
  </script>

</body>
</html>
```

## Ressources

- **Documentation officielle DSFR** : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/modale
- **RGAA 4.1** : https://www.numerique.gouv.fr/publications/rgaa-accessibilite/
- **Storybook DSFR Modal** : https://storybook.systeme-de-design.gouv.fr/?path=/docs/composants-modal
- **WAI-ARIA Dialog Pattern** : https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/
- **MDN `<dialog>`** : https://developer.mozilla.org/fr/docs/Web/HTML/Element/dialog

## Notes de version

**Version DSFR 1.14** :
- Structure de la modale stabilisée
- Support complet du mode sombre
- API JavaScript complète avec événements
- Gestion automatique du focus
- Conformité RGAA 4.1 à 100%
- Support du backdrop non-fermable

**Compatibilité navigateurs** :
- Chrome/Edge 90+
- Firefox 88+
- Safari 15+ (support natif `<dialog>`)
- Support IE11 via polyfill (bundle `nomodule`)

## Différences avec Alert

| Aspect | Modal (Modale) | Alert (Alerte) |
|--------|----------------|----------------|
| **Position** | Overlay plein écran | Dans le contenu |
| **Focus** | Piégé dans la modale | Pas de piège de focus |
| **Fermeture** | Bouton + Esc + backdrop | Généralement non-fermable |
| **JavaScript** | Obligatoire | Non obligatoire |
| **Usage** | Action utilisateur requise | Information contextuelle |
| **Blocage** | Bloque l'interaction | N'empêche pas l'interaction |
