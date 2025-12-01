# DSFR - Composant Formulaire (Form)

## Vue d'ensemble

Le composant Formulaire (Form) du DSFR fournit une structure standardisée pour organiser des ensembles de champs de formulaire, gérer les erreurs, les messages d'aide et les validations. Il repose sur l'élément HTML `<fieldset>` pour regrouper logiquement les champs.

**Version DSFR**: 1.14
**Composant**: Form
**Fichier CSS**: `@gouvfr/dsfr/dist/component/form/form.min.css`

## Caractéristiques

- **Usage** : Collecte d'informations utilisateur
- **Structure** : Basée sur `<fieldset>` et `<legend>`
- **Validation** : États d'erreur, succès, avertissement, information
- **Accessibilité** : RGAA 4.1 conforme (labels, messages, ARIA)
- **Responsive** : Disposition adaptative (inline desktop, stacked mobile)

## Structure HTML complète

### 1. Structure de base

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset" aria-labelledby="fieldset-legend fieldset-messages">
    <legend class="fr-fieldset__legend" id="fieldset-legend">
      Légende pour l'ensemble des éléments
      <span class="fr-hint-text">Texte de description additionnel</span>
    </legend>

    <!-- Champ 1 -->
    <div class="fr-fieldset__element">
      <div class="fr-input-group">
        <label class="fr-label" for="text-1">
          Libellé champ de saisie
        </label>
        <input class="fr-input" name="text-1" id="text-1" type="text">
      </div>
    </div>

    <!-- Champ 2 -->
    <div class="fr-fieldset__element">
      <div class="fr-input-group">
        <label class="fr-label" for="text-2">
          Libellé champ de saisie
        </label>
        <input class="fr-input" name="text-2" id="text-2" type="text">
      </div>
    </div>

    <!-- Messages du groupe -->
    <div class="fr-messages-group" id="fieldset-messages" aria-live="polite">
    </div>
  </fieldset>

  <button class="fr-btn" type="submit">
    Enregistrer les informations
  </button>
</form>
```

**Éléments obligatoires** :
- `<form>` : conteneur du formulaire
- `<fieldset>` : groupe de champs
- `<legend>` : légende du groupe (obligatoire)
- `fr-fieldset__element` : conteneur de chaque champ
- `fr-messages-group` : zone de messages

### 2. Anatomie détaillée

#### Le conteneur `<form>`

```html
<form action="/submit" method="post" id="my-form">
  <!-- Contenu -->
</form>
```

**Attributs obligatoires** :
- `action` : URL de soumission
- `method` : `"post"` (recommandé) ou `"get"`

**Attributs optionnels** :
- `id` : identifiant unique
- `novalidate` : désactive la validation HTML5 native
- `enctype="multipart/form-data"` : pour upload de fichiers
- `autocomplete="on"` : autocomplétion (activée par défaut)

#### Le groupe de champs `<fieldset>`

```html
<fieldset class="fr-fieldset" aria-labelledby="legend-id messages-id">
  <!-- Contenu -->
</fieldset>
```

**Attributs obligatoires** :
- `class="fr-fieldset"` : classe de style
- `aria-labelledby` : référence la légende ET les messages

**États possibles** :
- `fr-fieldset--error` : état d'erreur
- `fr-fieldset--success` : état de succès
- `fr-fieldset--valid` : état valide (optionnel)
- `disabled` : désactivé (attribut HTML natif)

#### La légende `<legend>`

```html
<legend class="fr-fieldset__legend" id="legend-id">
  Titre du groupe de champs
  <span class="fr-hint-text">Description optionnelle</span>
</legend>
```

**Caractéristiques** :
- **OBLIGATOIRE** dans chaque `<fieldset>`
- Doit avoir un `id` pour `aria-labelledby`
- Peut contenir un `fr-hint-text` pour précisions

#### Les éléments de champ `fr-fieldset__element`

```html
<div class="fr-fieldset__element">
  <div class="fr-input-group">
    <label class="fr-label" for="input-id">Libellé</label>
    <input class="fr-input" id="input-id" name="input-name" type="text">
  </div>
</div>
```

**Rôle** : Conteneur de mise en page pour chaque champ.

**Classes de disposition** :
- `fr-fieldset__element` : disposition par défaut (pleine largeur)
- `fr-fieldset__element--inline` : disposition en ligne (toujours)
- `fr-fieldset__element--inline@md` : disposition en ligne desktop uniquement (≥ 768px)

**Classes de taille** :
- `fr-fieldset__element--inline-grow` : s'adapte à la largeur restante
- `fr-fieldset__element--postal` : taille code postal (240px)
- `fr-fieldset__element--number` : taille numéro/jour/mois (80px)
- `fr-fieldset__element--year` : taille année (112px)

#### Le groupe de messages `fr-messages-group`

```html
<div class="fr-messages-group" id="messages-id" aria-live="polite">
  <p class="fr-message fr-message--error">Texte d'erreur</p>
  <p class="fr-message fr-message--info">Texte d'information</p>
</div>
```

**Attributs obligatoires** :
- `id` : pour `aria-labelledby` du fieldset
- `aria-live="polite"` : annonce les messages aux lecteurs d'écran

**Types de messages** :
- `fr-message--error` : erreur (rouge)
- `fr-message--success` : succès (vert)
- `fr-message--warning` : avertissement (orange)
- `fr-message--info` : information (bleu)

## Classes CSS DSFR

### Classes principales

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-fieldset` | `<fieldset>` | Groupe de champs |
| `fr-fieldset__legend` | `<legend>` | Légende du groupe (obligatoire) |
| `fr-fieldset__element` | `<div>` | Conteneur de chaque champ |
| `fr-messages-group` | `<div>` | Zone de messages du groupe |
| `fr-message` | `<p>` | Message individuel |

### États du fieldset

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-fieldset--error` | `<fieldset>` | Groupe en erreur (bordure rouge) |
| `fr-fieldset--success` | `<fieldset>` | Groupe validé (bordure verte) |
| `fr-fieldset--valid` | `<fieldset>` | Groupe valide (optionnel) |
| `disabled` | `<fieldset>` | Groupe désactivé (attribut HTML) |

### Disposition des éléments

| Classe | Usage | Description |
|--------|-------|-------------|
| `fr-fieldset__element--inline` | `<div>` | Disposition en ligne (toujours) |
| `fr-fieldset__element--inline@md` | `<div>` | Disposition en ligne desktop uniquement |
| `fr-fieldset__element--inline-grow` | `<div>` | S'adapte à la largeur restante |

### Tailles prédéfinies

| Classe | Usage | Largeur | Cas d'usage |
|--------|-------|---------|-------------|
| `fr-fieldset__element--number` | `<div>` | 80px | Numéro de rue, jour, mois |
| `fr-fieldset__element--year` | `<div>` | 112px | Année (4 chiffres) |
| `fr-fieldset__element--postal` | `<div>` | 240px | Code postal |

### Types de messages

| Classe | Usage | Couleur | Icône |
|--------|-------|---------|-------|
| `fr-message--error` | `<p>` | Rouge | Erreur |
| `fr-message--success` | `<p>` | Vert | Succès |
| `fr-message--warning` | `<p>` | Orange | Avertissement |
| `fr-message--info` | `<p>` | Bleu | Information |

## Variantes

### 1. Formulaire simple (sans erreur)

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset" aria-labelledby="identity-legend identity-messages">
    <legend class="fr-fieldset__legend" id="identity-legend">
      Identité
      <span class="fr-hint-text">Informations personnelles</span>
    </legend>

    <div class="fr-fieldset__element">
      <div class="fr-input-group">
        <label class="fr-label" for="firstname">Prénom</label>
        <input class="fr-input" id="firstname" name="firstname" type="text" required>
      </div>
    </div>

    <div class="fr-fieldset__element">
      <div class="fr-input-group">
        <label class="fr-label" for="lastname">Nom</label>
        <input class="fr-input" id="lastname" name="lastname" type="text" required>
      </div>
    </div>

    <div class="fr-messages-group" id="identity-messages" aria-live="polite">
    </div>
  </fieldset>

  <button class="fr-btn" type="submit">Enregistrer</button>
</form>
```

### 2. Formulaire en erreur

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset fr-fieldset--error" aria-labelledby="identity-legend identity-messages">
    <legend class="fr-fieldset__legend" id="identity-legend">
      Identité
    </legend>

    <div class="fr-fieldset__element">
      <div class="fr-input-group fr-input-group--error">
        <label class="fr-label" for="firstname">Prénom</label>
        <input class="fr-input" id="firstname" name="firstname" type="text" aria-describedby="firstname-error">
        <div class="fr-messages-group" id="firstname-error" aria-live="polite">
          <p class="fr-message fr-message--error">Ce champ est obligatoire</p>
        </div>
      </div>
    </div>

    <div class="fr-fieldset__element">
      <div class="fr-input-group">
        <label class="fr-label" for="lastname">Nom</label>
        <input class="fr-input" id="lastname" name="lastname" type="text">
      </div>
    </div>

    <div class="fr-messages-group" id="identity-messages" aria-live="polite">
      <p class="fr-message fr-message--error">Veuillez corriger les erreurs ci-dessus</p>
    </div>
  </fieldset>

  <button class="fr-btn" type="submit">Enregistrer</button>
</form>
```

### 3. Formulaire avec champs en ligne

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset" aria-labelledby="address-legend address-messages">
    <legend class="fr-fieldset__legend" id="address-legend">
      Adresse postale
    </legend>

    <!-- Numéro de rue (80px) + Nom de rue (reste) -->
    <div class="fr-fieldset__element fr-fieldset__element--number">
      <div class="fr-input-group">
        <label class="fr-label" for="street-number">N°</label>
        <input class="fr-input" id="street-number" name="street-number" type="text">
      </div>
    </div>
    <div class="fr-fieldset__element fr-fieldset__element--inline fr-fieldset__element--inline-grow">
      <div class="fr-input-group">
        <label class="fr-label" for="street-name">Nom de la rue</label>
        <input class="fr-input" id="street-name" name="street-name" type="text">
      </div>
    </div>

    <!-- Code postal (240px) + Ville (inline desktop uniquement) -->
    <div class="fr-fieldset__element fr-fieldset__element--postal">
      <div class="fr-input-group">
        <label class="fr-label" for="postal-code">Code postal</label>
        <input class="fr-input" id="postal-code" name="postal-code" type="text" maxlength="5">
      </div>
    </div>
    <div class="fr-fieldset__element fr-fieldset__element--inline@md">
      <div class="fr-input-group">
        <label class="fr-label" for="city">Ville</label>
        <input class="fr-input" id="city" name="city" type="text">
      </div>
    </div>

    <div class="fr-messages-group" id="address-messages" aria-live="polite">
    </div>
  </fieldset>

  <button class="fr-btn" type="submit">Enregistrer</button>
</form>
```

### 4. Formulaire avec date de naissance

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset" aria-labelledby="birthdate-legend birthdate-messages">
    <legend class="fr-fieldset__legend" id="birthdate-legend">
      Date de naissance
    </legend>

    <!-- Jour (80px) -->
    <div class="fr-fieldset__element fr-fieldset__element--inline fr-fieldset__element--number">
      <div class="fr-input-group">
        <label class="fr-label" for="birth-day">Jour</label>
        <input class="fr-input" id="birth-day" name="birth-day" type="text" maxlength="2" placeholder="JJ">
      </div>
    </div>

    <!-- Mois (80px) -->
    <div class="fr-fieldset__element fr-fieldset__element--inline fr-fieldset__element--number">
      <div class="fr-input-group">
        <label class="fr-label" for="birth-month">Mois</label>
        <input class="fr-input" id="birth-month" name="birth-month" type="text" maxlength="2" placeholder="MM">
      </div>
    </div>

    <!-- Année (112px) -->
    <div class="fr-fieldset__element fr-fieldset__element--inline fr-fieldset__element--year">
      <div class="fr-input-group">
        <label class="fr-label" for="birth-year">Année</label>
        <input class="fr-input" id="birth-year" name="birth-year" type="text" maxlength="4" placeholder="AAAA">
      </div>
    </div>

    <div class="fr-messages-group" id="birthdate-messages" aria-live="polite">
    </div>
  </fieldset>

  <button class="fr-btn" type="submit">Enregistrer</button>
</form>
```

### 5. Formulaire avec succès

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset fr-fieldset--success" aria-labelledby="contact-legend contact-messages">
    <legend class="fr-fieldset__legend" id="contact-legend">
      Coordonnées
    </legend>

    <div class="fr-fieldset__element">
      <div class="fr-input-group fr-input-group--valid">
        <label class="fr-label" for="email">Email</label>
        <input class="fr-input" id="email" name="email" type="email" value="john.doe@example.com">
      </div>
    </div>

    <div class="fr-fieldset__element">
      <div class="fr-input-group fr-input-group--valid">
        <label class="fr-label" for="phone">Téléphone</label>
        <input class="fr-input" id="phone" name="phone" type="tel" value="0612345678">
      </div>
    </div>

    <div class="fr-messages-group" id="contact-messages" aria-live="polite">
      <p class="fr-message fr-message--success">Les coordonnées ont été vérifiées avec succès</p>
    </div>
  </fieldset>

  <button class="fr-btn" type="submit">Enregistrer</button>
</form>
```

### 6. Formulaire désactivé

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset" disabled aria-labelledby="disabled-legend disabled-messages">
    <legend class="fr-fieldset__legend" id="disabled-legend">
      Informations verrouillées
      <span class="fr-hint-text">Ces informations ne peuvent pas être modifiées</span>
    </legend>

    <div class="fr-fieldset__element">
      <div class="fr-input-group">
        <label class="fr-label" for="locked-field">Champ verrouillé</label>
        <input class="fr-input" id="locked-field" name="locked-field" type="text" value="Valeur verrouillée">
      </div>
    </div>

    <div class="fr-messages-group" id="disabled-messages" aria-live="polite">
      <p class="fr-message fr-message--info">Ces champs sont en lecture seule</p>
    </div>
  </fieldset>
</form>
```

### 7. Formulaire avec types de champs variés

```html
<form action="/submit" method="post">
  <fieldset class="fr-fieldset" aria-labelledby="profile-legend profile-messages">
    <legend class="fr-fieldset__legend" id="profile-legend">
      Profil utilisateur
    </legend>

    <!-- Champ texte -->
    <div class="fr-fieldset__element">
      <div class="fr-input-group">
        <label class="fr-label" for="username">Nom d'utilisateur</label>
        <input class="fr-input" id="username" name="username" type="text" required>
      </div>
    </div>

    <!-- Liste déroulante -->
    <div class="fr-fieldset__element">
      <div class="fr-select-group">
        <label class="fr-label" for="grade">Grade</label>
        <select class="fr-select" id="grade" name="grade">
          <option value="" selected disabled hidden>Sélectionner un grade</option>
          <option value="colonel">Colonel</option>
          <option value="lieutenant-colonel">Lieutenant-colonel</option>
          <option value="commandant">Commandant</option>
        </select>
      </div>
    </div>

    <!-- Cases à cocher -->
    <div class="fr-fieldset__element">
      <fieldset class="fr-fieldset" aria-labelledby="permissions-legend">
        <legend class="fr-fieldset__legend" id="permissions-legend">
          Permissions
        </legend>
        <div class="fr-checkbox-group">
          <input type="checkbox" id="perm-read" name="permissions" value="read">
          <label class="fr-label" for="perm-read">Lecture</label>
        </div>
        <div class="fr-checkbox-group">
          <input type="checkbox" id="perm-write" name="permissions" value="write">
          <label class="fr-label" for="perm-write">Écriture</label>
        </div>
      </fieldset>
    </div>

    <div class="fr-messages-group" id="profile-messages" aria-live="polite">
    </div>
  </fieldset>

  <button class="fr-btn" type="submit">Enregistrer</button>
</form>
```

## Dépendances CSS

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

<!-- 4. FORM (requis - composant) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/form/form.min.css" />

<!-- 5. Composants de champs (selon besoins) -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/input/input.min.css" />
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/select/select.min.css" />
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/checkbox/checkbox.min.css" />
<!-- etc. -->
```

**Tableau des dépendances** :

| Dépendance | Obligatoire | Remarque |
|------------|-------------|----------|
| Core | ✅ Oui | Styles de base DSFR |
| Form | ✅ Oui | Styles du fieldset et messages |
| Input | ⚠️ Conditionnel | Si champs texte/email/tel |
| Select | ⚠️ Conditionnel | Si listes déroulantes |
| Checkbox | ⚠️ Conditionnel | Si cases à cocher |
| Radio | ⚠️ Conditionnel | Si boutons radio |
| Upload | ⚠️ Conditionnel | Si upload de fichiers |

## JavaScript

### Fonctionnement de base

**Les formulaires DSFR ne nécessitent PAS de JavaScript** pour leur fonctionnement de base. La validation HTML5 native et la soumission de formulaire fonctionnent sans JavaScript.

### Validation côté client (recommandé)

Pour améliorer l'UX, ajouter une validation JavaScript :

```javascript
// Validation de formulaire basique
document.getElementById('my-form').addEventListener('submit', function(e) {
  e.preventDefault(); // Empêcher la soumission par défaut

  const form = e.target;
  const fieldset = form.querySelector('.fr-fieldset');
  const messagesContainer = form.querySelector('.fr-messages-group');

  // Réinitialiser les états
  fieldset.classList.remove('fr-fieldset--error', 'fr-fieldset--success');
  messagesContainer.innerHTML = '';

  // Validation basique
  const requiredFields = form.querySelectorAll('[required]');
  let hasErrors = false;

  requiredFields.forEach(field => {
    if (!field.value.trim()) {
      hasErrors = true;

      // Marquer le champ en erreur
      const inputGroup = field.closest('.fr-input-group');
      if (inputGroup) {
        inputGroup.classList.add('fr-input-group--error');
      }
    }
  });

  if (hasErrors) {
    fieldset.classList.add('fr-fieldset--error');
    messagesContainer.innerHTML = `
      <p class="fr-message fr-message--error">
        Veuillez remplir tous les champs obligatoires
      </p>
    `;
    return;
  }

  // Validation réussie
  fieldset.classList.add('fr-fieldset--success');
  messagesContainer.innerHTML = `
    <p class="fr-message fr-message--success">
      Le formulaire a été validé avec succès
    </p>
  `;

  // Soumettre le formulaire
  form.submit();
});
```

### Validation en temps réel (champ par champ)

```javascript
// Validation en temps réel sur perte de focus
document.querySelectorAll('.fr-input[required]').forEach(input => {
  input.addEventListener('blur', function() {
    const inputGroup = this.closest('.fr-input-group');
    const messagesContainer = inputGroup.querySelector('.fr-messages-group') ||
      createMessagesContainer(inputGroup);

    // Réinitialiser
    inputGroup.classList.remove('fr-input-group--error', 'fr-input-group--valid');
    messagesContainer.innerHTML = '';

    // Valider
    if (!this.value.trim()) {
      inputGroup.classList.add('fr-input-group--error');
      messagesContainer.innerHTML = `
        <p class="fr-message fr-message--error">Ce champ est obligatoire</p>
      `;
    } else {
      inputGroup.classList.add('fr-input-group--valid');
      messagesContainer.innerHTML = `
        <p class="fr-message fr-message--success">Valide</p>
      `;
    }
  });
});

function createMessagesContainer(inputGroup) {
  const container = document.createElement('div');
  container.className = 'fr-messages-group';
  container.setAttribute('aria-live', 'polite');
  inputGroup.appendChild(container);
  return container;
}
```

### Validation avec bibliothèques tierces

#### Exemple avec Constraint Validation API (natif)

```javascript
// Utiliser l'API de validation native du navigateur
document.getElementById('my-form').addEventListener('submit', function(e) {
  e.preventDefault();

  const form = e.target;
  const fieldset = form.querySelector('.fr-fieldset');
  const messagesContainer = form.querySelector('.fr-messages-group');

  // Vérifier la validité native
  if (!form.checkValidity()) {
    fieldset.classList.add('fr-fieldset--error');

    // Afficher les erreurs natives
    const invalidFields = form.querySelectorAll(':invalid');
    const errorMessages = Array.from(invalidFields).map(field => {
      return `<li>${field.labels[0]?.textContent || 'Champ'}: ${field.validationMessage}</li>`;
    }).join('');

    messagesContainer.innerHTML = `
      <p class="fr-message fr-message--error">
        Veuillez corriger les erreurs suivantes :
      </p>
      <ul>${errorMessages}</ul>
    `;
    return;
  }

  // Succès
  fieldset.classList.add('fr-fieldset--success');
  messagesContainer.innerHTML = `
    <p class="fr-message fr-message--success">Formulaire validé</p>
  `;

  form.submit();
});
```

### Soumission AJAX

```javascript
// Soumission asynchrone avec fetch
document.getElementById('my-form').addEventListener('submit', async function(e) {
  e.preventDefault();

  const form = e.target;
  const fieldset = form.querySelector('.fr-fieldset');
  const messagesContainer = form.querySelector('.fr-messages-group');
  const submitBtn = form.querySelector('button[type="submit"]');

  // Désactiver le bouton pendant la soumission
  submitBtn.disabled = true;
  submitBtn.textContent = 'Envoi en cours...';

  // Réinitialiser les messages
  fieldset.classList.remove('fr-fieldset--error', 'fr-fieldset--success');
  messagesContainer.innerHTML = '';

  try {
    const formData = new FormData(form);
    const response = await fetch(form.action, {
      method: form.method,
      body: formData
    });

    if (!response.ok) {
      throw new Error('Erreur serveur');
    }

    const data = await response.json();

    // Succès
    fieldset.classList.add('fr-fieldset--success');
    messagesContainer.innerHTML = `
      <p class="fr-message fr-message--success">${data.message || 'Formulaire soumis avec succès'}</p>
    `;

    // Réinitialiser le formulaire
    form.reset();

  } catch (error) {
    // Erreur
    fieldset.classList.add('fr-fieldset--error');
    messagesContainer.innerHTML = `
      <p class="fr-message fr-message--error">
        Une erreur est survenue : ${error.message}
      </p>
    `;
  } finally {
    // Réactiver le bouton
    submitBtn.disabled = false;
    submitBtn.textContent = 'Enregistrer les informations';
  }
});
```

## Accessibilité

### Attributs ARIA obligatoires

| Élément | Attribut | Valeur | Justification |
|---------|----------|--------|---------------|
| `<fieldset>` | `aria-labelledby` | IDs de la légende + messages | Lie le groupe à sa légende et ses messages |
| `<legend>` | `id` | Identifiant unique | Référencé par `aria-labelledby` |
| `<label>` | `for` | ID de l'input | Lie le label au champ |
| `<input>` | `id` | Identifiant unique | Lié au `for` du label |
| `<div>` (messages) | `aria-live` | `"polite"` | Annonce les messages dynamiques |

### Conformité RGAA 4.1

Le composant Formulaire DSFR est **100% conforme RGAA 4.1** :

- ✅ Critère 11.1 : Chaque champ a un label associé
- ✅ Critère 11.2 : Labels pertinents et explicites
- ✅ Critère 11.5 : Regroupement de champs avec `<fieldset>` et `<legend>`
- ✅ Critère 11.10 : Messages d'erreur liés aux champs
- ✅ Critère 11.11 : Contraste des messages (4.5:1 minimum)
- ✅ Critère 13.1 : Information accessible sans JavaScript

### Navigation au clavier

| Touche | Action |
|--------|--------|
| `Tab` | Naviguer entre les champs |
| `Shift + Tab` | Navigation arrière |
| `Enter` | Soumettre le formulaire (sur le bouton) |
| `Space` | Cocher une case / activer un bouton |

### Lecteurs d'écran

- La légende du fieldset est annoncée avant les champs
- Chaque label est annoncé avec son champ
- Les messages d'erreur sont annoncés automatiquement (`aria-live`)
- L'état du fieldset (erreur/succès) est identifiable
- Les champs requis sont identifiés (`required`)

### Bonnes pratiques

1. **Labels explicites** : Toujours fournir un label clair pour chaque champ
2. **Messages d'erreur clairs** : Indiquer précisément ce qui ne va pas
3. **Validation progressive** : Valider au fur et à mesure (blur) pour guider l'utilisateur
4. **Ordre logique** : Organiser les champs dans un ordre logique de complétion
5. **Autocomplete** : Utiliser `autocomplete` pour faciliter la saisie
6. **Type de champ approprié** : `type="email"`, `type="tel"`, etc.
7. **Required vs optionnel** : Indiquer clairement les champs obligatoires

## Tokens de couleurs

### État normal

```scss
// Bordure du fieldset
$border-default-grey: #dddddd (light) / #3a3a3a (dark)

// Légende
$text-title-grey: #161616 (light) / #f6f6f6 (dark)

// Texte explicatif (hint)
$text-mention-grey: #666666 (light) / #9c9c9c (dark)
```

### État erreur

```scss
// Bordure du fieldset
$border-plain-error: #ce0500 (light) / #ff5655 (dark)

// Message d'erreur
$text-default-error: #ce0500 (light) / #ff5655 (dark)

// Arrière-plan du message
$background-flat-error: #ffe9e9 (light) / #4a1313 (dark)
```

### État succès

```scss
// Bordure du fieldset
$border-plain-success: #18753c (light) / #27a658 (dark)

// Message de succès
$text-default-success: #18753c (light) / #27a658 (dark)

// Arrière-plan du message
$background-flat-success: #b8fec9 (light) / #0f3a1f (dark)
```

### Messages d'information et avertissement

```scss
// Information (bleu)
$text-default-info: #0063cb (light) / #518fff (dark)
$background-flat-info: #e8edff (light) / #1e2a3a (dark)

// Avertissement (orange)
$text-default-warning: #ff9940 (light) / #ffab5e (dark)
$background-flat-warning: #fff4e5 (light) / #4a3a13 (dark)
```

## Espacement

Le composant respecte le **système de grille 8 points** :

```scss
// Espacement vertical du fieldset
.fr-fieldset {
  margin-bottom: 8v;  // 32px / 2rem
  padding: 4v;        // 16px / 1rem (padding interne)
}

// Espacement de la légende
.fr-fieldset__legend {
  margin-bottom: 4v;  // 16px / 1rem
}

// Espacement entre les éléments de champ
.fr-fieldset__element {
  margin-bottom: 4v;  // 16px / 1rem
}

// Espacement des messages
.fr-messages-group {
  margin-top: 2v;     // 8px / 0.5rem
}

.fr-message {
  padding: 2v 3v;     // 8px 12px / 0.5rem 0.75rem
  margin-bottom: 1v;  // 4px / 0.25rem
}
```

## Règles strictes

### ✅ OBLIGATOIRE

1. **Légende obligatoire** : Chaque `<fieldset>` doit avoir une `<legend>`
2. **Attribut `aria-labelledby`** : Doit référencer la légende ET les messages
3. **Labels sur tous les champs** : Chaque input doit avoir un `<label>` associé
4. **Messages liés aux erreurs** : Messages d'erreur obligatoires si `fr-fieldset--error`
5. **Attribut `aria-live="polite"`** : Sur tous les `fr-messages-group`
6. **Type de bouton** : `type="submit"` sur le bouton de soumission
7. **Method du form** : Toujours spécifier `method="post"` ou `method="get"`

### ❌ INTERDIT

1. **Omission de la légende** : `<legend>` est obligatoire dans chaque `<fieldset>`
2. **Champs sans label** : Tous les champs doivent être labellisés
3. **Messages génériques** : "Erreur" ❌ → "Le champ Email est obligatoire" ✅
4. **Styles inline** : Pas de `style=""` sur les éléments
5. **Validation uniquement côté client** : Toujours valider côté serveur (sécurité)
6. **Fieldset en erreur sans message** : Si `fr-fieldset--error`, message obligatoire
7. **Mélanger inline et block** : Ne pas utiliser `--inline` avec tailles incompatibles

## Exemple complet (Projet Grist SP2C)

```html
<!DOCTYPE html>
<html lang="fr" data-fr-scheme="system">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Création de projet - Gestion de projet SP2C</title>

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
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/form/form.min.css" />
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/input/input.min.css" />
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/select/select.min.css" />
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@1.14/dist/component/button/button.min.css" />
</head>
<body>

  <div class="fr-container fr-my-6w">
    <h1 class="fr-h2">Création d'un nouveau projet</h1>

    <form id="project-form" action="/api/projects" method="post">

      <!-- Informations générales -->
      <fieldset class="fr-fieldset" aria-labelledby="general-legend general-messages">
        <legend class="fr-fieldset__legend" id="general-legend">
          Informations générales
          <span class="fr-hint-text">Informations de base du projet</span>
        </legend>

        <div class="fr-fieldset__element">
          <div class="fr-input-group">
            <label class="fr-label" for="project-name">
              Nom du projet
              <span class="fr-hint-text">Maximum 100 caractères</span>
            </label>
            <input class="fr-input" id="project-name" name="project-name" type="text" maxlength="100" required>
          </div>
        </div>

        <div class="fr-fieldset__element">
          <div class="fr-input-group">
            <label class="fr-label" for="project-description">Description</label>
            <textarea class="fr-input" id="project-description" name="project-description" rows="4" required></textarea>
          </div>
        </div>

        <div class="fr-fieldset__element">
          <div class="fr-select-group">
            <label class="fr-label" for="department">Département</label>
            <select class="fr-select" id="department" name="department" required>
              <option value="" selected disabled hidden>Sélectionner un département</option>
              <option value="DRGP">DRGP</option>
              <option value="DNUM">DNUM</option>
              <option value="SP2C">SP2C</option>
            </select>
          </div>
        </div>

        <div class="fr-messages-group" id="general-messages" aria-live="polite">
        </div>
      </fieldset>

      <!-- Période du projet -->
      <fieldset class="fr-fieldset" aria-labelledby="period-legend period-messages">
        <legend class="fr-fieldset__legend" id="period-legend">
          Période du projet
        </legend>

        <div class="fr-fieldset__element">
          <div class="fr-input-group">
            <label class="fr-label" for="start-date">Date de début</label>
            <input class="fr-input" id="start-date" name="start-date" type="date" required>
          </div>
        </div>

        <div class="fr-fieldset__element">
          <div class="fr-input-group">
            <label class="fr-label" for="end-date">Date de fin estimée</label>
            <input class="fr-input" id="end-date" name="end-date" type="date">
          </div>
        </div>

        <div class="fr-messages-group" id="period-messages" aria-live="polite">
        </div>
      </fieldset>

      <!-- Boutons d'action -->
      <div class="fr-btns-group fr-btns-group--inline-sm">
        <button type="submit" class="fr-btn">
          Créer le projet
        </button>
        <button type="reset" class="fr-btn fr-btn--secondary">
          Réinitialiser
        </button>
        <button type="button" class="fr-btn fr-btn--secondary" onclick="window.history.back()">
          Annuler
        </button>
      </div>
    </form>
  </div>

  <!-- JavaScript de validation -->
  <script>
    document.getElementById('project-form').addEventListener('submit', async function(e) {
      e.preventDefault();

      const form = e.target;
      const generalFieldset = form.querySelector('#general-legend').closest('.fr-fieldset');
      const generalMessages = document.getElementById('general-messages');
      const submitBtn = form.querySelector('button[type="submit"]');

      // Réinitialiser
      generalFieldset.classList.remove('fr-fieldset--error', 'fr-fieldset--success');
      generalMessages.innerHTML = '';
      submitBtn.disabled = true;
      submitBtn.textContent = 'Envoi en cours...';

      try {
        // Validation basique
        if (!form.checkValidity()) {
          throw new Error('Veuillez remplir tous les champs obligatoires');
        }

        // Soumission AJAX
        const formData = new FormData(form);
        const response = await fetch(form.action, {
          method: form.method,
          body: formData
        });

        if (!response.ok) {
          throw new Error('Erreur serveur');
        }

        const data = await response.json();

        // Succès
        generalFieldset.classList.add('fr-fieldset--success');
        generalMessages.innerHTML = `
          <p class="fr-message fr-message--success">
            Le projet "${data.projectName}" a été créé avec succès
          </p>
        `;

        // Rediriger après 2 secondes
        setTimeout(() => {
          window.location.href = '/projets/' + data.projectId;
        }, 2000);

      } catch (error) {
        // Erreur
        generalFieldset.classList.add('fr-fieldset--error');
        generalMessages.innerHTML = `
          <p class="fr-message fr-message--error">
            Une erreur est survenue : ${error.message}
          </p>
        `;
        submitBtn.disabled = false;
        submitBtn.textContent = 'Créer le projet';
      }
    });
  </script>

</body>
</html>
```

## Ressources

- **Documentation officielle DSFR** : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/formulaire
- **RGAA 4.1** : https://www.numerique.gouv.fr/publications/rgaa-accessibilite/
- **Storybook DSFR Form** : https://storybook.systeme-de-design.gouv.fr/?path=/docs/composants-form
- **MDN Forms** : https://developer.mozilla.org/fr/docs/Web/HTML/Element/form
- **Constraint Validation API** : https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation

## Notes de version

**Version DSFR 1.14** :
- Structure du formulaire stabilisée
- Support complet du mode sombre
- Classes de taille prédéfinies (postal, number, year)
- Disposition responsive (inline@md)
- Conformité RGAA 4.1 à 100%

**Compatibilité navigateurs** :
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Support IE11 via bundle `nomodule`

## Différences entre composants

| Aspect | Fieldset (Form) | Input (isolé) |
|--------|-----------------|---------------|
| **Usage** | Regrouper plusieurs champs | Champ unique |
| **Structure** | `<fieldset>` + `<legend>` | `<div>` + `<label>` + `<input>` |
| **Messages** | Groupe de messages | Messages individuels |
| **Validation** | Groupe entier | Champ individuel |
| **Largeur** | Gestion via `fr-fieldset__element` | Gestion via classes utilitaires |
