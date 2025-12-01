# Composant Alerte (Alert) - Documentation Technique DSFR

## Vue d'ensemble

L'**Alerte** est un composant d'indication poussé par l'interface pour relayer une information à l'usager (information, avertissement, erreur, succès).

## Quand utiliser ce composant ?

Intégrer des alertes pour attirer l'attention de l'usager sur une information sans interrompre sa tâche en cours.

Les alertes s'affichent de manière contextuelle dans une page ou un formulaire, suite à une interaction de l'usager (exemple : à la soumission d'un formulaire) ou lors d'événements côté application/système (exemple : au rechargement d'une page).

## Comment utiliser ce composant ?

### Adapter l'alerte à la nature de l'information

**✅ À FAIRE** : Adapter l'alerte à la nature de l'information relayée.

**❌ À NE PAS FAIRE** : Ne pas proposer une variation de l'alerte ne correspondant pas à la nature de l'information relayée.

Choisir la variation de l'alerte adéquate, correspondant à la nature de l'information qu'elle relaie (erreur, succès, information etc.)

### Placer l'alerte correctement

**✅ À FAIRE** : Placer l'alerte de succès en haut de page suite à la soumission d'un formulaire, par exemple.

**❌ À NE PAS FAIRE** : Ne pas placer l'alerte de succès en bas de page suite à la soumission d'un formulaire.

Placer l'alerte en première place du contenu auquel elle est associée (exemple : en haut d'une page, d'un formulaire, d'un container etc.)

### Rendre l'action attendue claire

**✅ À FAIRE** : Préciser à l'usager l'action attendue suite à l'apparition de l'alerte.

**❌ À NE PAS FAIRE** : Ne pas laisser l'usager supposer du problème rencontré. La marche à suivre doit être claire.

Rendre toute action induite suite à l'affichage d'une alerte aussi simple que possible, notamment en détaillant ce qui est attendu de l'usager dans la description.

---

## Structure HTML

### Composant de base

```html
<div class="fr-alert">
  <h3 class="fr-alert__title">Titre de l'alerte</h3>
  <p>Description de l'alerte</p>
  <button title="Masquer le message"
          onclick="const alert = this.parentNode; alert.parentNode.removeChild(alert)"
          type="button"
          class="fr-btn--close fr-btn">
    Masquer le message
  </button>
</div>
```

### Éléments constitutifs

1. **Conteneur principal** : `<div class="fr-alert">`
2. **Titre (facultatif)** : `<hx class="fr-alert__title">` (h3 par défaut, adapter selon hiérarchie)
3. **Description** : `<p>` contenant le message
4. **Bouton fermeture (facultatif)** : `<button type="button" class="fr-btn--close fr-btn">`

---

## Types d'alertes

| Type | Classe | Usage | Couleur |
|------|--------|-------|---------|
| **Info** | `fr-alert--info` | Message informatif | Bleu |
| **Warning** | `fr-alert--warning` | Avertissement | Jaune |
| **Error** | `fr-alert--error` | Erreur | Rouge |
| **Success** | `fr-alert--success` | Succès | Vert |

### Exemple avec type

```html
<div class="fr-alert fr-alert--error">
  <h3 class="fr-alert__title">Erreur critique</h3>
  <p>Une erreur est survenue, veuillez réessayer plus tard.</p>
  <button title="Masquer le message"
          onclick="const alert = this.parentNode; alert.parentNode.removeChild(alert)"
          type="button"
          class="fr-btn--close fr-btn">
    Masquer le message
  </button>
</div>
```

---

## Tailles

| Taille | Classe | Usage |
|--------|--------|-------|
| **Medium (MD)** | *(par défaut)* | Taille normale |
| **Small (SM)** | `fr-alert--sm` | Alerte compacte |

### Exemple taille SM

```html
<div class="fr-alert fr-alert--success fr-alert--sm">
  <h3 class="fr-alert__title">Succès</h3>
  <p>Votre demande a été traitée avec succès.</p>
  <button title="Masquer le message"
          onclick="const alert = this.parentNode; alert.parentNode.removeChild(alert)"
          type="button"
          class="fr-btn--close fr-btn">
    Masquer le message
  </button>
</div>
```

---

## Installation CSS

### Dépendances

| Fichier | Obligatoire | Remarque |
|---------|-------------|----------|
| Core | ✅ Oui | Fondamentaux DSFR |
| Alert | ✅ Oui | Composant alerte |
| Button | ❌ Non | Uniquement pour version refermable |
| Utility | ❌ Non | Uniquement pour icônes custom |

### Import CSS

```html
<link href="dist/core/core.min.css" rel="stylesheet">
<link href="dist/component/alert/alert.min.css" rel="stylesheet">
```

---

## JavaScript

### ⚠️ Gestion de la fermeture

Le DSFR **ne gère pas** la fermeture automatique (trop dépendant de la technologie utilisée). Vous devez implémenter la logique de fermeture.

### Exemple JavaScript vanilla

```javascript
document.querySelector('.fr-alert__close').addEventListener('click', function() {
  this.closest('.fr-alert').remove();
});
```

### Alternative : inline onclick (fourni dans exemples)

```html
<button onclick="const alert = this.parentNode; alert.parentNode.removeChild(alert)"
        type="button"
        class="fr-btn--close fr-btn">
  Masquer le message
</button>
```

---

## Utilisation dans les widgets Grist

### Fonction standardisée (OBLIGATOIRE)

```javascript
function showNotification(message, type = 'success') {
  const container = document.getElementById('notifications-container');
  const notif = document.createElement('div');
  notif.className = `fr-alert fr-alert--${type} fr-alert--sm fr-mb-2w`;
  notif.innerHTML = `<p class="fr-alert__title">${message}</p>`;
  notif.style.animation = 'slideInRight 0.3s ease';
  container.appendChild(notif);

  // Auto-dismiss après 4s
  setTimeout(() => {
    notif.style.animation = 'slideOutRight 0.3s ease';
    setTimeout(() => notif.remove(), 300);
  }, 4000);
}
```

### Types disponibles

```javascript
showNotification('Projet créé avec succès', 'success');
showNotification('Données chargées', 'info');
showNotification('Champ requis manquant', 'warning');
showNotification('Erreur lors de l\'enregistrement', 'error');
```

### Conteneur requis

```html
<div id="notifications-container"
     style="position: fixed; top: 20px; right: 20px; z-index: 9999; max-width: 400px;">
</div>
```

---

## Règles éditoriales

### Titre clair et concis

Choisir un titre d'alerte clair et concis permettant à l'usager de comprendre facilement la situation.

### Description détaillée

Détailler clairement l'information ou le problème ainsi que l'action attendue (si elle existe) à l'usager à l'aide de la description.

### Ton courtois

**✅ À FAIRE** : Employer un ton courtois, l'objectif étant d'accompagner l'usager au sein de son parcours.

**❌ À NE PAS FAIRE** : Ne pas employer un ton laissant suggérer que l'on blâme l'usager pour son erreur.

Arborer un ton courtois, l'objectif étant d'accompagner l'usager et non de le blâmer.

### Langage compréhensible

**✅ À FAIRE** : S'affranchir de tout terme technique pour permettre la compréhension par un plus grand nombre.

**❌ À NE PAS FAIRE** : Ne pas inclure de termes techniques à une alerte, au risque d'altérer la bonne compréhension des usagers.

Employer un langage compréhensible facilement en évitant tout jargon technique.

### Expliciter la nature du message

**✅ À FAIRE** : Préciser la nature du message porté par l'alerte dans son titre.

**❌ À NE PAS FAIRE** : Ne pas s'appuyer uniquement sur l'icône et la couleur de l'alerte pour restituer la nature du message.

Expliciter la nature du message porté par le composant (succès, erreur, information etc.) dans le titre de l'alerte. L'icône et la couleur ne garantissent pas à elles seules la bonne compréhension du message pour la totalité des usagers.

---

## Règles DSFR critiques

### ❌ INTERDIT

- **Ne JAMAIS utiliser** `alert()`, `confirm()`, `prompt()` natifs
- Ne pas modifier les couleurs ou icônes par défaut
- Ne pas utiliser de styles inline pour les couleurs

### ✅ OBLIGATOIRE

- Utiliser uniquement les 4 types définis (info, warning, error, success)
- Respecter la hiérarchie des titres (`<h3>` par défaut)
- Tester en mode sombre (`data-fr-theme="dark"`)
- Ajouter `title="Masquer le message"` sur bouton fermeture

---

## Accessibilité

### Attributs recommandés

- **Pas de** `role="alert"` (retiré en v1.3.0 pour améliorer expérience lecteur d'écran)
- Bouton fermeture avec texte visible "Masquer le message"
- Titre (`fr-alert__title`) pour contexte

### Conformité RGAA 4.1

✅ Le composant Alerte est 100% conforme RGAA 4.1

---

## Notes de version

### v1.11.1 (31/01/2024)
- ✨ Ajout exemple MD avec description seule (#853)

### v1.11.0 (11/12/2023)
- 🐛 Remplacement box-shadow → background-image pour bordures (#742)

### v1.3.1 (07/02/2022)
- Alerte dynamique refermable (#199)
- Ajout exemple dynamique (#194)

### v1.3.0 (18/01/2022)
- 🐛 Retrait attribut `role="alert"` (#182)

---

## Références

- **Documentation DSFR** : https://www.systeme-de-design.gouv.fr/composants/alerte
- **GitHub** : https://github.com/GouvernementFR/dsfr
