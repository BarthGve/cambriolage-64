# DSFR - Composant Accordéon

## Vue d'ensemble

L'accordéon est un élément d'interaction permettant à l'usager d'afficher ou de masquer une section de contenu dans une page. Il est particulièrement utile pour économiser de l'espace dans les pages au contenu dense.

## Quand utiliser ce composant ?

### ✅ À FAIRE

- Alléger des pages de contenus denses en permettant à l'utilisateur de consulter uniquement ce dont il a besoin
- Simplifier l'expérience de l'usager en le guidant dans des parcours complexes
- Adapter son utilisation au contexte (l'utilisateur n'a pas besoin de lire tous les contenus)
- Privilégier des interactions simples (bouton ou lien) au sein des accordéons
- Rédiger un titre d'en-tête clair, explicite et précis
- Soigner la mise en forme avec des types de contenu adaptés (texte, listes à puces)

### ❌ À NE PAS FAIRE

- Ne pas utiliser les accordéons au sein d'une modale
- Ne pas utiliser si l'utilisateur doit lire tous les contenus de la page
- Ne pas intégrer des composants trop complexes aux accordéons
- Ne pas utiliser pour des contenus très courts (privilégier liste ou paragraphe)

## Structure HTML

### Accordéon simple

```html
<section class="fr-accordion">
    <h3 class="fr-accordion__title">
        <button type="button" class="fr-accordion__btn" aria-expanded="false" aria-controls="accordion-1">
            Libellé accordéon
        </button>
    </h3>
    <div id="accordion-1" class="fr-collapse">
        <!-- Contenu de l'accordéon -->
        <p>Votre contenu ici...</p>
    </div>
</section>
```

### Éléments de structure

| Élément | Balise | Classe | Description |
|---------|--------|--------|-------------|
| Conteneur | `<section>` | `fr-accordion` | Conteneur principal de l'accordéon |
| Titre | `<h3>` | `fr-accordion__title` | Niveau de titre variable (h1-h6) selon hiérarchie |
| Bouton | `<button>` | `fr-accordion__btn` | Bouton d'ouverture/fermeture |
| Collapse | `<div>` | `fr-collapse` | Bloc refermable contenant le contenu |

### Attributs obligatoires

**Sur le bouton :**
- `type="button"` - Type de bouton
- `aria-expanded="[true|false]"` - État ouvert/fermé
- `aria-controls="ID_COLLAPSE"` - Lien vers le collapse

**Sur le collapse :**
- `id="ID_UNIQUE"` - Identifiant unique pour être lié au bouton

## Groupe d'accordéons

Pour regrouper plusieurs accordéons :

```html
<div class="fr-accordions-group" data-fr-group="true">
    <section class="fr-accordion">
        <h3 class="fr-accordion__title">
            <button type="button" class="fr-accordion__btn" aria-expanded="false" aria-controls="accordion-1">
                Premier accordéon
            </button>
        </h3>
        <div id="accordion-1" class="fr-collapse">
            <p>Contenu du premier accordéon</p>
        </div>
    </section>

    <section class="fr-accordion">
        <h3 class="fr-accordion__title">
            <button type="button" class="fr-accordion__btn" aria-expanded="false" aria-controls="accordion-2">
                Deuxième accordéon
            </button>
        </h3>
        <div id="accordion-2" class="fr-collapse">
            <p>Contenu du deuxième accordéon</p>
        </div>
    </section>
</div>
```

### Attribut data-fr-group

| Valeur | Comportement |
|--------|--------------|
| `true` | Les accordéons sont liés : ouvrir l'un ferme les autres |
| `false` | Les accordéons sont indépendants : plusieurs peuvent être ouverts |
| Non défini | Comportement par défaut : liés (`true`) |

## Installation CSS

### Dépendances CSS requises

| Dépendance | Obligatoire |
|------------|-------------|
| Core | ✅ Oui |
| Accordéon | ✅ Oui |

### Import CSS

```html
<head>
    <link href="dist/core/core.min.css" rel="stylesheet">
    <link href="dist/component/accordion/accordion.min.css" rel="stylesheet">
</head>
```

### Import via CDN

```html
<head>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/core/core.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/component/accordion/accordion.min.css">
</head>
```

## Installation JavaScript

### Fichiers JS requis

```html
<!-- Avant </body> -->
<script type="module" src="dist/core/core.module.min.js"></script>
<script type="module" src="dist/component/accordion/accordion.module.min.js"></script>
```

### Via CDN

```html
<script type="module" src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/core/core.module.min.js"></script>
<script type="module" src="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/component/accordion/accordion.module.min.js"></script>
```

### Support Internet Explorer 11 (Legacy)

```html
<script type="text/javascript" nomodule src="dist/legacy/legacy.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/core/core.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/component/accordion/accordion.nomodule.min.js"></script>
```

## API JavaScript

### Accès à l'API

```javascript
const elem = document.getElementById('accordion-1');
dsfr(elem).collapse.disclose(); // Ouvre l'accordéon
```

### Instances

Les éléments suivants sont instanciés automatiquement :
- Groupe : `fr-accordions-group`
- Accordéon : `fr-accordion`
- Bouton : `fr-accordion__btn`
- Collapse : `fr-collapse`

Un attribut `data-fr-js-NOM_INSTANCE="true"` est ajouté sur chaque élément instancié.

### API Accordion

| Propriété/Méthode | Type | Description | Exemple |
|-------------------|------|-------------|---------|
| `node` | property | Renvoie le noeud HTML | `dsfr(elem).accordion.node` |
| `isEnabled` | property | Active/désactive l'accordéon | `dsfr(elem).accordion.isEnabled = false` |

### API AccordionGroup

| Propriété/Méthode | Type | Retour | Description |
|-------------------|------|--------|-------------|
| `current` | property | object \| null | Collapse actuellement ouvert |
| `hasFocus` | property | Boolean | Focus sur un élément du groupe |
| `index` | property | Number | Index de l'accordéon courant |
| `isGrouped` | property | Boolean | Les accordéons sont-ils liés ? |
| `length` | property | Number | Nombre d'accordéons |
| `members` | property | Array | Tableau des collapses |
| `node` | property | DOMElement | Noeud HTML du groupe |

**Exemples :**

```javascript
const group = document.querySelector('.fr-accordions-group');

// Obtenir l'accordéon ouvert
const current = dsfr(group).accordionsGroup.current;

// Changer d'accordéon
dsfr(group).accordionsGroup.index = 2;

// Délier les accordéons
dsfr(group).accordionsGroup.isGrouped = false;
```

### API Collapse

| Méthode/Propriété | Type | Description | Exemple |
|-------------------|------|-------------|---------|
| `conceal()` | function | Ferme le collapse | `dsfr(elem).collapse.conceal()` |
| `disclose()` | function | Ouvre le collapse | `dsfr(elem).collapse.disclose()` |
| `isDisclosed` | property | Retourne true si ouvert | `dsfr(elem).collapse.isDisclosed` |
| `isEnabled` | property | Active/désactive | `dsfr(elem).collapse.isEnabled = false` |
| `group` | property | API du groupe parent | `dsfr(elem).collapse.group` |
| `buttons` | property | Boutons d'ouverture | `dsfr(elem).collapse.buttons` |
| `focus()` | function | Replace le focus | `dsfr(elem).collapse.focus()` |
| `parent` | property | Instance parente | `dsfr(elem).collapse.parent` |
| `children` | property | Instances enfantes | `dsfr(elem).collapse.children` |
| `node` | property | Noeud HTML | `dsfr(elem).collapse.node` |

### API CollapseButton

| Méthode/Propriété | Type | Description | Exemple |
|-------------------|------|-------------|---------|
| `focus()` | function | Replace le focus | `dsfr(elem).collapseButton.focus()` |
| `parent` | property | Instance de l'accordéon | `dsfr(elem).collapseButton.parent` |
| `node` | property | Noeud HTML | `dsfr(elem).collapseButton.node` |

## Événements personnalisés

| Événement | Action | Élément | Attribut |
|-----------|--------|---------|----------|
| `dsfr.conceal` | Fermeture | Collapse | `data-fr-js-collapse` |
| `dsfr.disclose` | Ouverture | Collapse | `data-fr-js-collapse` |
| `dsfr.click` | Click sur bouton | CollapseButton | `data-fr-js-collapse-button` |

### Écouter les événements

```javascript
const collapse = document.getElementById('accordion-1');

collapse.addEventListener('dsfr.disclose', function() {
    console.log('Accordéon ouvert');
});

collapse.addEventListener('dsfr.conceal', function() {
    console.log('Accordéon fermé');
});
```

## Règles éditoriales

### Titre
- Rédiger un titre clair, explicite et précis
- L'utilisateur doit comprendre le contenu sans ouvrir l'accordéon
- Utiliser un niveau de titre cohérent avec la hiérarchie de la page

### Contenu
- Soigner la mise en forme (paragraphes, listes, liens...)
- Ne pas placer de texte directement dans la `<div>`, utiliser des balises appropriées
- Éviter les contenus trop courts (privilégier liste ou paragraphe simple)
- Privilégier les interactions simples (boutons, liens)
- Ne pas intégrer de composants complexes (modales, autres accordéons...)

## Exemples d'utilisation dans les widgets Grist

### Widget FAQ / Documentation

```html
<div class="fr-accordions-group">
    <section class="fr-accordion">
        <h3 class="fr-accordion__title">
            <button type="button" class="fr-accordion__btn"
                    aria-expanded="false" aria-controls="faq-1">
                Comment classifier mon système IA ?
            </button>
        </h3>
        <div id="faq-1" class="fr-collapse">
            <p>La classification se fait via le questionnaire de 10 questions...</p>
            <ul>
                <li>Haut risque : ≥50 points</li>
                <li>Risque surveillé : 30-49 points</li>
                <li>Risque limité : 15-29 points</li>
                <li>Risque minimal : &lt;15 points</li>
            </ul>
        </div>
    </section>

    <section class="fr-accordion">
        <h3 class="fr-accordion__title">
            <button type="button" class="fr-accordion__btn"
                    aria-expanded="false" aria-controls="faq-2">
                Quelles sont les obligations pour un système à haut risque ?
            </button>
        </h3>
        <div id="faq-2" class="fr-collapse">
            <ul class="fr-raw-list">
                <li>✓ AI Data Fundamentals (AIDF)</li>
                <li>✓ Marquage CE</li>
                <li>✓ Surveillance post-commercialisation</li>
                <li>✓ Documentation technique complète</li>
            </ul>
        </div>
    </section>
</div>
```

### Widget avec sections de formulaire

```html
<form>
    <div class="fr-accordions-group">
        <section class="fr-accordion">
            <h3 class="fr-accordion__title">
                <button type="button" class="fr-accordion__btn"
                        aria-expanded="true" aria-controls="section-1">
                    1. Informations générales
                </button>
            </h3>
            <div id="section-1" class="fr-collapse">
                <div class="fr-input-group">
                    <label class="fr-label" for="nom-projet">Nom du projet</label>
                    <input class="fr-input" type="text" id="nom-projet" name="nom">
                </div>
            </div>
        </section>

        <section class="fr-accordion">
            <h3 class="fr-accordion__title">
                <button type="button" class="fr-accordion__btn"
                        aria-expanded="false" aria-controls="section-2">
                    2. Classification AI Act
                </button>
            </h3>
            <div id="section-2" class="fr-collapse">
                <!-- Contenu du questionnaire -->
            </div>
        </section>
    </div>
</form>
```

### Accordéons indépendants (plusieurs ouverts simultanément)

```html
<div class="fr-accordions-group" data-fr-group="false">
    <section class="fr-accordion">
        <h3 class="fr-accordion__title">
            <button type="button" class="fr-accordion__btn"
                    aria-expanded="false" aria-controls="risque-1">
                Risque de biais algorithmique
            </button>
        </h3>
        <div id="risque-1" class="fr-collapse">
            <p><strong>Probabilité :</strong> Élevée (4/5)</p>
            <p><strong>Gravité :</strong> Critique (5/5)</p>
            <p><strong>Score :</strong> 20</p>
        </div>
    </section>

    <section class="fr-accordion">
        <h3 class="fr-accordion__title">
            <button type="button" class="fr-accordion__btn"
                    aria-expanded="false" aria-controls="risque-2">
                Risque de non-conformité RGPD
            </button>
        </h3>
        <div id="risque-2" class="fr-collapse">
            <p><strong>Probabilité :</strong> Moyenne (3/5)</p>
            <p><strong>Gravité :</strong> Élevée (4/5)</p>
            <p><strong>Score :</strong> 12</p>
        </div>
    </section>
</div>
```

## Accessibilité (RGAA)

### Points clés

- ✅ Utiliser les attributs ARIA appropriés (`aria-expanded`, `aria-controls`)
- ✅ Le bouton doit avoir un libellé explicite
- ✅ Le contenu doit utiliser les balises sémantiques appropriées
- ✅ Navigation au clavier fonctionnelle (Tab, Entrée, Espace)
- ✅ Focus visible sur le bouton
- ✅ État ouvert/fermé annoncé aux lecteurs d'écran

### Navigation clavier

| Touche | Action |
|--------|--------|
| Tab | Naviguer entre les boutons d'accordéons |
| Entrée / Espace | Ouvrir/fermer l'accordéon |
| Shift + Tab | Navigation arrière |

## Classe dynamique

Quand le JavaScript est activé, le collapse reçoit automatiquement la classe `fr-collapse--expanded` lorsque `aria-expanded="true"`. C'est cette classe qui déclenche l'ouverture visuelle.

## Ressources

- **Documentation officielle DSFR** : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/accordeon
- **Accessibilité** : https://accessibilite.numerique.gouv.fr/
- **Code source** : https://github.com/GouvernementFR/dsfr

## Notes pour les développeurs

1. **IDs uniques** : Chaque collapse doit avoir un ID unique dans la page
2. **Hiérarchie des titres** : Adapter le niveau de titre (`<h1>` à `<h6>`) selon le contexte
3. **Contenu libre** : Le collapse accepte tout contenu HTML, mais utiliser les balises appropriées
4. **Performance** : Le composant fonctionne automatiquement une fois le JS chargé
5. **Variantes** : Aucune variation de style ou accentuation n'est disponible sur ce composant
