# Bouton (Button)

Le bouton est un élément d'interaction avec l'interface permettant à l'usager d'effectuer une action.

## Vue d'ensemble

Le composant Bouton est un élément interactif permettant de déclencher des actions dans l'interface. Il se distingue du lien qui sert à la navigation.

## Quand utiliser ce composant ?

Utiliser le bouton pour déclencher une action dans la page.

### ℹ️ Information

**Bien différencier les boutons des liens.**

Le lien est utilisé pour naviguer à l'intérieur (ou à l'extérieur) de votre site.

## Comment utiliser ce composant ?

### Hiérarchie des boutons

Utiliser le **bouton primaire** pour les actions principales (soumettre un formulaire, rediriger vers un contenu priorisé, etc.). Il est recommandé de limiter son usage à **un bouton primaire par page**.

**✅ À FAIRE** : Aligner un bouton primaire avec un bouton secondaire ou un lien.

**❌ À NE PAS FAIRE** : Ne pas utiliser deux boutons primaires côte à côte.

---

Choisir le **bouton secondaire** pour des actions moins importantes (réinitialiser les valeurs d'un formulaire, par exemple).

Réserver le **bouton tertiaire** pour des actions contextuelles ou alternatives (fermeture de modale, annuler, partager, suivre sur un réseau social, copier un lien, etc.)

**❌ À NE PAS FAIRE** : Ne pas indiquer une hiérarchie entre 2 boutons tertiaires via la présence ou non de contour.

---

**Attention à hiérarchiser les actions proposées à l'usager.** Utiliser une combinaison de bouton de styles différents pour maintenir l'attention sur l'action principale (cf. composant "Groupe de boutons").

**Utiliser uniquement la couleur bleue.** Cette couleur est utilisée pour signaler une interaction sur les éléments principaux (cf. couleurs).

---

## Règles éditoriales

### Rédiger un texte concis et explicite

Rédiger un texte concis et explicite sur l'action que le bouton va initier.

**✅ À FAIRE** : Rédiger un texte clair, explicite et prévisible. L'usager doit savoir ce qui va se passer.

**❌ À NE PAS FAIRE** : Ne pas tromper l'usager. Fournir le contexte que l'usager sache quelle action va être réalisée.

**❌ À NE PAS FAIRE** : Ne pas rédiger des libellés trop longs pour éviter le passage du bouton sur 2 lignes.

### Indiquer l'action, pas le composant

Indiquer ce que l'usager va faire, sans nommer le bouton ou sa localisation.

**✅ À FAIRE** : Se concentrer sur l'action principale, en restant concis et clair.

**❌ À NE PAS FAIRE** : Ne pas mentionner le composant bouton, ni sa localisation.

### Commencer par un verbe d'action

Commencer les textes des boutons avec un verbe d'action.

**✅ À FAIRE** : Commencer les textes des boutons avec un verbe d'action à l'infinitif.

**❌ À NE PAS FAIRE** : Ne pas utiliser "Je" ou ne pas conjuguer le verbe.

### Conserver une unité d'écriture

Conserver une unité dans le format d'écriture de tous vos libellés de boutons.

**✅ À FAIRE** : Mettre des majuscules en début de phrase.

**❌ À NE PAS FAIRE** : Ne pas rédiger les libellés de vos boutons en lettres capitales.

### Éviter les redondances

Éviter les redondances entre instructions et boutons. Ces éléments sont complémentaires.

**✅ À FAIRE** : Accompagner vos boutons d'instructions pour garantir la bonne compréhension de l'usager, lorsque nécessaire.

---

## Structure HTML

### Composant de base

```html
<button class="fr-btn" type="button">
    Libellé bouton
</button>
```

### Éléments constitutifs

1. **Bouton** : Élément HTML `<button>` de type `"button"` défini par la classe `fr-btn`
2. **Contenu textuel** : Doit être succinct et indiquer clairement l'action

---

## Groupes de boutons

Les boutons peuvent être regroupés pour former des ensembles d'actions. Le groupe est formé par la succession de boutons structurés sous forme de liste par l'élément HTML `<ul>` et la classe `fr-btns-group`.

Un groupe est dit **hiérarchisé** s'il dispose d'un bouton primaire et de boutons secondaires. Sauf cas exceptionnel, n'utiliser qu'un seul bouton primaire dans un groupe.

Un groupe **non hiérarchisé** est constitué uniquement de boutons secondaires, tertiaires, et/ou tertiaires sans contours.

### Exemple de groupe de boutons

```html
<ul class="fr-btns-group">
  <li>
    <button class="fr-btn" type="button">
        Bouton 1
    </button>
  </li>
  <li>
    <button class="fr-btn fr-btn--secondary" type="button">
        Bouton 2
    </button>
  </li>
</ul>
```

---

## CSS

### Installation du CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

Il est possible d'importer les fichiers CSS avec un niveau de granularité adapté à vos besoins. Voir le découpage des fichiers CSS du DSFR dans la documentation dédiée.

#### Dépendances CSS

| Dépendance | Obligatoire | Remarque |
|------------|-------------|----------|
| Core | ✅ Oui | |
| Button | ✅ Oui | |
| Utility | ❌ Non | Uniquement pour l'ajout d'icône |

#### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/button/button.min.css" rel="stylesheet">
```

---

## Variantes

### Variantes de style

Le bouton peut avoir différents styles définis par les classes :

- **Par défaut** : Bouton primaire
- `fr-btn--secondary` : Bouton secondaire
- `fr-btn--tertiary` : Bouton tertiaire
- `fr-btn--tertiary-no-outline` : Bouton tertiaire sans contour

#### Exemples de variantes de style

```html
<button class="fr-btn" type="button">
    Bouton primaire
</button>
<button class="fr-btn fr-btn--secondary" type="button">
    Bouton secondaire
</button>
<button class="fr-btn fr-btn--tertiary" type="button">
    Bouton tertiaire
</button>
<button class="fr-btn fr-btn--tertiary-no-outline" type="button">
    Bouton tertiaire sans contour
</button>
```

### Variantes de taille

Le Bouton peut avoir différentes tailles qui auront un impact sur la taille du texte, de l'icône, et des espacements :

- `fr-btn--sm` : Petit bouton
- **Par défaut** : Bouton moyen
- `fr-btn--lg` : Grand bouton

Dans le cas d'un groupe de boutons, la taille des boutons peut être généralisée au niveau du groupe avec les classes `fr-btns-group--sm` ou `fr-btns-group--lg`.

#### Exemples de variantes de taille

```html
<button class="fr-btn fr-btn--sm" type="button">
    Petit bouton
</button>
<button class="fr-btn" type="button">
    Bouton moyen
</button>
<button class="fr-btn fr-btn--lg" type="button">
    Grand bouton
</button>
```

### Variantes d'icônes

Le Bouton peut avoir une icône à l'intérieur, elle est ajoutée via la classe utilitaire d'icône `fr-icon--NOM-ICONE` (voir Icônes).

Cette classe peut être associée à une classe de positionnement de l'icône :

- **Par défaut** : Icône seule, le libellé est caché
- `fr-btn--icon-left` : L'icône apparaît à gauche du libellé
- `fr-btn--icon-right` : L'icône apparaît à droite du libellé

Dans le cas d'un groupe de boutons, le positionnement de l'icône des boutons peut être généralisé au niveau du groupe avec les classes `fr-btns-group--icon-left` ou `fr-btns-group--icon-right`.

#### Exemples de variantes d'icônes

```html
<button type="button" class="fr-btn fr-icon-checkbox-circle-line fr-btn--icon-left">
    Bouton avec icône
</button>
```

### Variante désactivé

Le style désactivé du bouton est appliqué par l'ajout de l'attribut `disabled` sur l'élément `<button>`. Le bouton est alors grisé et les effets au survol et au clic sont retirés. Le pointeur de la souris prend la valeur `not-allowed` au survol du bouton ce qui change son style.

```html
<button class="fr-btn" type="button" disabled>
    Bouton désactivé
</button>
```

---

## Variantes du groupe de bouton

Le groupe de bouton vient avec de nombreuses variations :

### Taille des boutons

Les variations de taille sont accessibles au niveau du groupe avec les classes :

- `fr-btns-group--sm` : Groupe de boutons SM
- `fr-btns-group--lg` : Groupe de boutons LG

### Positionnement des icônes

Les variations de position de l'icône des boutons sont accessibles au niveau du groupe avec les classes :

- `fr-btns-group--icon-left` : Icône des boutons à gauche
- `fr-btns-group--icon-right` : Icône des boutons à droite

### Alignement des boutons

Les boutons d'un groupe sont, par défaut, alignés à gauche. Cet alignement peut être modifié par les classes suivantes :

- `fr-btns-group--right` : Aligne les boutons à droite
- `fr-btns-group--center` : Aligne les boutons au centre

### Groupe de boutons horizontal

Par défaut, le groupe de bouton positionne les boutons les uns en dessous des autres. Les boutons peuvent être placés en ligne par les classes suivantes :

- `fr-btns-group--inline` : Aligne toujours les boutons horizontalement (avec passage à la ligne en cas de dépassement du conteneur)
- `fr-btns-group--inline-sm` : Aligne les boutons horizontalement uniquement à partir du breakpoint SM (576px)
- `fr-btns-group--inline-md` : Aligne les boutons horizontalement uniquement à partir du breakpoint MD (768px)
- `fr-btns-group--inline-lg` : Aligne les boutons horizontalement uniquement à partir du breakpoint LG (992px)

### Inversion du positionnement

L'ordre des boutons peut être inversé lorsqu'ils sont positionnés horizontalement et alignés à droite. La classe `fr-btns-group--inline-reverse` permet d'inverser cet ordre, uniquement en combinaison avec les classes d'alignement "inline" et "right". L'ordre par défaut, et en alignement vertical, correspond à l'ordre des boutons dans le DOM.

### Taille des boutons équivalente

La classe `fr-btns-group--equisized`, grâce au javascript du bouton, ajuste la largeur des boutons du groupe à celle du bouton le plus large. Cela permet d'égaliser la taille des boutons.

**Toutes ces classes peuvent être combinées entre elles.**

---

## JavaScript

Le composant Bouton nécessite l'utilisation de JavaScript **uniquement dans le cas de l'utilisation d'une fonctionnalité avancée** : les groupes de boutons "equisized".

Cette fonctionnalité permet d'adapter automatiquement la taille des boutons d'un groupe à celle du bouton le plus large.

En dehors de cette fonctionnalité l'inclusion du JS du bouton n'est pas utile.

### Installation du JavaScript

Chaque composant utilisant JavaScript possède un fichier JS spécifique et requiert le fichier JS du core.

Il est donc nécessaire d'importer ces fichiers à la fin de la page (avant `</body>`) :

```html
<script type="module" src="dist/core/core.module.min.js"></script>
<script type="module" src="dist/component/button/button.module.min.js"></script>
```

**NB:** Il est aussi possible d'importer le JS global du DSFR `dsfr.module.min.js`

#### Support Internet Explorer 11 (legacy)

Pour fonctionner sur Internet Explorer 11, un fichier legacy, en version nomodule ES5, peut aussi être importé :

```html
<script type="text/javascript" nomodule src="dist/legacy/legacy.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/core/core.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/component/button/button.nomodule.min.js"></script>
```

Une fois le JavaScript chargé, la classe `fr-btn--equisized` fonctionne automatiquement.

### Instances

Sur le bouton, les éléments suivants sont instanciés :

- Le groupe de boutons, via la classe : `fr-btns-group--equisized`
- Les boutons, dans un groupe "equisized", via la classe : `fr-btn`

Une fois chargé, le JS ajoute un attribut `data-fr-js-NOM_INSTANCE="true"` sur chacun des éléments instanciés.

### API JavaScript

Il est possible d'interagir avec les instances du composant en JavaScript via une API.

Cette API est disponible depuis la méthode `window.dsfr(instance)` du core.

L'ensemble des propriétés et méthodes disponibles sont définies ci-après :

#### equisizedsGroup

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(btnGroup).equisizedsGroup.node` |

### ℹ️ Information

L'activation ou la désactivation de la fonction equisize n'est pas disponible en JS, elle se fait via l'ajout ou le retrait de la classe `fr-btns-group--equisized` sur le groupe.

#### equisized

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(btn).equisized.node` |

---

## Références

- **Documentation DSFR** : https://www.systeme-de-design.gouv.fr/composants/bouton
- **GitHub** : https://github.com/GouvernementFR/dsfr
