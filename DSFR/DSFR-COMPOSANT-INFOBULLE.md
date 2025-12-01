# Composant Infobulle (Tooltip) - DSFR

## Structure du composant

Il existe deux types d'Infobulles suivant son déclenchement.

### Déclenchement au survol

L'infobulle au survol se compose des éléments suivants :

**Une zone de déclenchement :**
- Doit être un élément focusable (`<a>`, `<input>`, `<select>`, `<textarea>`, etc) pour déclencher l'affichage du conteneur à la prise de focus.
- Elle est liée au conteneur via l'attribut `aria-describedby`, sa valeur doit correspondre à l'attribut `id` du conteneur.

**Un conteneur pour le texte de l'infobulle :**
- Représenté par un élément `<span>`.
- Doit avoir un attribut `id` obligatoire, pour être lié à la zone de déclenchement.
- Doit avoir un attribut `role="tooltip"`.
- Doit avoir les classes `fr-tooltip` et `fr-placement`.

#### Exemple de structure HTML (survol)

```html
<a class="fr-link" aria-describedby="tooltip-1" href="[à modifier]">
    Exemple
</a>
<span class="fr-tooltip fr-placement" id="tooltip-1" role="tooltip">
    Lorem [...] elit ut.
</span>
```

### Déclenchement au clic

L'infobulle au clic se compose des éléments suivants :

**Une zone de déclenchement :**
- La zone de déclenchement est une balise `<button type="button">`.
- Elle est liée au conteneur via l'attribut `aria-describedby`, sa valeur doit correspondre à l'attribut `id` du conteneur.
- Doit avoir les classes `fr-btn--tooltip fr-btn`.

**Un conteneur pour le texte de l'infobulle :**
- Représenté par un élément `<span>`.
- Doit avoir un attribut `id` obligatoire, pour être lié à la zone de déclenchement.
- Doit avoir un attribut `role="tooltip"`.
- Doit avoir les classes `fr-tooltip` et `fr-placement`.

#### Exemple de structure HTML (clic)

```html
<button class="fr-btn--tooltip fr-btn" type="button" aria-describedby="tooltip-2">
    Information contextuelle
</button>
<span class="fr-tooltip fr-placement" id="tooltip-2" role="tooltip">
    Lorem [...] elit ut.
</span>
```

## CSS

### Installation du CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

Il est possible d'importer les fichiers CSS avec un niveau de granularité adapté à vos besoins. Voir le découpage des fichiers CSS du DSFR dans la documentation dédiée.

### Dépendances CSS

| Dépendance | Obligatoire | Remarque |
|------------|-------------|----------|
| Core | Oui | |
| tooltip | Oui | |
| Button | Non | Pour la version avec ouverture au clic |
| Link | Non | Pour la version avec ouverture au survol |

### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/tooltip/tooltip.min.css" rel="stylesheet">
```

## JavaScript

L'infobulle est un composant qui nécessite l'importation de fichiers JavaScript spécifiques pour son fonctionnement de base.

### Installation du JavaScript

Chaque composant utilisant JavaScript possède un fichier JS spécifique et requiert le fichier JS du core.

Il est donc nécessaire d'importer ces fichiers à la fin de la page (avant `</body>`) :

```html
<script type="module" src="dist/core/core.module.min.js"></script>
<script type="module" src="dist/component/tooltip/tooltip.module.min.js"></script>
```

**NB:** Il est aussi possible d'importer le JS global du DSFR `dsfr.module.min.js`

Pour fonctionner sur Internet Explorer 11, un fichier legacy, en version nomodule ES5, peut aussi être importé :

```html
<script type="text/javascript" nomodule src="dist/legacy/legacy.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/core/core.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/component/tooltip/tooltip.nomodule.min.js"></script>
```

Une fois le JavaScript chargé, le composant fonctionne automatiquement.

### Instances

Sur le tooltip, les éléments suivants sont instanciés :

- Le conteneur, via la classe : `fr-tooltip`
- Le déclencheur, via l'attribut : `aria-describedby` lié à l'`id` du conteneur

Une fois chargé, le JS ajoute un attribut `data-fr-js-NOM_INSTANCE="true"` sur chacun des éléments instanciés.

## API

Il est possible d'interagir avec les instances du composant en JavaScript via une API.

Cette API est disponible depuis la méthode `window.dsfr(instance)` du core.

### Exemple d'utilisation

```javascript
const elem = document.getElementById('ID_TOOLTIP');
dsfr(elem).tooltip.show();
```

### API tooltip

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `parent` | property | Retourne l'instance du dsfr parente | object \| null | `dsfr(elem).parent` |
| `children` | property | Renvoie un tableau d'instances enfants | Array | `dsfr(elem).children` |
| `node` | property | Renvoie le nœud HTML de l'élément | DOMElement | `dsfr(elem).tooltip.node` |
| `isEnabled` | property | Défini si le fonctionnement de l'infobulle est activé ou non | Boolean | `dsfr(elem).tooltip.isEnabled = false` |
| `isShown` | property | Défini si l'infobulle est affichée ou non | Boolean | `dsfr(elem).tooltip.isShown = false` |
| `show` | function | Affiche l'infobulle | none | `dsfr(elem).tooltip.show()` |
| `hide` | function | Cache l'infobulle | none | `dsfr(elem).tooltip.hide()` |
| `mode` | property | Défini le mode de placement de l'infobulle | 'placement_auto' \| 'placement_manual' | `dsfr(elem).tooltip.mode = 'placement_manual'` |
| `align` | property | Défini l'alignement vertical de l'infobulle en mode='placement_manual' | 'align_start' \| 'align_center' \| 'align_end' | `dsfr(elem).tooltip.align = 'align_start'` |
| `place` | property | Définit le placement horizontal de l'infobulle par rapport au déclencheur en mode='placement_manual' | 'place_top' \| 'place_bottom' \| 'place_left' \| 'place_right' | `dsfr(elem).tooltip.place = 'place_top'` |

### API tooltipReferent

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `parent` | property | Retourne l'instance du dsfr parente | object \| null | `dsfr(elem).parent` |
| `children` | property | Renvoie un tableau d'instances enfants | Array | `dsfr(elem).children` |
| `node` | property | Renvoie le nœud HTML de l'élément | DOMElement | `dsfr(elem).tooltipReferent.node` |
| `isEnabled` | property | Défini si le fonctionnement du déclencheur est activé ou non | Boolean | `dsfr(elem).tooltipReferent.isEnabled = false` |

## Événements

Le Système de Design fournit des événements personnalisés pour les actions uniques de la part de certains composants réactifs listés sur la page de l'API Javascript.

Sur l'infobulle, les événements suivants sont disponibles :

| Événement | Action | Élément | Attribut |
|-----------|--------|---------|----------|
| `dsfr.show` | Affichage de l'infobulle | tooltip | `data-fr-js-tab-tooltip` |
| `dsfr.hide` | Masquage de l'infobulle | tooltip | `data-fr-js-tab-tooltip` |

### Exemple d'écoute d'événements

```javascript
const tooltip = document.getElementById('tooltip-1');
tooltip.addEventListener('dsfr.show', function() {
    console.log('Infobulle affichée');
});

tooltip.addEventListener('dsfr.hide', function() {
    console.log('Infobulle masquée');
});
```
