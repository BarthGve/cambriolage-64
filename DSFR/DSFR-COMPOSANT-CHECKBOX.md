# Composant Case à cocher (Checkbox) - DSFR

## Quand utiliser ce composant ?

Utiliser les cases à cocher pour permettre à l'utilisateur de **sélectionner une ou plusieurs options dans une liste**.

### ℹ️ Information importante

Bien différencier les cases à cocher des boutons radio ou liste déroulante :

- **Cases à cocher** : sélection multiple (de 0 à N éléments) ou choix binaire (sélectionner/désélectionner une seule option)
- **Boutons radio** : contraindre le choix à une seule option
- **Liste déroulante** : au-delà de 5 choix ou lorsque l'espace est restreint

---

## HTML - Structure du composant

### Checkbox simple

Le composant Case à cocher, ci-après nommée Checkbox, est un élément interactif permettant de sélectionner une ou plusieurs options. Sa structure est la suivante :

1. La checkbox doit être contenu dans un élément HTML `<div>` défini par la classe **`fr-checkbox-group`**
2. La checkbox est un élément HTML `<input>` de type `checkbox` défini par la classe **`fr-checkbox`**
3. La checkbox doit être associée à un label `<label>` avec la classe **`fr-label`**
4. Une description additionnelle de l'option _(optionnelle)_ peut être ajoutée dans le label, elle est définie par un élément `<span>` et la classe utilitaire **`fr-hint-text`**
5. Un message d'erreur ou de succès peut être associé à la checkbox en utilisant un élément `<div>` avec la classe **`fr-messages-group`** dans lequel on peut ajouter un message `fr-message`. Son attribut `id` doit être associé à l'attribut `aria-describedby` de la checkbox. Ce bloc peut être placé vide et être rempli dynamiquement, auquel cas il doit être annoncé à l'utilisateur en utilisant l'attribut `aria-live="polite"`

#### Exemple de structure HTML simple

```html
<div class="fr-checkbox-group">
    <input id="checkbox" type="checkbox" aria-describedby="checkbox-messages">
    <label class="fr-label" for="checkbox">
        Libellé checkbox
        <span class="fr-hint-text">Description optionnelle</span>
    </label>
    <div class="fr-messages-group" id="checkbox-messages" aria-live="polite">
    </div>
</div>
```

---

### Groupe de checkboxes

Pour regrouper plusieurs checkboxes liées, utilisez un élément `<fieldset>` avec une légende `<legend>`. Cela permet de structurer les options de manière accessible.

1. L'élément `<fieldset>` est défini par la classe **`fr-fieldset`**
2. La légende `<legend>` est définie par la classe **`fr-fieldset__legend`**. Par défaut une légende sera en gras car le fieldset est utilisé pour regroupé plusieurs champs ayant chacun un label. Dans le cas des checkboxes la légende est visuellement perçue comme le label du groupe de checkboxes. On ajoutera donc la classe **`fr-fieldset__legend--regular`** pour repasser la légende sur une graisse standard
3. Une description additionnelle pour la légende _(optionnelle)_ peut être ajoutée dans la légende, elle est définie par un élément `<span>` et la classe utilitaire **`fr-hint-text`**
4. Chaque élément de checkbox est contenu dans un élément `<div>` défini par la classe **`fr-fieldset__element`**. Ces éléments peuvent être placés en ligne avec la classe **`fr-fieldset__element--inline`**
5. Comme pour chaque checkbox, le groupe de checkbox, représenté par un fieldset, peut contenir un message d'erreur/information/succès via un bloc `fr-messages-group`

#### Exemple de groupe de checkboxes

```html
<fieldset class="fr-fieldset" aria-labelledby="checkboxes-legend checkboxes-messages">
    <legend class="fr-fieldset__legend--regular fr-fieldset__legend" id="checkboxes-legend">
        Légende pour l'ensemble des éléments
    </legend>
    <div class="fr-fieldset__element">
        <div class="fr-checkbox-group">
            <input name="checkboxes-1" id="checkboxes-1" type="checkbox">
            <label class="fr-label" for="checkboxes-1">
                Libellé case à cocher
            </label>
        </div>
    </div>
    <div class="fr-fieldset__element">
        <div class="fr-checkbox-group">
            <input checked name="checkboxes-2" id="checkboxes-2" type="checkbox">
            <label class="fr-label" for="checkboxes-2">
                Libellé case à cocher
            </label>
        </div>
    </div>
    <div class="fr-fieldset__element">
        <div class="fr-checkbox-group">
            <input name="checkboxes-3" id="checkboxes-3" type="checkbox">
            <label class="fr-label" for="checkboxes-3">
                Libellé case à cocher
            </label>
        </div>
    </div>
    <div class="fr-messages-group" id="checkboxes-messages" aria-live="polite">
    </div>
</fieldset>
```

---

## CSS - Installation et variantes

### Installation du CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

#### Dépendances CSS

| Dépendance | Obligatoire |
|------------|-------------|
| Core       | Oui         |
| Form       | Oui         |
| Checkbox   | Oui         |

#### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/form/form.min.css" rel="stylesheet">
<link href="dist/component/checkbox/checkbox.min.css" rel="stylesheet">
```

**Ou avec CDN :**

```html
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/core/core.min.css" rel="stylesheet">
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/component/form/form.min.css" rel="stylesheet">
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/component/checkbox/checkbox.min.css" rel="stylesheet">
```

---

### Variantes de tailles

La checkbox est disponible en deux variantes de tailles :

- **En taille MD** : par défaut
- **En taille SM** : définie par la classe **`fr-checkbox-group--sm`**

#### Exemple de checkbox en taille SM

```html
<div class="fr-checkbox-group fr-checkbox-group--sm">
    <input id="checkbox-sm" type="checkbox">
    <label class="fr-label" for="checkbox-sm">
        Libellé checkbox taille SM
    </label>
</div>
```

---

### Variantes d'états

La checkbox est disponible en plusieurs variantes d'états :

#### États pour une checkbox individuelle

- **Checkbox avec erreur** : définie par la classe **`fr-checkbox-group--error`**
- **Checkbox avec succès** : définie par la classe **`fr-checkbox-group--valid`**
- **Checkbox désactivée** : définie par l'attribut **`disabled`** sur l'élément `<input>`

#### Exemples d'états individuels

**Checkbox avec erreur :**

```html
<div class="fr-checkbox-group fr-checkbox-group--error">
    <input id="checkbox-error" type="checkbox" aria-describedby="checkbox-messages-error">
    <label class="fr-label" for="checkbox-error">
        Libellé checkbox avec erreur
    </label>
    <div class="fr-messages-group" id="checkbox-messages-error" aria-live="polite">
        <p class="fr-message fr-message--error">Texte d'erreur</p>
    </div>
</div>
```

**Checkbox avec succès :**

```html
<div class="fr-checkbox-group fr-checkbox-group--valid">
    <input id="checkbox-valid" type="checkbox" aria-describedby="checkbox-messages-valid">
    <label class="fr-label" for="checkbox-valid">
        Libellé checkbox avec succès
    </label>
    <div class="fr-messages-group" id="checkbox-messages-valid" aria-live="polite">
        <p class="fr-message fr-message--valid">Texte de succès</p>
    </div>
</div>
```

**Checkbox désactivée :**

```html
<div class="fr-checkbox-group">
    <input id="checkbox-disabled" type="checkbox" disabled>
    <label class="fr-label" for="checkbox-disabled">
        Libellé checkbox désactivée
    </label>
</div>
```

---

#### États pour un groupe de checkboxes

Dans le cas d'utilisation d'un groupe de checkboxes, ces états sont définis sur le groupe (le fieldset), et non sur chaque checkbox.

- **Groupe en erreur** : définie par la classe **`fr-fieldset--error`**
- **Groupe en succès** : définie par la classe **`fr-fieldset--valid`**
- **Groupe désactivé** : définie par l'attribut **`disabled`**

#### Exemple de groupe avec état d'erreur

```html
<fieldset class="fr-fieldset fr-fieldset--error" aria-labelledby="checkboxes-legend checkboxes-messages">
    <legend class="fr-fieldset__legend--regular fr-fieldset__legend" id="checkboxes-legend">
        Légende pour l'ensemble des éléments en erreur
    </legend>
    <div class="fr-fieldset__element">
        <div class="fr-checkbox-group">
            <input name="checkboxes-error-1" id="checkboxes-error-1" type="checkbox">
            <label class="fr-label" for="checkboxes-error-1">
                Libellé case à cocher
            </label>
        </div>
    </div>
    <div class="fr-fieldset__element">
        <div class="fr-checkbox-group">
            <input name="checkboxes-error-2" id="checkboxes-error-2" type="checkbox">
            <label class="fr-label" for="checkboxes-error-2">
                Libellé case à cocher
            </label>
        </div>
    </div>
    <div class="fr-messages-group" id="checkboxes-messages" aria-live="polite">
        <p class="fr-message fr-message--error">Texte d'erreur pour le groupe</p>
    </div>
</fieldset>
```

#### Exemple de groupe désactivé

```html
<fieldset class="fr-fieldset" disabled aria-labelledby="checkboxes-legend checkboxes-messages">
    <legend class="fr-fieldset__legend--regular fr-fieldset__legend" id="checkboxes-legend">
        Légende pour l'ensemble des éléments désactivés
    </legend>
    <div class="fr-fieldset__element">
        <div class="fr-checkbox-group">
            <input name="checkboxes-disabled-1" id="checkboxes-disabled-1" type="checkbox">
            <label class="fr-label" for="checkboxes-disabled-1">
                Libellé case à cocher
            </label>
        </div>
    </div>
    <div class="fr-fieldset__element">
        <div class="fr-checkbox-group">
            <input name="checkboxes-disabled-2" id="checkboxes-disabled-2" type="checkbox">
            <label class="fr-label" for="checkboxes-disabled-2">
                Libellé case à cocher
            </label>
        </div>
    </div>
    <div class="fr-messages-group" id="checkboxes-messages" aria-live="polite">
    </div>
</fieldset>
```

---

## JavaScript

Le composant Case à cocher **ne nécessite pas l'utilisation de JavaScript** pour son fonctionnement de base.

Un script est disponible pour faire remonter les évènements de changement d'état des checkboxes, mais il n'est pas nécessaire pour le fonctionnement du composant. Ce script est notamment utilisé pour gérer la sélection des lignes d'un tableau.

---

## Comment utiliser ce composant ?

### ✅ À FAIRE

- Utiliser la case à cocher au sein d'un formulaire
- Privilégier une **disposition en liste verticale** des cases à cocher lorsqu'elles sont en liste, la version horizontale étant plus difficile à lire pour les utilisateurs, notamment lorsque les options sont nombreuses
- Accompagner les cases à cocher d'un **texte d'aide** pour clarifier la nature du contenu attendu

### ❌ À NE PAS FAIRE

- Ne pas masquer le texte d'aide dans une infobulle

---

## Règles éditoriales

- Il est important de rédiger des **libellés clairs et concis** pour faciliter la compréhension des options et du choix à réaliser
- Maintenir une **cohérence dans les libellés** des boutons radio en utilisant des termes logiques entre eux et cohérents avec le reste du site
- Conserver une **unité dans le format d'écriture** de tous les libellés de case à cocher, en mettant uniquement la première lettre en majuscule et sans ponctuer la fin d'un libellé
- Accompagner la ou les cases à cocher d'un **texte d'aide pour clarifier** la nature du contenu attendu, lorsque nécessaire. Si cette information est essentielle, éviter de la masquer dans une infobulle

---

## Récapitulatif des classes DSFR

### Classes principales

| Classe | Élément | Description |
|--------|---------|-------------|
| `fr-checkbox-group` | `<div>` | Conteneur de la checkbox |
| `fr-checkbox-group--sm` | `<div>` | Variante petite taille |
| `fr-checkbox-group--error` | `<div>` | État d'erreur |
| `fr-checkbox-group--valid` | `<div>` | État de succès |
| `fr-label` | `<label>` | Label de la checkbox |
| `fr-hint-text` | `<span>` | Description additionnelle |
| `fr-messages-group` | `<div>` | Conteneur de messages |
| `fr-message` | `<p>` | Message d'information |
| `fr-message--error` | `<p>` | Message d'erreur |
| `fr-message--valid` | `<p>` | Message de succès |

### Classes pour les groupes

| Classe | Élément | Description |
|--------|---------|-------------|
| `fr-fieldset` | `<fieldset>` | Groupe de checkboxes |
| `fr-fieldset--error` | `<fieldset>` | Groupe en erreur |
| `fr-fieldset--valid` | `<fieldset>` | Groupe en succès |
| `fr-fieldset__legend` | `<legend>` | Légende du groupe |
| `fr-fieldset__legend--regular` | `<legend>` | Légende en graisse normale |
| `fr-fieldset__element` | `<div>` | Conteneur d'un élément du groupe |
| `fr-fieldset__element--inline` | `<div>` | Élément affiché en ligne |

---

## Attributs ARIA importants

| Attribut | Élément | Obligatoire | Description |
|----------|---------|-------------|-------------|
| `aria-describedby` | `<input>` | Recommandé | Référence l'ID du bloc de messages |
| `aria-live="polite"` | `<div>` messages | Recommandé | Annonce les changements de messages |
| `aria-labelledby` | `<fieldset>` | Recommandé | Référence l'ID de la légende et des messages |
| `for` | `<label>` | Obligatoire | Référence l'ID de l'input associé |
| `id` | `<input>`, `<legend>`, `<div>` | Obligatoire | Identifiant unique pour les associations |

---

**Date de création** : 2025-01-20
**Source** : [Système de Design de l'État (DSFR)](https://www.systeme-de-design.gouv.fr/)
