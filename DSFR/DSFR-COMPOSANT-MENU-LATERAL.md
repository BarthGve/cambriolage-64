# Menu latéral (Side menu)

Le menu latéral est un système de navigation secondaire présentant une liste verticale de liens placée à côté du contenu.

## Vue d'ensemble

Le composant Menu latéral permet aux utilisateurs de naviguer entre les différentes pages d'une rubrique ou d'un même thème. Il se présente sous la forme d'une liste verticale de liens positionnée sur le côté de la page.

Le menu latéral peut contenir jusqu'à **trois niveaux d'arborescence** et permet d'afficher les niveaux 1, 2 et 3 imbriqués d'une rubrique.

## Quand utiliser ce composant ?

Proposer le menu latéral pour permettre à l'usager de naviguer entre les différentes pages d'une rubrique ou d'un même thème.

Il est recommandé d'utiliser le menu latéral sur des **sites ayant un niveau de profondeur assez important** (2 niveaux de navigation ou plus).

### ⚠️ Attention

**Bien différencier le menu latéral du sommaire.** Le sommaire est utilisé pour naviguer entre les différentes sections d'une même page. Il ne présente pas des liens mais des ancres.

---

## Comment utiliser ce composant ?

### Indiquer la page active

- Proposer des pages n'étant pas déjà rattachées à la navigation principale au sein du menu latéral. Il ne s'agit pas d'une redite mais bien d'une navigation secondaire et complémentaire.
- Indiquer à l'usager où il se trouve dans la hiérarchie de navigation en affichant la page active. Pour cela, l'élément de menu correspondant à la page courante doit être en état "actif".

**✅ À FAIRE** : Indiquer la page active au sein du menu latéral pour que l'usager sache où il se trouve.

**❌ À NE PAS FAIRE** : Ne pas laisser l'usager déduire sa position au sein du menu latéral.

---

### Positionnement et dimensions

Placer le menu latéral à gauche ou à droite de la page, selon le besoin. Quel que soit son positionnement, il prend une largeur de **3 colonnes sur toute la hauteur de la page**.

**✅ À FAIRE** : Positionner le menu latéral à gauche ou à droite du contenu, sur une largeur de 3 colonnes, sur toute la hauteur de la page.

**❌ À NE PAS FAIRE** : Ne pas repasser le contenu de la page sur une grille de 12 colonnes en présence d'un menu latéral.

---

### Version mobile

Réintégrer les éléments de navigation du menu latéral dans le menu burger si vous choisissez de le cacher en version mobile.

---

## Règles éditoriales

### Cohérence des noms de rubrique

Garder le même nom de rubrique dans le menu et dans le contenu, pour donner un repère à l'usager.

**✅ À FAIRE** : Avoir le même nom de rubrique dans le contenu et au sein du menu latéral.

**❌ À NE PAS FAIRE** : Ne pas changer le nom de la rubrique au sein du menu latéral pour ne pas perdre l'usager.

---

### Raccourcissement des titres

Raccourcir les titres des liens au sein du menu latéral par rapport aux titres véritables des pages si ces derniers apparaissent trop longs.

---

## Structure HTML

### Composant de base

Le composant Menu latéral permet aux utilisateurs de naviguer entre les différentes pages d'une rubrique ou d'un même thème.

Sa structure est conçue pour s'adapter aux écrans mobiles et comprend les éléments suivants :

```html
<nav class="fr-sidemenu" aria-labelledby="fr-sidemenu-title">
  <div class="fr-sidemenu__inner">
    <button class="fr-sidemenu__btn" aria-controls="fr-sidemenu-wrapper" aria-expanded="false">
      Dans cette rubrique
    </button>
    <div class="fr-collapse" id="fr-sidemenu-wrapper">
      <div class="fr-sidemenu__title" id="fr-sidemenu-title">Titre de rubrique</div>
      <ul class="fr-sidemenu__list">
        <li class="fr-sidemenu__item fr-sidemenu__item--active">
          <a class="fr-sidemenu__link" href="#" target="_self" aria-current="page">
            Accès direct
          </a>
        </li>
        <li class="fr-sidemenu__item">
          <a class="fr-sidemenu__link" href="#" target="_self">
            Accès direct
          </a>
        </li>
        <li class="fr-sidemenu__item">
          <a class="fr-sidemenu__link" href="#" target="_self">
            Accès direct
          </a>
        </li>
      </ul>
    </div>
  </div>
</nav>
```

### Éléments constitutifs

1. **Conteneur principal** (`<nav>`) : Élément HTML `<nav>` défini par la classe `fr-sidemenu`
   - Dispose d'un attribut `aria-labelledby` dont la valeur correspond à l'attribut `id` du titre du menu latéral

2. **Conteneur intérieur** (`<div>`) : Élément HTML `<div>` défini par la classe `fr-sidemenu__inner`

3. **Bouton d'ouverture mobile** (`<button>`) : Élément HTML `<button>` de type `button` défini par la classe `fr-sidemenu__btn` (affiché uniquement en mobile)
   - Le libellé du bouton indique l'action d'ouverture du menu latéral en vue mobile
   - Dispose d'un attribut `aria-expanded` [true|false] définissant si le bloc est ouvert ou fermé
   - Lié au bloc refermable via l'attribut `aria-controls`

4. **Bloc refermable** (`<div>`) : Élément HTML `<div>` défini par la classe `fr-collapse`
   - Dispose d'un attribut `id` obligatoire pour être lié au bouton d'ouverture
   - Contient le titre et la liste de liens

5. **Titre** (`<div>`) : Élément HTML `<div>` défini par la classe `fr-sidemenu__title` (optionnel)

6. **Liste de liens** (`<ul>`) : Élément HTML `<ul>` défini par la classe `fr-sidemenu__list`
   - Chaque élément `<li>` est défini par la classe `fr-sidemenu__item`
   - Les liens `<a>` sont définis par la classe `fr-sidemenu__link`
   - L'élément actif dispose de la classe `fr-sidemenu__item--active`
   - Le lien actif dispose d'un attribut `aria-current="page"`

---

## Sous-sections (multi-niveaux)

Le menu latéral peut contenir jusqu'à trois niveaux d'arborescence et permettent d'afficher les niveaux 1, 2 et 3 imbriqués d'une rubrique.

### Structure des sous-sections

Le conteneur d'une sous-section est un élément de la liste de liens `<li>` défini par la classe `fr-sidemenu__item` contenant :

- **Bouton d'ouverture** : Élément HTML `<button>` de type `button` défini par la classe `fr-sidemenu__btn`
  - Le libellé du bouton indique le nom de la sous-section
  - Attribut `aria-expanded` [true|false] définissant l'état d'ouverture
  - Attribut `aria-controls` lié au bloc refermable
  - Attribut `aria-current` [true|false] définissant si le bouton est actif

- **Bloc refermable** : Élément HTML `<div>` défini par la classe `fr-collapse`
  - Attribut `id` obligatoire pour être lié au bouton
  - Contient une liste de liens pouvant contenir un troisième niveau

### Exemple de structure avec sous-sections

```html
<nav class="fr-sidemenu" role="navigation" aria-labelledby="sidemenu-title">
  <div class="fr-sidemenu__inner">
    <button aria-expanded="false" aria-controls="sidemenu" type="button" class="fr-sidemenu__btn">
      Dans cette rubrique
    </button>
    <div class="fr-collapse" id="sidemenu">
      <p class="fr-sidemenu__title" id="sidemenu-title">Titre de rubrique</p>
      <ul class="fr-sidemenu__list">
        <li class="fr-sidemenu__item">
          <button aria-expanded="true" aria-controls="sidemenu-submenu-level-02" aria-current="true" type="button" class="fr-sidemenu__btn">
            Entrée menu active
          </button>
          <div class="fr-collapse" id="sidemenu-submenu-level-02">
            <ul class="fr-sidemenu__list">
              <li class="fr-sidemenu__item">
                <a href="#" class="fr-sidemenu__link">Accès direct niveau 2</a>
              </li>
              <li class="fr-sidemenu__item">
                <button aria-expanded="true" aria-controls="sidemenu-submenu-level-03" aria-current="true" type="button" class="fr-sidemenu__btn">
                  Entrée menu active
                </button>
                <div class="fr-collapse" id="sidemenu-submenu-level-03">
                  <ul class="fr-sidemenu__list">
                    <li class="fr-sidemenu__item">
                      <a href="#" class="fr-sidemenu__link">Accès direct niveau 3</a>
                    </li>
                    <li class="fr-sidemenu__item">
                      <a aria-current="page" href="#" class="fr-sidemenu__link">Accès direct niveau 3</a>
                    </li>
                  </ul>
                </div>
              </li>
            </ul>
          </div>
        </li>
        <li class="fr-sidemenu__item">
          <a href="#" class="fr-sidemenu__link">Accès direct</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
```

---

## CSS

### Installation du CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

Il est possible d'importer les fichiers CSS avec un niveau de granularité adapté à vos besoins. Voir le découpage des fichiers CSS du DSFR dans la documentation dédiée.

#### Dépendances CSS

| Dépendance | Obligatoire |
|------------|-------------|
| Core | ✅ Oui |
| Sidemenu | ✅ Oui |

#### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/sidemenu/sidemenu.min.css" rel="stylesheet">
```

---

## Variantes

### Variante de menu latéral fixe

Le menu latéral peut s'afficher de manière fixe sur votre page, afin de rester visible tout au long de la navigation de l'utilisateur sur la page ouverte avec l'utilisation de la classe `fr-sidemenu--sticky`.

```html
<nav class="fr-sidemenu fr-sidemenu--sticky" role="navigation" aria-labelledby="sidemenu-sticky-title">
    <!-- Contenu du menu latéral fixe -->
</nav>
```

### Variante de menu latéral fixe sur 100% de la hauteur

Le menu latéral peut s'afficher de manière fixe sur 100% de la hauteur de votre page avec l'utilisation de la classe `fr-sidemenu--sticky-full-height`.

```html
<nav class="fr-sidemenu fr-sidemenu--sticky-full-height" role="navigation" aria-labelledby="sidemenu-sticky-full-height-title">
    <!-- Contenu du menu latéral fixe, affiché sur 100% de la hauteur de page -->
</nav>
```

### Variante de menu latéral à droite de la page

Le menu latéral peut être placé à droite de la page avec l'utilisation de la classe `fr-sidemenu--right` afin que la bordure se positionne à gauche du menu. On peut également le rendre fixe avec l'utilisation de la classe `fr-sidemenu--sticky`.

```html
<nav class="fr-sidemenu fr-sidemenu--right" role="navigation" aria-labelledby="sidemenu-right-title">
    <!-- Contenu du menu latéral à droite de la page -->
</nav>
```

---

## JavaScript

### Installation du JavaScript

Pour fonctionner le composant menu latéral nécessite l'utilisation de JavaScript. Chaque composant utilisant JavaScript possède un fichier JS spécifique et requiert le fichier JS du core.

Il est donc nécessaire d'importer ces fichiers à la fin de la page (avant `</body>`) :

```html
<script type="module" src="dist/core/core.module.min.js"></script>
<script type="module" src="dist/component/sidemenu/sidemenu.module.min.js"></script>
```

**NB:** Il est aussi possible d'importer le JS global du DSFR `dsfr.module.min.js`

#### Support Internet Explorer 11 (legacy)

Pour fonctionner sur Internet Explorer 11, un fichier legacy, en version nomodule ES5, peut aussi être importé :

```html
<script type="text/javascript" nomodule src="dist/legacy/legacy.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/core/core.nomodule.min.js"></script>
<script type="text/javascript" nomodule src="dist/component/sidemenu/sidemenu.nomodule.min.js"></script>
```

Une fois le JavaScript chargé, le composant fonctionne automatiquement.

### Instances

Sur le menu latéral, les éléments suivants sont instanciés :

- La liste de liens, via la classe : `fr-sidemenu__list`
- Les éléments de la liste, via la classe : `fr-sidemenu__item`
- Le bouton d'ouverture, via la classe : `fr-sidemenu__btn`
- La sous-section, via la classe : `fr-collapse`

Une fois chargé, le JS ajoute un attribut `data-fr-js-NOM_INSTANCE="true"` sur chacun des éléments instanciés.

---

## API JavaScript

Il est possible d'interagir avec les instances du composant en JavaScript via une API.

Cette API est disponible depuis la méthode `window.dsfr(instance)` du core.

**Exemple :**

```javascript
const elem = document.getElementById('ID_SOUS_SECTION');
dsfr(elem).collapse.disclose();
```

L'ensemble des propriétés et méthodes disponibles sont définies ci-après :

### sidemenuList

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `current` | property | Retourne l'API de la sous-section ouverte. Si aucune sous-section n'est ouverte, ou si plusieurs sous-sections sont ouvertes, renvoie null. | object \| null | `dsfr(elem).sidemenuList.current` |
| `hasFocus` | property | Renvoie vrai si le focus est sur un des éléments du groupe | Boolean | `dsfr(elem).sidemenuList.hasFocus` |
| `index` | property | Retourne ou modifie l'index de la sous-section courante. Si aucune sous-section n'est ouverte, l'index vaut 0. | Number | `dsfr(elem).sidemenuList.index`<br>`dsfr(elem).sidemenuList.index = 2` |
| `isGrouped` | property | Défini si les sous-sections du groupe sont liées entre elles ou non. Si true, lorsqu'une sous-section est ouverte les autres se referment. Si false, il est possible d'en ouvrir plusieurs. Si l'attribut n'est pas défini les sous-sections sont groupées par défaut. | Boolean | `dsfr(elem).sidemenuList.isGrouped`<br>`dsfr(elem).sidemenuList.isGrouped = true` |
| `length` | property | Retourne le nombre de sous-sections dans le groupe | Number | `dsfr(elem).sidemenuList.length` |
| `members` | property | Renvoie un tableau d'objets correspondant aux sous-sections du groupe | Array | `dsfr(elem).sidemenuList.members` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).sidemenuList.node` |

### sidemenuItem

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `isEnabled` | property | Défini si le fonctionnement du menu latéral est activé ou non | Boolean | `dsfr(elem).sidemenuItem.isEnabled = false` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).sidemenuItem.node` |

### collapseButton

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `focus` | function | Replace le focus sur le bouton | Boolean | `dsfr(elem).collapseButton.focus()` |
| `isEnabled` | property | Défini si le fonctionnement du bouton du menu latéral est activé ou non | Boolean | `dsfr(elem).collapseButton.isEnabled = false` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).collapseButton.node` |

### collapse

| Propriété/Méthode | Type | Description | Retour | Exemple |
|-------------------|------|-------------|--------|---------|
| `conceal` | function | Ferme la sous-section | none | `dsfr(elem).collapse.conceal()` |
| `disclose` | function | Ouvre la sous-section | none | `dsfr(elem).collapse.disclose()` |
| `isDisclosed` | property | Retourne vrai si la sous-section est ouverte | Boolean | `dsfr(elem).collapse.isDisclosed` |
| `isEnabled` | property | Défini si le fonctionnement du menu latéral est activé ou non | Boolean | `dsfr(elem).collapse.isEnabled = false` |
| `group` | property | Retourne l'API du groupe, ou null s'il n'y a pas de groupe | object \| null | `dsfr(elem).collapse.group` |
| `buttons` | property | Retourne un tableau de boutons d'ouverture de la sous-section | Array | `dsfr(elem).collapse.buttons` |
| `focus` | function | Replace le focus sur le bouton de la sous-section | Boolean | `dsfr(elem).collapse.focus()` |
| `parent` | property | Retourne l'instance du DSFR parent, ici le menu latéral | object \| null | `dsfr(elem).parent` |
| `children` | property | Renvoie un tableau d'instances enfants | Array | `dsfr(elem).children` |
| `node` | property | Renvoie le noeud HTML de l'élément | DOMElement | `dsfr(elem).collapse.node` |

---

## Événements

Le Système de Design fournit des événements personnalisés pour les actions uniques de la part de certains composants réactifs.

Dans la version mobile du menu latéral et sur chaque menu déroulant du menu latéral, les événements suivants sont disponibles :

| Événement | Action | Élément | Attribut |
|-----------|--------|---------|----------|
| `dsfr.conceal` | Fermeture de l'élément | Collapse | `data-fr-js-collapse` |
| `dsfr.disclose` | Ouverture de l'élément | Collapse | `data-fr-js-collapse` |
| `dsfr.click` | Click sur le bouton d'ouverture | CollapseButton | `data-fr-js-collapse-button` |

### Exemple d'utilisation des événements

```javascript
// Écouter l'ouverture d'une sous-section
document.addEventListener('dsfr.disclose', function(e) {
  if (e.target.matches('[data-fr-js-collapse]')) {
    console.log('Sous-section ouverte:', e.target);
  }
});

// Écouter la fermeture d'une sous-section
document.addEventListener('dsfr.conceal', function(e) {
  if (e.target.matches('[data-fr-js-collapse]')) {
    console.log('Sous-section fermée:', e.target);
  }
});
```

---

## Bonnes pratiques

### Accessibilité

- Toujours utiliser l'attribut `aria-labelledby` sur le `<nav>` pour lier le menu à son titre
- Utiliser `aria-current="page"` sur le lien actif pour indiquer la page courante
- Utiliser `aria-expanded` sur les boutons pour indiquer l'état ouvert/fermé
- Assurer une navigation au clavier fluide (Tab, Entrée, Espace)

### Performance

- Limiter le nombre de niveaux à 3 maximum pour éviter une complexité excessive
- Utiliser la variante fixe (`fr-sidemenu--sticky`) avec parcimonie, uniquement lorsque nécessaire

### Ergonomie

- Toujours indiquer visuellement la page active dans le menu
- Maintenir la cohérence des libellés entre le menu et les titres de page
- Éviter les menus latéraux trop longs (> 20 éléments au niveau 1)

---

## Références

- **Documentation DSFR** : https://www.systeme-de-design.gouv.fr/composants/menu-lateral
- **GitHub** : https://github.com/GouvernementFR/dsfr
- **API JavaScript** : https://www.systeme-de-design.gouv.fr/utilisation-et-configuration/developpeurs/prise-en-main
