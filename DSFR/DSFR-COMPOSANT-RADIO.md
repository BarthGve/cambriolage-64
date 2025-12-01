# DSFR - Composant Bouton Radio

> Documentation du composant Bouton Radio (Radio Button) du Design System de l'État Français (DSFR)

**Source officielle :** https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/bouton-radio

---

## Table des matières

1. [Introduction](#introduction)
2. [Structure HTML](#structure-html)
3. [Groupe de radios](#groupe-de-radios)
4. [Bouton radio riche](#bouton-radio-riche)
5. [Installation CSS](#installation-css)
6. [Variantes](#variantes)
7. [Exemples complets](#exemples-complets)
8. [Accessibilité](#accessibilité)
9. [Bonnes pratiques](#bonnes-pratiques)

---

## Introduction

Le composant **Bouton radio** (Radio) est un élément interactif permettant de **sélectionner une seule option parmi un groupe d'options**. Il n'est jamais utilisé seul, mais toujours dans un ensemble de radios.

### Caractéristiques principales

- **Sélection exclusive** : Un seul choix possible dans le groupe
- **Toujours en groupe** : Minimum 2 options, sinon utiliser une case à cocher
- **Structuré** : Utilisation obligatoire de `<fieldset>` et `<legend>`
- **Accessible** : Support ARIA et navigation clavier

### Cas d'usage

✅ **Utiliser quand :**
- L'utilisateur doit choisir **une seule option** parmi plusieurs
- Les options sont **mutuellement exclusives**
- Il y a entre 2 et 7 options (au-delà, privilégier un Select)

❌ **Ne pas utiliser quand :**
- Plusieurs choix sont possibles → Utiliser des **cases à cocher**
- Une seule option existe → Utiliser une **case à cocher** unique
- Plus de 7 options → Utiliser un **Select**

---

## Structure HTML

### Radio simple

Un radio individuel se compose de :
1. Container `<div>` avec classe `fr-radio-group`
2. Input `<input type="radio">` avec classe `fr-radio`
3. Label `<label>` avec classe `fr-label`
4. Description optionnelle dans le label (`fr-hint-text`)

```html
<div class="fr-radio-group">
    <input id="radio" type="radio" name="radio" aria-describedby="radio-messages">
    <label class="fr-label" for="radio">
        Libellé bouton radio
        <span class="fr-hint-text">Description optionnelle</span>
    </label>
</div>
```

### Éléments clés

| Élément | Classe | Obligatoire | Rôle |
|---------|--------|-------------|------|
| `<div>` | `fr-radio-group` | ✅ Oui | Container du radio |
| `<input type="radio">` | `fr-radio` | ✅ Oui | Champ interactif |
| `<label>` | `fr-label` | ✅ Oui | Libellé associé |
| `<span>` | `fr-hint-text` | ❌ Non | Description additionnelle |

### Attributs importants

```html
<input
    id="radio-unique-id"        <!-- ID unique pour association avec label -->
    type="radio"                 <!-- Type radio obligatoire -->
    name="radio-group-name"      <!-- Même name pour tous les radios du groupe -->
    value="valeur"               <!-- Valeur envoyée au formulaire -->
    aria-describedby="msg-id"    <!-- Lien vers messages d'erreur/succès -->
    checked                      <!-- Optionnel : radio présélectionné -->
    disabled                     <!-- Optionnel : radio désactivé -->
>
```

---

## Groupe de radios

Un bouton radio seul ne fait pas sens. Il doit **toujours être dans un ensemble** structuré avec `<fieldset>` et `<legend>`.

### Structure complète

```html
<fieldset class="fr-fieldset" aria-labelledby="radio-legend radio-messages">
    <!-- Légende du groupe -->
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="radio-legend">
        Légende pour l'ensemble des éléments
        <span class="fr-hint-text">Description optionnelle du groupe</span>
    </legend>

    <!-- Radio 1 -->
    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="1" type="radio" id="radio-1" name="radio">
            <label class="fr-label" for="radio-1">
                Libellé bouton radio 1
            </label>
        </div>
    </div>

    <!-- Radio 2 -->
    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="2" type="radio" id="radio-2" name="radio">
            <label class="fr-label" for="radio-2">
                Libellé bouton radio 2
            </label>
        </div>
    </div>

    <!-- Radio 3 -->
    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="3" type="radio" id="radio-3" name="radio">
            <label class="fr-label" for="radio-3">
                Libellé bouton radio 3
            </label>
        </div>
    </div>

    <!-- Zone de messages (erreur/succès) -->
    <div class="fr-messages-group" id="radio-messages" aria-live="polite">
    </div>
</fieldset>
```

### Classes du groupe

| Élément | Classes | Rôle |
|---------|---------|------|
| `<fieldset>` | `fr-fieldset` | Container du groupe |
| `<legend>` | `fr-fieldset__legend` `fr-fieldset__legend--regular` | Titre du groupe (graisse standard) |
| `<div>` wrapper | `fr-fieldset__element` | Wrapper de chaque radio |
| `<div>` messages | `fr-messages-group` | Zone de messages d'état |

### Radios en ligne

Pour afficher les radios **horizontalement** (sur une même ligne) :

```html
<div class="fr-fieldset__element fr-fieldset__element--inline">
    <div class="fr-radio-group">
        <!-- ... -->
    </div>
</div>
```

**Classe à ajouter :** `fr-fieldset__element--inline`

---

## Bouton radio riche

Le composant propose une **variante enrichie** avec bordure et pictogramme optionnel.

### Structure du radio riche

```html
<div class="fr-radio-group fr-radio-rich">
    <input value="1" type="radio" id="radio-rich-1" name="radio-rich">
    <label class="fr-label" for="radio-rich-1">
        Libellé bouton radio
        <span class="fr-hint-text">Description optionnelle</span>
    </label>

    <!-- Pictogramme optionnel -->
    <div class="fr-radio-rich__pictogram">
        <svg aria-hidden="true" class="fr-artwork" viewBox="0 0 80 80" width="80px" height="80px">
            <use class="fr-artwork-decorative" href="path/to/pictogram.svg#artwork-decorative"></use>
            <use class="fr-artwork-minor" href="path/to/pictogram.svg#artwork-minor"></use>
            <use class="fr-artwork-major" href="path/to/pictogram.svg#artwork-major"></use>
        </svg>
    </div>
</div>
```

### Caractéristiques du radio riche

- **Classe principale :** `fr-radio-rich` (à ajouter à `fr-radio-group`)
- **Bordure visible** autour de l'option
- **Pictogramme optionnel** dans `<div class="fr-radio-rich__pictogram">`
- **SVG en 3 parties :** decorative, minor, major (artwork)

### Accentuation du pictogramme

Pour colorer la partie mineure du pictogramme :

```html
<svg aria-hidden="true" class="fr-artwork fr-artwork--green-emeraude" ...>
```

**Classes d'accent disponibles :**
- `fr-artwork--green-emeraude`
- `fr-artwork--blue-france`
- `fr-artwork--orange-terre-battue`
- Voir la documentation des pictogrammes pour la liste complète

### Radio riche sans pictogramme

Il est possible d'utiliser la variante riche **sans pictogramme** :

```html
<div class="fr-radio-group fr-radio-rich">
    <input value="1" type="radio" id="radio-rich-1" name="radio-rich">
    <label class="fr-label" for="radio-rich-1">
        Libellé bouton radio
    </label>
    <!-- Pas de div fr-radio-rich__pictogram -->
</div>
```

---

## Installation CSS

### Dépendances CSS

| Fichier CSS | Obligatoire | Rôle |
|-------------|-------------|------|
| `core/core.min.css` | ✅ Oui | Styles de base DSFR |
| `component/radio/radio.min.css` | ✅ Oui | Styles du composant radio |

### Import dans le HTML

```html
<head>
    <!-- Core DSFR (obligatoire) -->
    <link href="dist/core/core.min.css" rel="stylesheet">

    <!-- Composant Radio (obligatoire) -->
    <link href="dist/component/radio/radio.min.css" rel="stylesheet">
</head>
```

### Via CDN (jsDelivr)

```html
<head>
    <link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/core/core.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/component/radio/radio.min.css" rel="stylesheet">
</head>
```

### JavaScript

⚠️ Le composant Bouton radio **ne nécessite pas de JavaScript** pour son fonctionnement de base.

---

## Variantes

### Variantes de taille

Le composant propose 2 tailles :

| Taille | Classe | Description |
|--------|--------|-------------|
| **MD (défaut)** | *Aucune* | Taille standard (par défaut) |
| **SM (Small)** | `fr-radio-group--sm` | Taille réduite |

**Application :**

```html
<!-- Taille MD (défaut) -->
<div class="fr-radio-group">
    <!-- ... -->
</div>

<!-- Taille SM -->
<div class="fr-radio-group fr-radio-group--sm">
    <!-- ... -->
</div>
```

### Variantes d'états

Les états s'appliquent **au niveau du groupe** (`<fieldset>`), pas sur les radios individuels.

#### 1. État d'erreur

**Classe :** `fr-fieldset--error`

```html
<fieldset class="fr-fieldset fr-fieldset--error" aria-labelledby="radio-legend radio-messages">
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="radio-legend">
        Légende pour l'ensemble des éléments en erreur
    </legend>

    <!-- Radios... -->

    <div class="fr-messages-group" id="radio-messages" aria-live="polite">
        <p class="fr-message fr-message--error" id="radio-message-error">
            Texte d'erreur : Veuillez sélectionner une option
        </p>
    </div>
</fieldset>
```

**Caractéristiques :**
- Bordure rouge autour du groupe
- Message d'erreur obligatoire dans `fr-messages-group`
- Lié via `aria-describedby` et `aria-labelledby`

#### 2. État de succès

**Classe :** `fr-fieldset--valid`

```html
<fieldset class="fr-fieldset fr-fieldset--valid" aria-labelledby="radio-legend radio-messages">
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="radio-legend">
        Légende pour l'ensemble des éléments en succès
    </legend>

    <!-- Radios... -->

    <div class="fr-messages-group" id="radio-messages" aria-live="polite">
        <p class="fr-message fr-message--valid" id="radio-message-valid">
            Texte de succès : Choix enregistré
        </p>
    </div>
</fieldset>
```

**Caractéristiques :**
- Bordure verte autour du groupe
- Message de succès obligatoire dans `fr-messages-group`

#### 3. État désactivé

**Attribut :** `disabled` sur le `<fieldset>`

```html
<fieldset class="fr-fieldset" disabled aria-labelledby="radio-legend radio-messages">
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="radio-legend">
        Légende pour l'ensemble des éléments désactivés
    </legend>

    <!-- Radios... -->

    <div class="fr-messages-group" id="radio-messages" aria-live="polite">
    </div>
</fieldset>
```

**Caractéristiques :**
- Tous les radios du groupe sont désactivés
- Apparence grisée
- Non interactifs

**Alternative :** Désactiver un radio individuel :

```html
<input type="radio" id="radio-1" name="radio" disabled>
```

### Tableau récapitulatif des états

| État | Classe/Attribut | Niveau | Message requis |
|------|-----------------|--------|----------------|
| Normal | *Aucun* | Groupe | Non |
| Erreur | `fr-fieldset--error` | Groupe | ✅ Oui |
| Succès | `fr-fieldset--valid` | Groupe | ✅ Oui |
| Désactivé | `disabled` | Groupe ou Radio | Non |

---

## Exemples complets

### Exemple 1 : Groupe de radios simple

```html
<fieldset class="fr-fieldset" aria-labelledby="classification-legend">
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="classification-legend">
        Classification du système IA
        <span class="fr-hint-text">Sélectionnez le niveau de risque identifié</span>
    </legend>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="minimal" type="radio" id="risk-minimal" name="risk-level" checked>
            <label class="fr-label" for="risk-minimal">
                Risque minimal
                <span class="fr-hint-text">Aucune obligation spécifique</span>
            </label>
        </div>
    </div>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="limited" type="radio" id="risk-limited" name="risk-level">
            <label class="fr-label" for="risk-limited">
                Risque limité
                <span class="fr-hint-text">Obligations de transparence</span>
            </label>
        </div>
    </div>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="high" type="radio" id="risk-high" name="risk-level">
            <label class="fr-label" for="risk-high">
                Haut risque
                <span class="fr-hint-text">Obligations renforcées (AIDF, marquage CE)</span>
            </label>
        </div>
    </div>

    <div class="fr-messages-group" id="classification-messages" aria-live="polite">
    </div>
</fieldset>
```

### Exemple 2 : Radios riches avec pictogrammes

```html
<fieldset class="fr-fieldset" aria-labelledby="domain-legend">
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="domain-legend">
        Domaine d'application
    </legend>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group fr-radio-rich">
            <input value="health" type="radio" id="domain-health" name="domain">
            <label class="fr-label" for="domain-health">
                Santé
                <span class="fr-hint-text">Diagnostic médical, dispositifs médicaux</span>
            </label>
            <div class="fr-radio-rich__pictogram">
                <svg aria-hidden="true" class="fr-artwork fr-artwork--green-emeraude" viewBox="0 0 80 80" width="80px" height="80px">
                    <use class="fr-artwork-decorative" href="dist/artwork/pictograms/health/health.svg#artwork-decorative"></use>
                    <use class="fr-artwork-minor" href="dist/artwork/pictograms/health/health.svg#artwork-minor"></use>
                    <use class="fr-artwork-major" href="dist/artwork/pictograms/health/health.svg#artwork-major"></use>
                </svg>
            </div>
        </div>
    </div>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group fr-radio-rich">
            <input value="education" type="radio" id="domain-education" name="domain">
            <label class="fr-label" for="domain-education">
                Éducation
                <span class="fr-hint-text">Formation, évaluation des élèves</span>
            </label>
            <div class="fr-radio-rich__pictogram">
                <svg aria-hidden="true" class="fr-artwork fr-artwork--blue-france" viewBox="0 0 80 80" width="80px" height="80px">
                    <use class="fr-artwork-decorative" href="dist/artwork/pictograms/education/education.svg#artwork-decorative"></use>
                    <use class="fr-artwork-minor" href="dist/artwork/pictograms/education/education.svg#artwork-minor"></use>
                    <use class="fr-artwork-major" href="dist/artwork/pictograms/education/education.svg#artwork-major"></use>
                </svg>
            </div>
        </div>
    </div>

    <div class="fr-messages-group" id="domain-messages" aria-live="polite">
    </div>
</fieldset>
```

### Exemple 3 : Radios en ligne (inline)

```html
<fieldset class="fr-fieldset" aria-labelledby="choice-legend">
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="choice-legend">
        Avez-vous réalisé une AIDF ?
    </legend>

    <div class="fr-fieldset__element fr-fieldset__element--inline">
        <div class="fr-radio-group">
            <input value="yes" type="radio" id="aidf-yes" name="aidf">
            <label class="fr-label" for="aidf-yes">Oui</label>
        </div>
    </div>

    <div class="fr-fieldset__element fr-fieldset__element--inline">
        <div class="fr-radio-group">
            <input value="no" type="radio" id="aidf-no" name="aidf">
            <label class="fr-label" for="aidf-no">Non</label>
        </div>
    </div>

    <div class="fr-fieldset__element fr-fieldset__element--inline">
        <div class="fr-radio-group">
            <input value="in-progress" type="radio" id="aidf-progress" name="aidf">
            <label class="fr-label" for="aidf-progress">En cours</label>
        </div>
    </div>

    <div class="fr-messages-group" id="aidf-messages" aria-live="polite">
    </div>
</fieldset>
```

### Exemple 4 : Groupe avec erreur

```html
<fieldset class="fr-fieldset fr-fieldset--error" aria-labelledby="required-legend required-messages">
    <legend class="fr-fieldset__legend fr-fieldset__legend--regular" id="required-legend">
        Type de système IA <span class="fr-hint-text">(obligatoire)</span>
    </legend>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="ml" type="radio" id="type-ml" name="ai-type">
            <label class="fr-label" for="type-ml">Machine Learning</label>
        </div>
    </div>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="expert" type="radio" id="type-expert" name="ai-type">
            <label class="fr-label" for="type-expert">Système expert</label>
        </div>
    </div>

    <div class="fr-fieldset__element">
        <div class="fr-radio-group">
            <input value="nlp" type="radio" id="type-nlp" name="ai-type">
            <label class="fr-label" for="type-nlp">Traitement du langage naturel</label>
        </div>
    </div>

    <div class="fr-messages-group" id="required-messages" aria-live="assertive">
        <p class="fr-message fr-message--error">
            Ce champ est obligatoire. Veuillez sélectionner un type de système IA.
        </p>
    </div>
</fieldset>
```

---

## Accessibilité

### Attributs ARIA essentiels

| Attribut | Élément | Rôle |
|----------|---------|------|
| `aria-labelledby` | `<fieldset>` | Lie le fieldset à sa légende et aux messages |
| `aria-describedby` | `<input>` | Lie le radio aux messages d'erreur/succès |
| `aria-live="polite"` | `fr-messages-group` | Annonce les messages dynamiques |
| `aria-live="assertive"` | `fr-messages-group` | Annonce immédiatement (erreurs critiques) |
| `aria-hidden="true"` | Pictogrammes SVG | Cache les décorations aux lecteurs d'écran |

### Structure accessible

```html
<fieldset
    class="fr-fieldset"
    aria-labelledby="legend-id messages-id"
    role="group"
>
    <legend id="legend-id">Titre du groupe</legend>

    <!-- Radios -->

    <div class="fr-messages-group" id="messages-id" aria-live="polite">
        <!-- Messages -->
    </div>
</fieldset>
```

### Navigation clavier

| Touche | Action |
|--------|--------|
| `Tab` | Naviguer vers/depuis le groupe de radios |
| `↑` / `↓` | Naviguer entre les radios du groupe |
| `←` / `→` | Naviguer entre les radios du groupe |
| `Espace` | Sélectionner le radio focalisé |

### Bonnes pratiques d'accessibilité

✅ **À faire :**
- Toujours utiliser `<fieldset>` et `<legend>` pour les groupes
- Lier les messages avec `aria-labelledby` et `aria-describedby`
- Utiliser `aria-live` pour les messages dynamiques
- Fournir des labels explicites et descriptifs
- Utiliser `fr-hint-text` pour les descriptions additionnelles

❌ **À éviter :**
- Ne pas utiliser de radios isolés
- Ne pas omettre le `<label>` associé
- Ne pas utiliser uniquement des couleurs pour indiquer l'état
- Ne pas désactiver la navigation clavier

---

## Bonnes pratiques

### Quand utiliser les radios

✅ **Utiliser des radios pour :**
- Choix **exclusif** parmi 2 à 7 options
- Options **visibles en permanence** (pas de menu déroulant)
- Décisions **binaires** étendues (ex: Oui/Non/Ne sait pas)

❌ **Ne pas utiliser pour :**
- Plus de 7 options → Préférer un `<select>`
- Choix multiples possibles → Utiliser des cases à cocher
- Un seul choix logique → Utiliser une case à cocher unique

### Rédaction des labels

**Labels clairs et concis :**
```html
<!-- ✅ BON -->
<label class="fr-label" for="risk-high">
    Haut risque
    <span class="fr-hint-text">Systèmes critiques soumis au marquage CE</span>
</label>

<!-- ❌ MAUVAIS -->
<label class="fr-label" for="risk-high">
    Si votre système IA présente des risques élevés pour les droits fondamentaux...
</label>
```

**Règles :**
- Label principal court (1-5 mots)
- Description détaillée dans `fr-hint-text`
- Vocabulaire métier compréhensible
- Éviter les négations (préférer "Oui/Non" à "Pas oui/Pas non")

### Gestion des états

**Messages d'erreur explicites :**
```html
<!-- ✅ BON -->
<p class="fr-message fr-message--error">
    Ce champ est obligatoire. Veuillez sélectionner une classification.
</p>

<!-- ❌ MAUVAIS -->
<p class="fr-message fr-message--error">
    Erreur
</p>
```

**Ordre de priorité :**
1. Erreur (bloquante)
2. Succès (validation)
3. Normal (aucun état)

### Performance

- Pas de JavaScript requis → Performance optimale
- CSS modulaire → Charger uniquement le nécessaire
- Pictogrammes SVG → Vecteurs légers et scalables

### Responsive

Les radios DSFR sont **responsive par défaut** :
- Adaptation automatique sur mobile
- Touch-friendly (zones de clic élargies)
- Utiliser `fr-fieldset__element--inline` avec précaution (peut casser sur petits écrans)

---

## Ressources

### Documentation officielle

- **Composant Radio** : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/bouton-radio
- **Pictogrammes** : https://www.systeme-de-design.gouv.fr/elements-d-interface/fondamentaux-de-l-identite-de-l-etat/les-pictogrammes
- **Messages** : https://www.systeme-de-design.gouv.fr/composants-et-modeles/composants/message-d-alerte

### Fichiers DSFR associés

- CSS : `dist/component/radio/radio.min.css`
- Core : `dist/core/core.min.css`
- Pictogrammes : `dist/artwork/pictograms/`

### Autres composants complémentaires

- **Case à cocher** : Pour sélections multiples
- **Select** : Pour plus de 7 options
- **Champ de saisie** : Pour valeurs libres

---

## Changelog

**Version 1.0** - 2025-10-20
- Documentation initiale complète
- Exemples adaptés au contexte AI Act
- Bonnes pratiques d'accessibilité

---

**Note :** Cette documentation est basée sur le DSFR v1.11+. Vérifier la version utilisée dans votre projet pour compatibilité.
