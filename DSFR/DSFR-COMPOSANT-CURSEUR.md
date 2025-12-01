# Curseur (Range)

Le curseur est un élément d'interaction avec l'interface permettant à l'usager de délimiter manuellement une sélection par rapport à une valeur minimale et maximale.

## Vue d'ensemble

Le composant Curseur permet à l'utilisateur de sélectionner une valeur dans une plage définie, avec affichage en temps réel de l'impact des options choisies pour éclairer la prise de décision.

## Quand utiliser ce composant ?

Utiliser un curseur lorsque la valeur saisie est imprécise ou à déterminer, par exemple, la luminosité d'un écran. Il sert à montrer en temps réel l'impact des options choisies et à éclairer la prise de décision.

### ℹ️ Information

Préférer un champ de saisie ou une liste déroulante lorsque la valeur à renseigner est précise, comme une année de naissance par exemple, ou que le nombre de valeurs spécifiques parmi lesquelles choisir est important.

Le curseur n'a pas vocation à communiquer un état d'avancement quelconque. Pour ce type d'usage, utiliser l'**indicateur d'étapes**.

## Comment utiliser ce composant ?

- Éviter d'intégrer un curseur au sein d'un formulaire, sauf cas exceptionnel.
- Lier l'usage du curseur à une actualisation du résultat en temps réel, en fonction de la valeur sélectionnée. Par exemple, en tant que filtre déterminant l'affichage de donnée dans une liste ou un tableau.
- Considérer que la valeur du curseur est toujours en nombre. Des unités peuvent ensuite y être ajoutées (k€, €, kg, etc).

### Proposer une fourchette de valeurs en nombre

**✅ À FAIRE** : Proposer une fourchette de valeurs exclusivement en nombre.

**❌ À NE PAS FAIRE** : Ne pas proposer des valeurs littérales et approximatives.

### Proposer des échelles de valeur adaptées

**✅ À FAIRE** : Proposer des échelles de valeur adaptées, ni trop petites ni trop larges.

**❌ À NE PAS FAIRE (échelle trop petite)** : Ne pas proposer une échelle de valeur non-adaptée, ici trop petite. Utiliser des cases à cocher ou des boutons radios en cas d'échelle de valeur trop petite.

**❌ À NE PAS FAIRE (échelle trop grande)** : Ne pas proposer une échelle de valeur non-adaptée, ici trop grande.

### Tenir compte de l'espace disponible

**✅ À FAIRE** : Utiliser le curseur lorsque vous avez l'espace de le faire, notamment lorsque l'échelle de valeur est large. Si l'espace est limité, un champ de saisie est certainement un meilleur choix.

Utiliser un champ de saisie est certainement un meilleur choix lorsque l'échelle de valeur est large et l'espace limité.

---

## Structure du composant

Le composant Curseur permet à l'utilisateur de sélectionner une valeur dans une plage définie. Sa structure est la suivante :

### Éléments constitutifs

| Élément | Balise HTML | Classe CSS | Obligatoire | Description |
|---------|-------------|------------|-------------|-------------|
| Conteneur global | `<div>` | `fr-range-group` | ✅ Oui | Conteneur principal du composant |
| Libellé | `<label>` | `fr-label` | ✅ Oui | Son attribut `id` doit être associé à l'attribut `aria-labelledby` du curseur |
| Description additionnelle | `<span>` | `fr-hint-text` | Non | Texte d'aide dans le libellé |
| Conteneur curseur | `<div>` | `fr-range` | ✅ Oui | Contient l'élément curseur |
| Valeur courante | `<span>` | `fr-range__output` | ✅ Oui | Affiche la valeur actuelle |
| Curseur | `<input type="range">` | `fr-range__input` | ✅ Oui | L'élément interactif |
| Valeur minimale affichée | `<span>` | `fr-range__min` | Non | Avec `aria-hidden="true"` |
| Valeur maximale affichée | `<span>` | `fr-range__max` | Non | Avec `aria-hidden="true"` |
| Messages | `<div>` | `fr-messages-group` | Non | Son `id` doit être associé à `aria-describedby` du curseur. Utiliser `aria-live="polite"` pour les mises à jour dynamiques |

### Attributs de l'élément `<input type="range">`

| Attribut | Description |
|----------|-------------|
| `value` | Valeur par défaut du curseur |
| `min` | Valeur minimale autorisée |
| `max` | Valeur maximale autorisée |
| `step` | Pas du curseur (incrément) |
| `aria-labelledby` | Référence l'`id` du label |
| `aria-describedby` | Référence l'`id` du bloc messages |

---

## Exemple de structure HTML

```html
<div class="fr-range-group">
    <label id="range-label" class="fr-label">
        Libellé
        <span class="fr-hint-text">Texte de description additionnel, valeur de 0 à 100.</span>
    </label>
    <div class="fr-range">
        <span class="fr-range__output">50</span>
        <input name="range" type="range" aria-labelledby="range-label" max="100" value="50" aria-describedby="range-messages">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
    <div class="fr-messages-group" id="range-messages" aria-live="polite">
    </div>
</div>
```

---

## CSS

### Installation du CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

Il est possible d'importer les fichiers CSS avec un niveau de granularité adapté à vos besoins. Voir le découpage des fichiers CSS du DSFR dans la documentation dédiée.

### Dépendances CSS

| Dépendance | Obligatoire |
|------------|-------------|
| Core | ✅ Oui |
| Range | ✅ Oui |

### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/range/range.min.css" rel="stylesheet">
```

---

## Variantes

### Variante de taille

Le curseur est disponible en deux variantes de tailles pour s'adapter à différents contextes d'utilisation. Pour appliquer une variante de taille, ajoutez une des classes suivantes à l'élément `<div class="fr-range">` :

| Taille | Classe | Description |
|--------|--------|-------------|
| MD | (par défaut) | Taille standard |
| SM | `fr-range--sm` | Taille réduite |

#### Exemple de variante de taille SM

```html
<div class="fr-range-group">
    <label id="range-sm-label" class="fr-label">Libellé</label>
    <div class="fr-range fr-range--sm">
        <span class="fr-range__output">50</span>
        <input name="range-sm" type="range" aria-labelledby="range-sm-label" max="100" value="50">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
</div>
```

### Variante de curseur cranté

Le curseur peut afficher des crans avec l'utilisation de la classe `fr-range--step`.

#### Exemple de curseur cranté

```html
<div class="fr-range-group">
    <label id="range-step-label" class="fr-label">Libellé</label>
    <div class="fr-range fr-range--step">
        <span class="fr-range__output">50</span>
        <input name="range-step" type="range" aria-labelledby="range-step-label" max="100" value="50" step="10">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
</div>
```

### Variante avec préfixe et suffixe

Le curseur peut afficher des préfixe et suffixe autour des valeurs courante, minimale et maximale avec l'utilisation des attributs `data-fr-prefix` et `data-fr-suffix` sur l'élément `<div class="fr-range">`.

#### Exemple de curseur avec préfixe et suffixe

```html
<div class="fr-range-group">
    <label id="range-prefix-suffix-label" class="fr-label">Libellé</label>
    <div class="fr-range" data-fr-prefix="~" data-fr-suffix="%">
        <span class="fr-range__output">50</span>
        <input name="range-prefix" type="range" aria-labelledby="range-prefix-suffix-label" max="100" value="50">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
</div>
```

### Variantes d'états

Les états d'erreur/succès/désactivé sont gérés au niveau du groupe. Pour ajouter un état à un curseur, ajoutez une des classes suivantes :

| État | Classe | Description |
|------|--------|-------------|
| Erreur | `fr-range-group--error` | Indique une erreur |
| Succès | `fr-range-group--valid` | Indique un succès |
| Désactivé | `fr-range-group--disabled` | État désactivé (+ attribut `disabled` sur `<input>`) |

Un message d'erreur ou de succès doit être ajouté dans un bloc `fr-messages-group` à la fin du groupe du curseur et doit être lié au curseur via un attribut `aria-describedby`.

#### Exemple de curseur avec erreur

```html
<div class="fr-range-group fr-range-group--error">
    <label id="range-error-label" class="fr-label">
        Libellé
        <span class="fr-hint-text">Texte de description additionnel, valeur de 0 à 100.</span>
    </label>
    <div class="fr-range">
        <span class="fr-range__output">50</span>
        <input id="range-error" name="range-error" type="range" aria-labelledby="range-error-label" max="100" value="50" aria-describedby="range-error-messages">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
    <div class="fr-messages-group" id="range-error-messages" aria-live="polite">
        <p class="fr-message fr-message--error" id="range-error-message-error">Valeur sélectionnée impossible</p>
    </div>
</div>
```

#### Exemple de curseur avec succès

```html
<div class="fr-range-group fr-range-group--valid">
    <label id="range-valid-label" class="fr-label">
        Libellé
        <span class="fr-hint-text">Texte de description additionnel, valeur de 0 à 100.</span>
    </label>
    <div class="fr-range">
        <span class="fr-range__output">50</span>
        <input name="range-valid" type="range" aria-labelledby="range-valid-label" max="100" value="50" aria-describedby="range-valid-messages">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
    <div class="fr-messages-group" id="range-valid-messages" aria-live="polite">
        <p class="fr-message fr-message--valid" id="range-valid-message-valid">Texte de validation</p>
    </div>
</div>
```

#### Exemple de curseur désactivé

```html
<div class="fr-range-group fr-range-group--disabled">
    <label id="range-disabled-label" class="fr-label">
        Libellé
        <span class="fr-hint-text">Texte de description additionnel, valeur de 0 à 100.</span>
    </label>
    <div class="fr-range">
        <span class="fr-range__output">20</span>
        <input name="range-disabled" type="range" aria-labelledby="range-disabled-label" max="100" value="20" disabled aria-describedby="range-disabled-messages">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
    <div class="fr-messages-group" id="range-disabled-messages" aria-live="polite">
    </div>
</div>
```

### Variante de curseur double

Le curseur double permet de disposer de deux poignées de sélection pour les valeurs minimale et maximale par l'ajout d'un second élément HTML `<input>` de type range.

#### Exemple de curseur double

```html
<div class="fr-range-group">
    <label id="range-double-label" class="fr-label">
        Libellé
        <span class="fr-hint-text">Texte de description additionnel, valeur de 0 à 100.</span>
    </label>
    <div class="fr-range fr-range--double">
        <span class="fr-range__output">25</span>
        <input name="range-double" type="range" aria-labelledby="range-double-label" max="100" value="25" aria-describedby="range-double-messages">
        <input name="range-double-2" type="range" aria-labelledby="range-double-label" max="100" value="75" aria-describedby="range-double-messages">
        <span class="fr-range__min" aria-hidden="true">0</span>
        <span class="fr-range__max" aria-hidden="true">100</span>
    </div>
    <div class="fr-messages-group" id="range-double-messages" aria-live="polite">
    </div>
</div>
```

---

## JavaScript

### Installation du JavaScript

Pour fonctionner, le composant curseur nécessite l'utilisation de JavaScript. Chaque composant utilisant JavaScript possède un fichier JS spécifique et requiert le fichier JS du core.

Il est donc nécessaire d'importer ces fichiers à la fin de la page (avant `</body>`) :

```html
<script type="module" src="dist/core/core.module.min.js"></script>
<script type="module" src="dist/component/range/range.module.min.js"></script>
```

**NB:** Il est aussi possible d'importer le JS global du DSFR `dsfr.module.min.js`

### Support Internet Explorer 11 (legacy)

Pour fonctionner sur Internet Explorer 11, un fichier legacy, en version nomodule ES5, peut aussi être importé :

```html
<script type="text/javascript" nomodule src="dist/legacy/legacy.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/core/core.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/component/range/range.nomodule.min.js"></script>
```

Une fois le JavaScript chargé, le composant fonctionne automatiquement.

### Instances

Sur le curseur, les éléments suivants sont instanciés :

| Élément | Sélecteur |
|---------|-----------|
| Le conteneur | Classe `fr-range` |
| Le ou les curseurs | Classe `fr-range` + éléments `<input type="range">` |
| La valeur courante | Classe `fr-range__output` |
| Les valeurs min/max | Classes `fr-range__min` et `fr-range__max` |

Une fois chargé, le JS ajoute un attribut `data-fr-js-NOM_INSTANCE="true"` sur chacun des éléments instanciés.

### API JavaScript

Il est possible d'interagir avec les instances du composant en JavaScript via une API.

Cette API est disponible depuis la méthode `window.dsfr(instance)` du core.

#### Exemple d'utilisation

```javascript
const elem = document.getElementById('ID_RANGE');
dsfr(elem).range.isEnabled;
```

### Propriétés et méthodes disponibles

#### range

| Propriété | Type | Description | Retour | Exemple |
|-----------|------|-------------|--------|---------|
| `isEnabled` | property | Définit si le fonctionnement du curseur est activé ou non | Boolean | `dsfr(elem).range.isEnabled = false` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).range.node` |

#### rangeInput

| Propriété | Type | Description | Retour | Exemple |
|-----------|------|-------------|--------|---------|
| `value` | property | Retourne la valeur courante du curseur | Number | `dsfr(elem).rangeInput.value` |
| `isEnabled` | property | Définit si le fonctionnement du curseur est activé ou non | Boolean | `dsfr(elem).rangeInput.isEnabled = false` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).rangeInput.node` |

#### rangeOutput

| Propriété | Type | Description | Retour | Exemple |
|-----------|------|-------------|--------|---------|
| `isEnabled` | property | Définit si le fonctionnement du curseur est activé ou non | Boolean | `dsfr(elem).rangeOutput.isEnabled = false` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).rangeOutput.node` |

#### rangeLimit

| Propriété | Type | Description | Retour | Exemple |
|-----------|------|-------------|--------|---------|
| `isEnabled` | property | Définit si le fonctionnement du curseur est activé ou non | Boolean | `dsfr(elem).rangeLimit.isEnabled = false` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).rangeLimit.node` |

---

## Récapitulatif des classes CSS

| Classe | Description |
|--------|-------------|
| `fr-range-group` | Conteneur global du composant |
| `fr-range` | Conteneur du curseur |
| `fr-range__input` | Élément input du curseur |
| `fr-range__output` | Affichage de la valeur courante |
| `fr-range__min` | Affichage de la valeur minimale |
| `fr-range__max` | Affichage de la valeur maximale |
| `fr-range--sm` | Variante de taille réduite |
| `fr-range--step` | Variante avec crans |
| `fr-range--double` | Variante avec deux poignées |
| `fr-range-group--error` | État d'erreur |
| `fr-range-group--valid` | État de succès |
| `fr-range-group--disabled` | État désactivé |

---

## Règles éditoriales

Le curseur n'est régi par aucune règle éditoriale spécifique.

---

## Références

- **Documentation DSFR** : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/curseur
- **GitHub** : https://github.com/GouvernementFR/dsfr
