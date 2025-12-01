# Tableau (Table)

Le tableau permet de présenter une liste structurée de données textuelles et/ou numériques dans le but de simplifier l'analyse et la comparaison d'informations pour l'usager.

## Quand utiliser ce composant ?

Utiliser le tableau pour présenter des données. À titre d'exemple, il peut :

- Permettre une visualisation de données organisées en lignes et en colonnes.
- Permettre l'analyse et la comparaison d'informations.
- Servir d'alternative textuelle à un graphique, si vous souhaitez que l'usager puisse lire les valeurs exactes des données plutôt que de les estimer visuellement, par exemple.

Toutefois, si les tableaux sont très pratiques, ils peuvent très vite devenir complexes et générer des difficultés de compréhension. Soyez donc créatifs pour que votre interface soit synthétique, intuitive et agréable à utiliser en proposant, si c'est nécessaire, plusieurs modes de présentation des données.

**Information :** Ce composant tableau n'est pas un tableur, il ne permet pas (sauf développement ad hoc) de réaliser d'opérations avec les données.

## Comment utiliser ce composant ?

- Adapter l'usage du tableau à la complexité et/ou au volume de données à présenter. Lorsque les données sont très simples ou si votre tableau possède moins de 4 lignes ou 3 colonnes, envisagez d'autres formats de présentation.
- Insérer des composants au sein de vos tableaux, selon vos besoin, et parmi ceux autorisés : texte, chiffres, icône, pictogramme, tag, badge, bouton, lien, champ de saisie, infobulle, interrupteur et liste déroulante.
- Permettre le tri du contenu de chaque colonne par ordre croissant ou décroissant, lorsque nécessaire.
- Rendre la première colonne flottante afin de permettre le défilement du reste du tableau, notamment s'il est plus large que la fenêtre.
- Ajouter une pagination dans la barre d'outils si le tableau contient beaucoup de lignes afin de faciliter la navigation de l'usager.
- Ajouter des cases à cocher, placée tout à gauche de la ligne, si vous souhaitez permettre la sélection de lignes.
- Intégrer un ou plusieurs boutons d'actions spécifiques à une ligne dans une cellule, au besoin. Dans ce cas, pensez à utiliser les boutons secondaires et tertiaires pour apporter la bonne hiérarchie entre les différents niveaux d'actions possibles.
- Permettre la sélection du nombre de lignes affichées par page du tableau via une liste déroulante lorsque cela est pertinent.
- Utiliser des bordures verticales pour améliorer la lisibilité du tableau si ce dernier est complexe.
- Améliorer la lisibilité du tableau en version mobile en utilisant une vue plus adaptée comme la liste.
- Placer systématiquement les actions de colonnes à droite au sein de la cellule d'en-tête.
- Placer systématiquement la colonne de case à cocher à gauche.
- Placer systématiquement la cellule d'action par ligne à droite.
- Permettre la fusion de cellules d'en-tête et de contenu, de façon verticale et/ou horizontale.
- Éviter de détourner l'usage des tableaux. Ils sont destinés à présenter des données et non à faire de la mise en page.

## Structure du composant

Le composant Tableau permet de présenter des données tabulaires. Sa structure est conçue pour s'adapter aux écrans mobiles et comprend les éléments suivants :

- Un conteneur principal sous la balise `<div>` :
  - Doit avoir la classe `fr-table`.
- Un premier sous-conteneur sous la balise `<div>` :
  - Doit avoir la classe `fr-table__wrapper`.
- Un deuxième sous-conteneur sous la balise `<div>` :
  - Doit avoir la classe `fr-table__container`.
- Un troisième sous-conteneur sous la balise `<div>` :
  - Doit avoir la classe `fr-table__content`.
- Une zone de contenu pour le tableau :
  - Représentée par un élément `<table>`.
- Un titre, obligatoire, qui peut être positionné en haut (par défaut), en bas ou hors écran :
  - Représenté par un élément `<caption>`.
- Une ligne d'en-tête de colonne, obligatoire :
  - Représentée par un élément `<thead>`.
- Plusieurs ligne de corps, obligatoires :
  - Regroupées dans un ou plusieurs éléments `<tbody>`.
  - Représentées par un élément `<tr>`.
- Plusieurs cellules de contenu, obligatoires :
  - Représentées par un élément `<th>` ou `<td>`.

### Exemple de structure HTML

```html
<div class="fr-table">
    <div class="fr-table__wrapper">
        <div class="fr-table__container">
            <div class="fr-table__content">
                <table>
                    <caption>
                        Titre du tableau (caption)
                    </caption>
                    <thead>
                        <tr>
                            <th scope="col">th0</th>
                            <th scope="col">th1</th>
                            <th scope="col">th2</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Lorem ipsum dolor sit amet</td>
                            <td>Lorem ipsum dolor sit amet</td>
                            <td>Lorem ipsum dolor sit amet</td>
                        </tr>
                        <tr>
                            <td>Lorem ipsum dolor sit amet</td>
                            <td>Lorem ipsum dolor sit amet</td>
                            <td>Lorem ipsum dolor sit amet</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</div>
```

## CSS

### Installation du CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

Il est possible d'importer les fichiers CSS avec un niveau de granularité adapté à vos besoins. Voir le découpage des fichiers CSS du DSFR dans la documentation dédiée.

#### Dépendances CSS

| Dépendance | Obligatoire | Remarque |
|------------|-------------|----------|
| Core | Oui | |
| Table | Oui | |
| Checkbox | Non | Uniquement pour la version avec sélection de lignes |
| Button | Non | Uniquement pour les boutons de trie ou l'ajout d'actions dans le header ou footer du tableau |
| Select | Non | Uniquement pour la selection du nombre de ligne par page dans footer du tableau |
| Pagination | Non | Uniquement pour ajouter une pagination dans le footer du tableau |
| Segmented | Non | Uniquement pour ajouter un contrôle segmenté dans le header du tableau |

#### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/table/table.min.css" rel="stylesheet">
```

**NB:** Il est aussi possible d'importer le CSS global du DSFR `dsfr.min.css`.

Pour une compatibilité avec Internet Explorer 11, les fichiers legacy peuvent également être ajoutés :

```html
<link href="dist/core/core.legacy.min.css" rel="stylesheet">
<link href="dist/component/table/table.legacy.min.css" rel="stylesheet">
```

## Comportement du tableau

Le tableau par défaut scrollable prend toujours 100% de la largeur de son conteneur et le contenu des cellules est affiché sur une seule ligne.

La largeur d'une colonne s'adapte à la largeur de la cellule dont le contenu est le plus long.

Nous mettons à disposition les variations multiline à travers l'utilisation des classes `fr-table--multiline` sur le composant ou `fr-cell--multiline` au niveau des cellules (`<th>` ou `<td>`) pour permettre le retour à la ligne à l'intérieur des cellules. C'est alors le navigateur qui décidera de faire des passages à la ligne pour éviter au maximum le scroll.

Nous mettons aussi à disposition des classes `fr-col--xs` (et sm, md, lg) pour fixer la largeur minimale d'une colonne. Associées à la classe `fr-table--multiline` elles permettent de fixer la largeur des colonnes du tableau (hors césure de mots).

## Variantes

### Variantes de tableau avec retour à la ligne automatique dans les cellules

Le tableau met à disposition des classes CSS pour permettre le retour à la ligne à l'intérieur des cellules :

- `fr-table--multiline` sur le composant `fr-table` applique le retour à la ligne sur toutes les cellules du tableau
- `fr-cell--multiline` au niveau des cellules (`<th>` ou `<td>`) applique le retour à la ligne sur la cellule

```html
<div class="fr-table fr-table--multiline">
    <!-- Contenu de tableau avec retour à la ligne automatique dans les cellules -->
</div>
```

### Variantes de tableau avec largeur de colonnes minimales

Vous avez à votre disposition des classes CSS pour permettre de fixer la largeur minimale des colonnes :

- `fr-col--xs` pour fixer une colonne minimale à 4rem (64px),
- `fr-col--sm` pour fixer une colonne minimale à 5rem (80px),
- `fr-col--md` pour fixer une colonne minimale à 12.5rem (200px),
- `fr-col--lg` pour fixer une colonne minimale à 25 rem (400px).

Ces classes doivent être utilisées au niveau des en-têtes de colonne `<th>`.

Combinées avec la classe `fr-table--multiline` au niveau du composant elles permettent de fixer la largeur des colonnes du tableau (hors césure de mots).

```html
<div class="fr-table fr-table--multiline">
    <div class="fr-table__wrapper">
        <div class="fr-table__container">
            <div class="fr-table__content">
                <table>
                    <caption>Titre du tableau (caption)</caption>
                    <thead>
                        <tr>
                            <th class="fr-col--xs">xs</th>
                            <th class="fr-col--sm">sm</th>
                            <th class="fr-col--md">md</th>
                            <th class="fr-col--lg">lg</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Lorem</td>
                            <td>Lorem ipsum</td>
                            <td>Lorem ipsum dolor sit</td>
                            <td>Lorem ipsum dolor sit amet consectetur</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</div>
```

### Variantes de densité

Le tableau peut être de différentes densités. Si la taille des composants intégrés dans les cellules ne change pas, cela vous permet de varier la densité d'affichage de votre tableau en fonction de son contenu. Il existe 3 niveaux de densité pour les cellules du tableau :

- `fr-table--sm` : densité SM,
- Par défaut en densité MD,
- `fr-table--lg` : densité LG.

```html
<div class="fr-table fr-table--sm">
    <!-- Contenu de tableau SM -->
</div>
<div class="fr-table">
    <!-- Contenu de tableau MD -->
</div>
<div class="fr-table fr-table--lg">
    <!-- Contenu de tableau LG -->
</div>
```

### Variante de tableau avec séparateurs verticaux

Vous avez la possibilité d'afficher des séparateurs de colonnes verticaux (obligatoires en cas de tableaux complexes) grâce à l'ajout de la classe `fr-table--bordered`.

```html
<div class="fr-table fr-table--bordered">
    <!-- Contenu de tableau -->
</div>
```

### Variante de tableau non scrollable

Le conteneur est responsive par défaut mais vous avez la possibilité de rendre le tableau non scrollable grâce à la classe `fr-table--no-scroll`.

```html
<div class="fr-table fr-table--no-scroll">
    <!-- Contenu de tableau -->
</div>
```

### Variantes de placement du titre

Le titre (`<caption>`) du tableau est obligatoire mais peut être positionné à différents emplacements :

- Par défaut en haut.
- `fr-table--caption-bottom` : en bas.
- `fr-table--no-caption` : hors écran.

```html
<div class="fr-table">
    <!-- Contenu de tableau avec titre en haut -->
</div>
<div class="fr-table fr-table--caption-bottom">
    <!-- Contenu de tableau avec titre en bas -->
</div>
<div class="fr-table fr-table--no-caption">
    <!-- Contenu de tableau avec titre hors écran -->
</div>
```

### Variantes de tableau avec lignes sélectionnables

Le tableau peut contenir des en-têtes de ligne contenant des cases à cocher permettant de selectionner la ligne entière :

- L'en-tête du tableau `<thead>` doit contenir :
  - dans sa première colonne une en-tête de ligne `<th>` avec la classe `fr-cell--fixed` contenant :
    - un texte hors écran avec la classe `fr-sr-only` annonçant l'action de "Sélectionner".
- Chaque ligne du corps du tableau `<tr>` doit avoir un attribut `aria-selected` et contenir :
  - dans sa première colonne une en-tête de ligne `<th>` avec la classe `fr-cell--fixed` contenant :
    - une case à cocher `<input type="checkbox">` avec les attributs `data-fr-row-select="true"` et `id` obligatoires, pour être liée au libellé.
    - un libellé `<label>`, avec la classe `fr-label`, lié à la case à cocher via l'attribut `for`, sa valeur doit correspondre à l'attribut `id` de la case à cocher et son texte doit annonçer l'action de selection par exemple "Sélectionner la ligne 1".

```html
<div class="fr-table">
    <div class="fr-table__wrapper">
        <div class="fr-table__container">
            <div class="fr-table__content">
                <table>
                    <caption>Titre du tableau (caption)</caption>
                    <thead>
                        <tr>
                            <th class="fr-cell--fixed" role="columnheader">
                                <span class="fr-sr-only">Sélectionner</span>
                            </th>
                            <th scope="col">th0</th>
                            <th scope="col">th1</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <th class="fr-cell--fixed" scope="row">
                                <div class="fr-checkbox-group fr-checkbox-group--sm">
                                    <input data-fr-row-select="true" id="table-select-checkbox-1" type="checkbox">
                                    <label class="fr-label" for="table-select-checkbox-1">
                                        Sélectionner la ligne 1
                                    </label>
                                </div>
                            </th>
                            <td>Lorem ipsum dolor sit amet</td>
                            <td>Lorem ipsum dolor sit amet</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</div>
```

### Variantes de tableau à double entrée avec colonne d'en-tête fixe

Le tableau peut présenter des en-têtes de ligne `<th>` fixes au scroll horizontal avec la classe `fr-cell--fixed`.

```html
<div class="fr-table">
    <div class="fr-table__wrapper">
        <div class="fr-table__container">
            <div class="fr-table__content">
                <table>
                    <caption>Titre du tableau (caption)</caption>
                    <thead>
                        <tr>
                            <th class="fr-cell--fixed" role="columnheader">
                                <span class="fr-sr-only">En tête de colonne [À MODIFIER]</span>
                            </th>
                            <th scope="col">th0</th>
                            <th scope="col">th1</th>
                            <th scope="col">th2</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <th class="fr-cell--fixed" scope="row">th0</th>
                            <td>Lorem ipsum dolor sit amet</td>
                            <td>Lorem ipsum dolor sit amet</td>
                            <td>Lorem ipsum dolor sit amet</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</div>
```

## Alignement

Par défaut, le contenu des cellules est aligné à gauche et centré verticalement.

### Alignement vertical

Vous avez à votre disposition des classes CSS pour modifier l'alignement vertical des cellules de contenu :

- `fr-cell--top` : Alignement vertical en haut.
- Alignement vertical au centre par défaut.
- `fr-cell--bottom` : Alignement vertical en bas.

### Alignement horizontal

Vous avez à votre disposition des classes CSS pour modifier l'alignement horizontal des cellules de contenu :

- Alignement horizontal à gauche par défaut.
- `fr-cell--center` : Alignement horizontal au centre.
- `fr-cell--right` : Alignement horizontal à droite.

### Exemple de tableau avec des alignements de cellules différents

```html
<div class="fr-table fr-table--bordered">
    <div class="fr-table__wrapper">
        <div class="fr-table__container">
            <div class="fr-table__content">
                <table>
                    <caption>Titre du tableau (caption)</caption>
                    <thead>
                        <tr>
                            <th scope="col">th0</th>
                            <th scope="col">th1</th>
                            <th scope="col">th2</th>
                            <th scope="col">th3</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="fr-cell--top">Lorem ipsum</td>
                            <td class="fr-cell--bottom">Lorem ipsum</td>
                            <td class="fr-cell--center">Lorem ipsum</td>
                            <td class="fr-cell--right">
                                Lorem<br>
                                Lorem ipsum<br>
                                Lorem ipsum dolor sit amet
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</div>
```

## JavaScript

### Installation du JavaScript

Pour fonctionner correctement, le JavaScript du composant et de ses dépendances doivent être importés. L'import doit se faire à la fin de la page, avant la balise `</body>`, et de préférence avec les fichiers minifiés, car plus légers.

```html
<script type="module" src="dist/core/core.module.min.js"></script>
<script type="module" src="dist/component/checkbox/checkbox.module.min.js"></script>
<script type="module" src="dist/component/table/table.module.min.js"></script>
```

**NB:** Il est aussi possible d'importer le Js global du DSFR `dsfr.module.min.js`

Pour fonctionner sur Internet Explorer 11, un fichier legacy, en version nomodule ES5, peut aussi être importé :

```html
<script type="text/javascript" nomodule src="dist/legacy/legacy.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/core/core.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/component/checkbox/checkbox.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/component/table/table.nomodule.min.js"></script>
```

Une fois le JavaScript chargé, le composant fonctionne automatiquement.

### Instances

Sur le tableau, les éléments suivants sont instanciés :

- Le composant "table", via la classe : `fr-table`
- L'élément `<table>` du composant, via le sélecteur : `fr-table table` (pour la version dépréciée)
- Les lignes du tableau, via le sélecteur : `fr-table tr` (pour la version avec lignes sélectionnables)
- Les checkboxes du tableau, via le sélecteur : `fr-table td` (pour la version avec lignes sélectionnables)

Une fois chargé, le Js ajoute un attribut `data-fr-js-NOM_INSTANCE="true"` sur chacun des éléments instanciés.

## API

Il est possible d'interagir avec les instances du composants en JavaScript via une API.

Cette API est disponible depuis la méthode `window.dsfr(instance)` du core.

Exemple :

```javascript
const elem = document.getElementById('ID_TABLE');
dsfr(elem).table.isEnabled;
```

L'ensemble des propriétés et méthodes disponibles sont définies ci-après :

### table

#### isEnabled

| Description | Défini si le fonctionnement du tableau est activé ou non |
|-------------|----------------------------------------------------------|
| Type | property |
| Retour | Boolean |
| Exemple | `dsfr(elem).table.isEnabled = false` |

#### parent

| Description | Retourne l'instance du dsfr parent |
|-------------|-------------------------------------|
| Type | property |
| Retour | object \| null |
| Exemple | `dsfr(elem).parent` |

#### children

| Description | Renvoie un tableau d'instances enfants |
|-------------|----------------------------------------|
| Type | property |
| Retour | Array |
| Exemple | `dsfr(elem).children` |

#### node

| Description | Renvoie le noeud HTML de l'élément. |
|-------------|-------------------------------------|
| Type | property |
| Retour | DOMElement |
| Exemple | `dsfr(elem).table.node` |

### tableCaption

#### resize

| Description | Permet de mettre à jour la taille du caption après un changement de libellé. |
|-------------|-------------------------------------------------------------------------------|
| Type | method |
| Retour | DOMElement |
| Exemple | `dsfr(tableCaption).tableCaption.resize()` |

## Règles éditoriales

- Utiliser des titres de colonnes et, le cas échéant, de lignes, clairs et concis.
- Mettre une majuscule au début des titres de colonnes et ne pas terminer par un élément de ponctuation (virgule, point ou point-virgule).
- Synthétiser les contenus à l'intérieur de chaque cellule.
- Indiquer "N/A" dans toute cellule vide.
- Préciser l'unité de mesure d'une donnée dans le titre de la colonne correspondante, afin d'éviter les répétitions dans les cellules de contenu.
- Aligner les chiffres à droite au sein de la cellule. Par défaut, le reste du contenu des cellules est aligné à gauche et centré verticalement.
