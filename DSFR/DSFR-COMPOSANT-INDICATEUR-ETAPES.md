# Indicateur d'étapes (Stepper)

L'indicateur d'étapes est un élément éditorial permettant d'accompagner l'usager au sein d'un formulaire ou une démarche en plusieurs étapes.

## Structure du composant

Le composant Indicateur d'étapes est un élément permettant de visualiser les étapes d'un processus.

Sa structure est la suivante :

### Conteneur principal

Le conteneur du stepper est un élément HTML `<div>` défini par la classe `fr-stepper`.

### Titre de l'étape en cours

Le titre de l'étape en cours, obligatoire, est contenu dans un niveau d'entête `<hx>`, variable en fonction de sa hiérarchie dans la page (par défaut h2), et possède la classe `fr-stepper__title`.

Le numéro de l'étape et le nombre d'étapes total, obligatoires, sont précisés à l'intérieur du titre dans un élément HTML `<span>` défini par la classe `fr-stepper__state`.

### Barre de progression

La barre de progression, obligatoire, un élément HTML `<div>` défini par la classe `fr-stepper__steps`.

La balise possède des attributs `data-fr-steps` et `data-fr-current-step` pour définir le nombre total d'étapes et l'étape actuelle.

### Détails de l'étape

Les détails de l'étape sont un élément HTML `<p>` défini par la classe `fr-stepper__details` et contiennent :

- Le titre de l'étape suivante, obligatoire, dans un élément HTML `<span>`.

## Exemple de structure HTML

```html
<div class="fr-stepper">
    <h2 class="fr-stepper__title">
        Titre de l'étape en cours
        <span class="fr-stepper__state">Étape 1 sur 3</span>
    </h2>
    <div class="fr-stepper__steps" data-fr-current-step="1" data-fr-steps="3"></div>
    <p class="fr-stepper__details">
        <span class="fr-text--bold">Étape suivante :</span> Titre de la prochaine étape
    </p>
</div>
```

## CSS

### Installation du CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés. L'import doit se faire avant le contenu de la page dans la partie `<head>`, et de préférence avec les fichiers minifiés, car plus légers.

Il est possible d'importer les fichiers CSS avec un niveau de granularité adapté à vos besoins. Voir le découpage des fichiers CSS du DSFR dans la documentation dédiée.

#### Dépendances CSS

| Dépendance | Obligatoire |
|------------|-------------|
| Core | Oui |
| Stepper | Oui |

#### Exemple d'imports CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/stepper/stepper.min.css" rel="stylesheet">
```

## JavaScript

Le composant Indicateur d'étapes ne nécessite pas l'utilisation de JavaScript pour son fonctionnement de base.
