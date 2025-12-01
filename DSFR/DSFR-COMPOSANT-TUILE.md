# DSFR - Composant Tuile

## Présentation

La tuile est un élément d'interaction avec l'interface permettant de rediriger l'usager vers des pages de contenu.

## Quand utiliser ce composant ?

Utiliser la tuile pour créer un raccourci ou un point d'entrée vers des pages de contenu.

**Important :** La tuile n'a pas vocation à être utilisée pour mettre en avant l'action principale d'une page.

### Différence avec la carte

Bien différencier la tuile de la carte. La carte permet d'avoir un aperçu du contenu des pages vers lesquelles elle renvoie.

## Comment utiliser ce composant ?

### Règles générales

- Utiliser les tuiles pour créer des collections ou listes d'éléments similaires. La tuile n'est jamais présentée de manière isolée.
- Harmoniser la hauteur des tuiles par ligne, en prenant la plus importante comme référence, lorsque celles-ci sont disposées au sein d'une liste ou d'une collection.
- Proposer des tuiles de même structure lorsque celles-ci composent une liste ou une collection.
- Préférer les tuiles horizontales lorsque les titres sont longs.
- Conserver l'intégralité de la tuile cliquable lorsque vous proposez cette variation.

### À faire

✅ Contraindre toutes les tuiles d'une même ligne à la même hauteur.
✅ Conserver un contenu commun au sein des tuiles qui forment un même ensemble.

### À ne pas faire

❌ Ne pas créer de disparité dans la hauteur des tuiles d'une même ligne.
❌ Ne pas proposer des contenus différents entre chacune des tuiles d'un même ensemble.

## Règles éditoriales

- Rédiger des titres et descriptions synthétiques.
- Proposer des contenus distincts pour chaque tuile, en évitant de réutiliser plusieurs fois le même pictogramme.
- Être vigilant sur les dimensions des illustrations utilisées afin de garantir leur adaptation aux différents types d'affichages responsive.

## Structure HTML

### Structure de base

Le composant Tuile est un élément interactif permettant de donner des aperçus cliquables d'une page de contenu.

Structure :
- La tuile est un élément HTML `<div>` défini par la classe `fr-tile`
- Les Tuiles sont généralement utilisées au sein d'une grille (voir grille dans les fondamentaux)
- Son contenu est structuré en plusieurs parties :

#### L'en-tête de la tuile (optionnel)

- `fr-tile__header` : Conteneur de l'en-tête
- `fr-tile__pictogram` : Pictogramme (voir Pictogramme)

#### Le corps de la tuile (obligatoire)

- `fr-tile__body` : Conteneur principal
- `fr-tile__content` : Contenu de la tuile
  - `fr-tile__title` : Titre (obligatoire) - élément HTML `<hx>` pouvant contenir un lien ou un simple texte
  - `fr-tile__desc` : Description (optionnelle) - élément `<p>`
  - `fr-tile__detail` : Texte de détail (optionnel) - élément `<p>`
  - `fr-tile__start` : Zone se plaçant avant le contenu, peut accueillir :
    - Un badge ou un tag (optionnels)
    - Un texte de détail `fr-tile__detail` (optionnel), auquel on peut associer une icône

### Exemple de structure HTML simple

```html
<div class="fr-tile fr-enlarge-link">
    <div class="fr-tile__body">
        <div class="fr-tile__content">
            <h3 class="fr-tile__title">
                <a href="[url - à modifier]">Intitulé de la tuile</a>
            </h3>
            <p class="fr-tile__desc">Description de la tuile</p>
            <p class="fr-tile__detail">Détail</p>
            <div class="fr-tile__start">
                <p class="fr-badge fr-badge--purple-glycine">Libellé badge</p>
            </div>
        </div>
    </div>
    <div class="fr-tile__header">
        <div class="fr-tile__pictogram">
            <svg aria-hidden="true" class="fr-artwork" viewBox="0 0 80 80" width="80px" height="80px">
                <use class="fr-artwork-decorative" href="../../../dist/artwork/pictograms/buildings/city-hall.svg#artwork-decorative"></use>
                <use class="fr-artwork-minor" href="../../../dist/artwork/pictograms/buildings/city-hall.svg#artwork-minor"></use>
                <use class="fr-artwork-major" href="../../../dist/artwork/pictograms/buildings/city-hall.svg#artwork-major"></use>
            </svg>
        </div>
    </div>
</div>
```

## Variante : Tuile de téléchargement

Une variante tuile de téléchargement existe, comme pour les composants Lien et Carte, pour proposer le téléchargement d'un fichier. La tuile de téléchargement est toujours en format horizontal par défaut.

### Règles spécifiques

- La Tuile doit avoir la classe `fr-tile--download`
- L'intitulé du titre doit avoir ce format : **Télécharger le/la [Typologie de document] « [Nom du document] »**
- Le lien du titre doit avoir :
  - L'attribut `download` (ajouter une valeur à l'attribut permet de renommer le fichier au moment du téléchargement)
  - L'attribut `hreflang`, si le fichier est dans une autre langue, avec comme valeur le code langue du document à télécharger
- **Étendre le clic à toute la tuile est obligatoire** :
  - Ajouter la classe `fr-enlarge-link` sur la tuile pour étendre le lien
  - Dans le cas d'un téléchargement programmatique, le téléchargement peut venir d'un bouton. Il est possible de remplacer le lien du titre par un `button`. Il faudra alors utiliser la classe `fr-enlarge-button` sur la tuile.
- Le texte de détail `fr-tile__detail` est **obligatoire**
  - Il doit indiquer le type de fichier (son extension), son poids, et sa langue si différente de la page
  - Il est possible de remplir automatiquement le détail en JS grâce à l'attribut `data-fr-assess-file` sur le lien

### Exemple de tuile de téléchargement

```html
<div class="fr-tile fr-tile--download fr-enlarge-link">
    <div class="fr-tile__body">
        <div class="fr-tile__content">
            <h3 class="fr-tile__title">
                <a download href="[url - à modifier]">Télécharger le document XX</a>
            </h3>
            <p class="fr-tile__desc">Description (optionnelle)</p>
            <p class="fr-tile__detail">Détail obligatoire (Extension - Poids - Langue)</p>
        </div>
    </div>
    <div class="fr-tile__header">
        <div class="fr-tile__pictogram">
            <svg aria-hidden="true" class="fr-artwork" viewBox="0 0 80 80" width="80px" height="80px">
                <use class="fr-artwork-decorative" href="../../../../dist/artwork/pictograms/document/document-download.svg#artwork-decorative"></use>
                <use class="fr-artwork-minor" href="../../../../dist/artwork/pictograms/document/document-download.svg#artwork-minor"></use>
                <use class="fr-artwork-major" href="../../../../dist/artwork/pictograms/document/document-download.svg#artwork-major"></use>
            </svg>
        </div>
    </div>
</div>
```

## Groupe de Tuiles

Il n'existe pas à proprement parlé de groupe de Tuiles. Néanmoins, les Tuiles sont généralement utilisées sous forme d'un ensemble d'éléments. Elles peuvent être disposées côte à côte grâce à la grille disponible dans les fondamentaux.

La grille permet de définir un nombre de colonnes pour chaque Tuile, sur une base de 12 colonnes, et peut varier en fonction de la taille de l'écran (breakpoint).

### Exemple de grille de Tuiles

```html
<div class="fr-grid-row fr-grid-row--gutters">
    <div class="fr-col-12 fr-col-md-4 fr-col-lg-3">
        <div class="fr-tile fr-enlarge-link">(...)</div>
    </div>
    <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">
        <div class="fr-tile fr-enlarge-link">(...)</div>
    </div>
    <div class="fr-col-12 fr-col-md-6 fr-col-lg-4">
        <div class="fr-tile fr-enlarge-link">(...)</div>
    </div>
</div>
```

## CSS

### Installation du CSS

Pour fonctionner correctement, le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

Il est possible d'importer les fichiers CSS avec un niveau de granularité adapté à vos besoins.

### Dépendances CSS

| Dépendance | Obligatoire |
|-----------|-------------|
| Core      | Oui         |
| Tile      | Oui         |

### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/tile/tile.min.css" rel="stylesheet">
```

## Variantes de taille

La tuile peut avoir différentes tailles qui auront un impact sur la taille du texte, des espacements, du pictogramme, et de l'icône :

- `fr-tile--sm` : Petite tuile
- Par défaut : Tuile moyenne

Par défaut, la tuile prend 100% de la largeur de son conteneur et sa hauteur varie en fonction de son contenu. La largeur des Tuiles peut être ajustée via le nombre de colonnes de la grille.

### Recommandations de largeur

- 2 à 4 colonnes pour une Tuile SM
- 3 à 6 colonnes pour une Tuile MD

### Exemples de variantes de taille

```html
<div class="fr-tile fr-tile--sm fr-enlarge-link">
    <!-- Contenu de la tuile SM -->
</div>
<div class="fr-tile fr-enlarge-link">
    <!-- Contenu de la tuile MD -->
</div>
```

## Variantes de style

La tuile est disponible en plusieurs variantes de style :

- `fr-tile--grey` : Tuile avec fond gris
- `fr-tile--no-background` : Tuile sur fond transparent
- `fr-tile--no-border` : Tuile sans bordure
- `fr-tile--shadow` : Tuile avec ombre portée

### Exemples de variantes de style

```html
<div class="fr-tile fr-tile--grey fr-enlarge-link">
    <!-- Contenu de la tuile sur fond gris -->
</div>
<div class="fr-tile fr-tile--no-background fr-enlarge-link">
    <!-- Contenu de la tuile sur fond transparent -->
</div>
<div class="fr-tile fr-tile--no-border fr-enlarge-link">
    <!-- Contenu de la tuile sans bordure -->
</div>
<div class="fr-tile fr-tile--shadow fr-enlarge-link">
    <!-- Contenu de la tuile avec ombre -->
</div>
```

## Variantes d'orientation

Les tuiles sont disponibles, par défaut, en format vertical (pictogramme en haut et contenu en bas). Il existe aussi des variantes permettant de passer la tuile en format horizontal (pictogramme à gauche et contenu à droite).

### Classes d'orientation

- `fr-tile--horizontal` : Passe la tuile en format horizontal en mobile et desktop
- `fr-tile--horizontal` + `fr-tile--vertical@md` : Passe la tuile en format horizontal puis en vertical à partir du breakpoint MD (768px)
- `fr-tile--horizontal` + `fr-tile--vertical@lg` : Passe la tuile en format horizontal puis en vertical à partir du breakpoint LG (992px)

### Exemples de tuiles horizontales

```html
<div class="fr-tile fr-tile--horizontal fr-enlarge-link">
    <!-- Contenu de la tuile horizontale -->
</div>
<div class="fr-tile fr-tile--horizontal fr-tile--vertical@md fr-enlarge-link">
    <!-- Contenu de la tuile horizontale puis verticale à partir du breakpoint MD -->
</div>
<div class="fr-tile fr-tile--horizontal fr-tile--vertical@lg fr-enlarge-link">
    <!-- Contenu de la tuile horizontale puis verticale à partir du breakpoint LG -->
</div>
```

## Variantes d'icônes

Par défaut, sur les tuiles avec lien étendu et non externe, une icône "arrow-right" apparaît en bas à droite. Dans certains cas, comme pour réduire la taille de la tuile, il peut être utile de retirer cette icône.

Il suffit pour cela d'ajouter la classe `fr-tile--no-icon` sur la tuile.

**Important :** Si le lien est un lien externe, l'icône "external-link" reste obligatoire.

### Exemple de retrait d'icône

```html
<div class="fr-tile fr-enlarge-link fr-tile--no-icon">
    <!-- Contenu de la tuile -->
</div>
```

## JavaScript

### Installation du JavaScript

Le composant Tuile ne nécessite pas l'utilisation de JavaScript pour son fonctionnement de base.

Une fonctionnalité disponible dans le core permet de remplir automatiquement le détail des Tuiles de téléchargement.

#### Imports JavaScript

À la fin de la page (avant `</body>`) :

```html
<script type="module" src="dist/core/core.module.min.js"></script>
```

Note : Il est aussi possible d'importer le Js global du DSFR `dsfr.module.min.js`

#### Pour Internet Explorer 11

```html
<script type="text/javascript" nomodule src="dist/legacy/legacy.nomodule.min.js" ></script>
<script type="text/javascript" nomodule src="dist/core/core.nomodule.min.js"></script>
```

### Remplissage automatique du détail (Tuile de téléchargement)

Pour instancier le javascript de remplissage automatique du détail sur la Tuile de téléchargement, ajouter l'attribut `data-fr-assess-file` sur le lien du titre.

**Fonctionnement :**
- Les propriétés de type, poids, et langue sont récupérées depuis le fichier
- Le texte de détail est automatiquement remplacé au chargement du JS
- Il est conseillé de tout de même remplir les infos connues dans le détail en solution de repli

**Important :**
- Pour fonctionner, le fichier à télécharger doit être sur le même cross-domain que le site
- Si la page est en Anglais, l'attribut `data-fr-assess-file` doit prendre la valeur `"bytes"`, pour afficher le poids en Bytes plutôt qu'en Octet

#### Exemple

```html
<a href="fichier.pdf" download data-fr-assess-file>Télécharger le document</a>
```

### API JavaScript

L'activation ou la désactivation de la fonction de remplissage automatique du détail des Tuiles de téléchargement (assess-file) n'est pas disponible via l'API JS, elle se fait via l'ajout ou le retrait de l'attribut `data-fr-assess-file` sur le lien.

## Classes CSS de référence

### Classes principales

- `fr-tile` : Classe de base de la tuile
- `fr-tile__header` : En-tête de la tuile
- `fr-tile__pictogram` : Conteneur du pictogramme
- `fr-tile__body` : Corps de la tuile
- `fr-tile__content` : Contenu de la tuile
- `fr-tile__title` : Titre de la tuile
- `fr-tile__desc` : Description de la tuile
- `fr-tile__detail` : Détail de la tuile
- `fr-tile__start` : Zone avant le contenu

### Classes modificatrices

#### Taille
- `fr-tile--sm` : Petite tuile

#### Style
- `fr-tile--grey` : Fond gris
- `fr-tile--no-background` : Fond transparent
- `fr-tile--no-border` : Sans bordure
- `fr-tile--shadow` : Avec ombre portée

#### Orientation
- `fr-tile--horizontal` : Format horizontal
- `fr-tile--vertical@md` : Retour au format vertical à partir du breakpoint MD
- `fr-tile--vertical@lg` : Retour au format vertical à partir du breakpoint LG

#### Type
- `fr-tile--download` : Tuile de téléchargement

#### Icône
- `fr-tile--no-icon` : Sans icône

#### Lien étendu
- `fr-enlarge-link` : Étend le lien à toute la tuile
- `fr-enlarge-button` : Étend le bouton à toute la tuile

## Accessibilité

### Bonnes pratiques

- Utiliser des niveaux de titre (`<hx>`) appropriés pour `fr-tile__title`
- Ajouter `aria-hidden="true"` sur les pictogrammes décoratifs
- Pour les tuiles de téléchargement, indiquer clairement le type de fichier, le poids et la langue dans le détail
- Assurer que les liens et boutons ont des labels explicites
- Maintenir un contraste suffisant entre le texte et le fond

### Attributs ARIA recommandés

Pour les pictogrammes :
```html
<svg aria-hidden="true" class="fr-artwork" viewBox="0 0 80 80">
```

Pour les liens de téléchargement :
```html
<a download href="..." hreflang="fr">Télécharger le document</a>
```

## Références

- Documentation officielle DSFR : https://www.systeme-de-design.gouv.fr/
- Composant Tuile : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/tuile/
- Grille DSFR : Voir `DSFR-FONDAMENTAUX.md`
- Pictogrammes : Voir `DSFR-FONDAMENTAUX-ICONES.md`
