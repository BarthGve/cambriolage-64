# Icône

Les icônes fonctionnelles sont des symboles visuels qui accompagnent l'utilisateur dans ses actions et qui aident à sa compréhension de l'interface.

## Utilisation des icônes

Nous mettons à votre disposition une sélection d'icônes, en grande partie issues de la librairie Remix Icons (libre de droits). Il s'agit, pour l'essentiel, des icônes utilisées par les composants du DSFR. Si l'icône recherchée est absente de notre sélection, vous pouvez compléter en recherchant d'abord dans Remix Icons.

### Pour les designers

Les icônes sont disponibles dans les Fondamentaux des librairies Sketch et Figma (section icônes fonctionnelles).

### Pour les développeurs

Les icônes, placées dans `dist/icons`, sont utilisées via des classes CSS disponibles dans `utility/icons/icons.min.css`. Il est de ce fait possible d'utiliser des icônes en utilisant directement la classe CSS associée, reprenant le nom de l'icône SVG, précédée du préfixe `fr-icon`. Exemple : `.fr-icon-error-fill`.

Les icônes sont rangées en catégories (system, business, map…), avec un fichier css pour chacune. Il est donc possible d'importer uniquement les catégories d'icônes désirées pour alléger la CSS.

Le chargement des icônes se fait directement via l'ajout du fichier CSS. Ce fichier contient un chemin relatif vers les icônes SVG, qui sont placées dans le dossier `dist/icons`. Il conviendra de respecter cette structure de dossier pour que les icônes soient correctement chargées.

Il est ensuite possible d'utiliser les classes d'icônes correspondantes, directement sur un composant qui permet d'ajouter une icône, par exemple un bouton :

```html
<button class="fr-btn fr-icon-checkbox-circle-line fr-btn--icon-left">
  Label bouton MD
</button>
```

Il est aussi possible de les utiliser de manière autonome, au sein d'un texte, en utilisant de préférence une balise `<span>`. Exemple :

```html
<span class="fr-icon-error-fill" aria-hidden="true"></span>
```

**Note :** L'ancienne nomenclature des classes en `fr-fi` (remplacée par `fr-icon`) est dépréciée mais toujours fonctionnelle.

## Ajout d'icônes personnalisées

Pour ajouter une icône qui ne serait pas présente dans le DSFR, il est possible de créer un fichier SVG ou de le télécharger depuis la librairie Remixicon. Il faudra ensuite créer un fichier CSS pour associé une classe à cette icône, en suivant la nomenclature `fr-icon-[nom-de-l'icône]`. Par exemple, pour une icône nommée `custom-icon`, le fichier CSS contiendra :

```css
.fr-icon-custom-icon::before,
.fr-icon-custom-icon::after {
  -webkit-mask-image: url("../icons/custom-icon.svg");
  mask-image: url("../icons/custom-icon.svg");
}
```

**[Facultatif]** Pour fonctionner sur Internet Explorer 11, il faudra également ajouter, de préférence dans un autre fichier CSS, la règle suivante :

```css
@media screen and (min-width: 0\0) and (min-resolution: 72dpi) {
  .fr-icon-custom-icon::before,
  .fr-icon-custom-icon::after {
    background-image: url("../icons/custom-icon.svg");
  }
}
```

**Information :** Ne pas modifier directement les fichiers CSS du DSFR, mais plutôt créer un fichier CSS personnalisé pour vos icônes. De cette manière, vous pourrez monter de version du DSFR sans perdre vos modifications.

## Sélection d'icônes

Les icônes doivent être utilisées pour attirer l'attention sur les actions, les ensembles de contenus importants ou les zones clés, il faut éviter d'en utiliser trop sur une même page pour ne pas créer de confusion. Un concept doit être représenté par la même icône sur l'ensemble du site et de l'écosystème numérique de l'État.

Les icônes ci-dessous sont pour la plupart issues de la librairie Remixicon. Les icônes classées dans dsfr sont soit des icônes créées spécialement, soit des icônes issues de Remixicon ayant été renommées afin de plus coller à l'usage.

### Arrows

#### Arrows - Icônes créées par l'équipe DSFR

```html
<span class="fr-icon-arrow-left-s-first-line" aria-hidden="true"></span>
<span class="fr-icon-arrow-right-s-last-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-left-s-line-double" aria-hidden="true"></span>
<span class="fr-icon-arrow-right-s-line-double" aria-hidden="true"></span>
```

#### Arrows - Icônes proposées par RemixIcon

```html
<span class="fr-icon-arrow-left-s-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-left-s-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-right-s-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-right-s-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-down-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-down-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-down-s-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-down-s-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-go-back-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-go-back-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-go-forward-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-go-forward-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-left-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-left-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-right-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-right-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-right-up-line" aria-hidden="true"></span>
<span class="fr-icon-arrow-up-down-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-up-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-up-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-up-s-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-up-s-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-down-circle-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-down-circle-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-left-circle-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-left-circle-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-left-down-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-left-down-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-left-right-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-left-right-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-right-circle-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-right-circle-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-right-down-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-right-down-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-right-up-fill" aria-hidden="true"></span>

<span class="fr-icon-arrow-turn-back-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-turn-back-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-turn-forward-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-turn-forward-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-up-circle-fill" aria-hidden="true"></span>
<span class="fr-icon-arrow-up-circle-line" aria-hidden="true"></span>

<span class="fr-icon-arrow-up-down-fill" aria-hidden="true"></span>

<span class="fr-icon-contract-left-fill" aria-hidden="true"></span>
<span class="fr-icon-contract-left-line" aria-hidden="true"></span>

<span class="fr-icon-contract-left-right-fill" aria-hidden="true"></span>
<span class="fr-icon-contract-left-right-line" aria-hidden="true"></span>

<span class="fr-icon-contract-right-fill" aria-hidden="true"></span>
<span class="fr-icon-contract-right-line" aria-hidden="true"></span>

<span class="fr-icon-contract-up-down-fill" aria-hidden="true"></span>
<span class="fr-icon-contract-up-down-line" aria-hidden="true"></span>

<span class="fr-icon-corner-down-left-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-down-left-line" aria-hidden="true"></span>

<span class="fr-icon-corner-down-right-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-down-right-line" aria-hidden="true"></span>

<span class="fr-icon-corner-left-down-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-left-down-line" aria-hidden="true"></span>

<span class="fr-icon-corner-left-up-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-left-up-line" aria-hidden="true"></span>

<span class="fr-icon-corner-right-down-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-right-down-line" aria-hidden="true"></span>

<span class="fr-icon-corner-right-up-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-right-up-line" aria-hidden="true"></span>

<span class="fr-icon-corner-up-left-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-up-left-line" aria-hidden="true"></span>

<span class="fr-icon-corner-up-right-fill" aria-hidden="true"></span>
<span class="fr-icon-corner-up-right-line" aria-hidden="true"></span>

<span class="fr-icon-expand-left-fill" aria-hidden="true"></span>
<span class="fr-icon-expand-left-line" aria-hidden="true"></span>

<span class="fr-icon-expand-left-right-fill" aria-hidden="true"></span>
<span class="fr-icon-expand-left-right-line" aria-hidden="true"></span>

<span class="fr-icon-expand-right-fill" aria-hidden="true"></span>
<span class="fr-icon-expand-right-line" aria-hidden="true"></span>

<span class="fr-icon-expand-up-down-fill" aria-hidden="true"></span>
<span class="fr-icon-expand-up-down-line" aria-hidden="true"></span>

<span class="fr-icon-skip-down-fill" aria-hidden="true"></span>
<span class="fr-icon-skip-down-line" aria-hidden="true"></span>

<span class="fr-icon-skip-up-fill" aria-hidden="true"></span>
<span class="fr-icon-skip-up-line" aria-hidden="true"></span>
```

### Business

```html
<span class="fr-icon-archive-fill" aria-hidden="true"></span>
<span class="fr-icon-archive-line" aria-hidden="true"></span>

<span class="fr-icon-attachment-fill" aria-hidden="true"></span>
<span class="fr-icon-attachment-line" aria-hidden="true"></span>

<span class="fr-icon-award-fill" aria-hidden="true"></span>
<span class="fr-icon-award-line" aria-hidden="true"></span>

<span class="fr-icon-bar-chart-box-fill" aria-hidden="true"></span>
<span class="fr-icon-bar-chart-box-line" aria-hidden="true"></span>

<span class="fr-icon-bookmark-fill" aria-hidden="true"></span>
<span class="fr-icon-bookmark-line" aria-hidden="true"></span>

<span class="fr-icon-briefcase-fill" aria-hidden="true"></span>
<span class="fr-icon-briefcase-line" aria-hidden="true"></span>

<span class="fr-icon-calendar-2-fill" aria-hidden="true"></span>
<span class="fr-icon-calendar-2-line" aria-hidden="true"></span>

<span class="fr-icon-calendar-event-fill" aria-hidden="true"></span>
<span class="fr-icon-calendar-event-line" aria-hidden="true"></span>

<span class="fr-icon-calendar-fill" aria-hidden="true"></span>
<span class="fr-icon-calendar-line" aria-hidden="true"></span>

<span class="fr-icon-cloud-fill" aria-hidden="true"></span>
<span class="fr-icon-cloud-line" aria-hidden="true"></span>

<span class="fr-icon-copyright-fill" aria-hidden="true"></span>
<span class="fr-icon-copyright-line" aria-hidden="true"></span>

<span class="fr-icon-customer-service-fill" aria-hidden="true"></span>
<span class="fr-icon-customer-service-line" aria-hidden="true"></span>

<span class="fr-icon-flag-fill" aria-hidden="true"></span>
<span class="fr-icon-flag-line" aria-hidden="true"></span>

<span class="fr-icon-global-fill" aria-hidden="true"></span>
<span class="fr-icon-global-line" aria-hidden="true"></span>

<span class="fr-icon-line-chart-fill" aria-hidden="true"></span>
<span class="fr-icon-line-chart-line" aria-hidden="true"></span>

<span class="fr-icon-links-fill" aria-hidden="true"></span>
<span class="fr-icon-links-line" aria-hidden="true"></span>

<span class="fr-icon-mail-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-line" aria-hidden="true"></span>

<span class="fr-icon-mail-open-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-open-line" aria-hidden="true"></span>

<span class="fr-icon-medal-fill" aria-hidden="true"></span>
<span class="fr-icon-medal-line" aria-hidden="true"></span>

<span class="fr-icon-pie-chart-2-fill" aria-hidden="true"></span>
<span class="fr-icon-pie-chart-2-line" aria-hidden="true"></span>

<span class="fr-icon-pie-chart-box-fill" aria-hidden="true"></span>
<span class="fr-icon-pie-chart-box-line" aria-hidden="true"></span>

<span class="fr-icon-printer-fill" aria-hidden="true"></span>
<span class="fr-icon-printer-line" aria-hidden="true"></span>

<span class="fr-icon-profil-fill" aria-hidden="true"></span>
<span class="fr-icon-profil-line" aria-hidden="true"></span>

<span class="fr-icon-projector-2-fill" aria-hidden="true"></span>
<span class="fr-icon-projector-2-line" aria-hidden="true"></span>

<span class="fr-icon-send-plane-fill" aria-hidden="true"></span>
<span class="fr-icon-send-plane-line" aria-hidden="true"></span>

<span class="fr-icon-slideshow-fill" aria-hidden="true"></span>
<span class="fr-icon-slideshow-line" aria-hidden="true"></span>

<span class="fr-icon-window-fill" aria-hidden="true"></span>
<span class="fr-icon-window-line" aria-hidden="true"></span>

<!-- Icônes additionnelles -->
<span class="fr-icon-archive-drawer-fill" aria-hidden="true"></span>
<span class="fr-icon-archive-drawer-line" aria-hidden="true"></span>

<span class="fr-icon-at-fill" aria-hidden="true"></span>
<span class="fr-icon-at-line" aria-hidden="true"></span>

<span class="fr-icon-bar-chart-2-fill" aria-hidden="true"></span>
<span class="fr-icon-bar-chart-2-line" aria-hidden="true"></span>

<span class="fr-icon-bar-chart-fill" aria-hidden="true"></span>
<span class="fr-icon-bar-chart-line" aria-hidden="true"></span>

<span class="fr-icon-bar-chart-horizontal-fill" aria-hidden="true"></span>
<span class="fr-icon-bar-chart-horizontal-line" aria-hidden="true"></span>

<span class="fr-icon-bubble-chart-fill" aria-hidden="true"></span>
<span class="fr-icon-bubble-chart-line" aria-hidden="true"></span>

<span class="fr-icon-calculator-fill" aria-hidden="true"></span>
<span class="fr-icon-calculator-line" aria-hidden="true"></span>

<span class="fr-icon-calendar-check-fill" aria-hidden="true"></span>
<span class="fr-icon-calendar-check-line" aria-hidden="true"></span>

<span class="fr-icon-calendar-close-fill" aria-hidden="true"></span>
<span class="fr-icon-calendar-close-line" aria-hidden="true"></span>

<span class="fr-icon-calendar-todo-fill" aria-hidden="true"></span>
<span class="fr-icon-calendar-todo-line" aria-hidden="true"></span>

<span class="fr-icon-cloud-off-fill" aria-hidden="true"></span>
<span class="fr-icon-cloud-off-line" aria-hidden="true"></span>

<span class="fr-icon-donut-chart-fill" aria-hidden="true"></span>
<span class="fr-icon-donut-chart-line" aria-hidden="true"></span>

<span class="fr-icon-honour-fill" aria-hidden="true"></span>
<span class="fr-icon-honour-line" aria-hidden="true"></span>

<span class="fr-icon-inbox-2-fill" aria-hidden="true"></span>
<span class="fr-icon-inbox-2-line" aria-hidden="true"></span>

<span class="fr-icon-inbox-archive-fill" aria-hidden="true"></span>
<span class="fr-icon-inbox-archive-line" aria-hidden="true"></span>

<span class="fr-icon-inbox-fill" aria-hidden="true"></span>
<span class="fr-icon-inbox-line" aria-hidden="true"></span>

<span class="fr-icon-inbox-unarchive-fill" aria-hidden="true"></span>
<span class="fr-icon-inbox-unarchive-line" aria-hidden="true"></span>

<span class="fr-icon-mail-add-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-add-line" aria-hidden="true"></span>

<span class="fr-icon-mail-check-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-check-line" aria-hidden="true"></span>

<span class="fr-icon-mail-close-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-close-line" aria-hidden="true"></span>

<span class="fr-icon-mail-download-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-download-line" aria-hidden="true"></span>

<span class="fr-icon-mail-forbid-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-forbid-line" aria-hidden="true"></span>

<span class="fr-icon-mail-lock-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-lock-line" aria-hidden="true"></span>

<span class="fr-icon-mail-send-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-send-line" aria-hidden="true"></span>

<span class="fr-icon-mail-settings-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-settings-line" aria-hidden="true"></span>

<span class="fr-icon-mail-star-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-star-line" aria-hidden="true"></span>

<span class="fr-icon-mail-unread-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-unread-line" aria-hidden="true"></span>

<span class="fr-icon-mail-volume-fill" aria-hidden="true"></span>
<span class="fr-icon-mail-volume-line" aria-hidden="true"></span>

<span class="fr-icon-megaphone-fill" aria-hidden="true"></span>
<span class="fr-icon-megaphone-line" aria-hidden="true"></span>

<span class="fr-icon-pass-expired-fill" aria-hidden="true"></span>
<span class="fr-icon-pass-expired-line" aria-hidden="true"></span>

<span class="fr-icon-pass-pending-fill" aria-hidden="true"></span>
<span class="fr-icon-pass-pending-line" aria-hidden="true"></span>

<span class="fr-icon-pass-valid-fill" aria-hidden="true"></span>
<span class="fr-icon-pass-valid-line" aria-hidden="true"></span>

<span class="fr-icon-pie-chart-fill" aria-hidden="true"></span>
<span class="fr-icon-pie-chart-line" aria-hidden="true"></span>

<span class="fr-icon-presentation-fill" aria-hidden="true"></span>
<span class="fr-icon-presentation-line" aria-hidden="true"></span>

<span class="fr-icon-printer-cloud-fill" aria-hidden="true"></span>
<span class="fr-icon-printer-cloud-line" aria-hidden="true"></span>

<span class="fr-icon-record-mail-fill" aria-hidden="true"></span>
<span class="fr-icon-record-mail-line" aria-hidden="true"></span>

<span class="fr-icon-reply-all-fill" aria-hidden="true"></span>
<span class="fr-icon-reply-all-line" aria-hidden="true"></span>

<span class="fr-icon-reply-fill" aria-hidden="true"></span>
<span class="fr-icon-reply-line" aria-hidden="true"></span>

<span class="fr-icon-seo-fill" aria-hidden="true"></span>
<span class="fr-icon-seo-line" aria-hidden="true"></span>

<span class="fr-icon-service-fill" aria-hidden="true"></span>
<span class="fr-icon-service-line" aria-hidden="true"></span>

<span class="fr-icon-shake-hands-fill" aria-hidden="true"></span>
<span class="fr-icon-shake-hands-line" aria-hidden="true"></span>

<span class="fr-icon-stack-fill" aria-hidden="true"></span>
<span class="fr-icon-stack-line" aria-hidden="true"></span>

<span class="fr-icon-window-2-fill" aria-hidden="true"></span>
<span class="fr-icon-window-2-line" aria-hidden="true"></span>
```

### Communication

```html
<span class="fr-icon-chat-2-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-2-line" aria-hidden="true"></span>

<span class="fr-icon-chat-3-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-3-line" aria-hidden="true"></span>

<span class="fr-icon-chat-check-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-check-line" aria-hidden="true"></span>

<span class="fr-icon-chat-delete-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-delete-line" aria-hidden="true"></span>

<span class="fr-icon-chat-poll-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-poll-line" aria-hidden="true"></span>

<span class="fr-icon-discuss-fill" aria-hidden="true"></span>
<span class="fr-icon-discuss-line" aria-hidden="true"></span>

<span class="fr-icon-feedback-fill" aria-hidden="true"></span>
<span class="fr-icon-feedback-line" aria-hidden="true"></span>

<span class="fr-icon-message-2-fill" aria-hidden="true"></span>
<span class="fr-icon-message-2-line" aria-hidden="true"></span>

<span class="fr-icon-question-answer-fill" aria-hidden="true"></span>
<span class="fr-icon-question-answer-line" aria-hidden="true"></span>

<span class="fr-icon-questionnaire-fill" aria-hidden="true"></span>
<span class="fr-icon-questionnaire-line" aria-hidden="true"></span>

<span class="fr-icon-video-chat-fill" aria-hidden="true"></span>
<span class="fr-icon-video-chat-line" aria-hidden="true"></span>

<!-- Icônes additionnelles -->
<span class="fr-icon-chat-download-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-download-line" aria-hidden="true"></span>

<span class="fr-icon-chat-follow-up-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-follow-up-line" aria-hidden="true"></span>

<span class="fr-icon-chat-forward-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-forward-line" aria-hidden="true"></span>

<span class="fr-icon-chat-history-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-history-line" aria-hidden="true"></span>

<span class="fr-icon-chat-new-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-new-line" aria-hidden="true"></span>

<span class="fr-icon-chat-off-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-off-line" aria-hidden="true"></span>

<span class="fr-icon-chat-private-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-private-line" aria-hidden="true"></span>

<span class="fr-icon-chat-quote-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-quote-line" aria-hidden="true"></span>

<span class="fr-icon-chat-settings-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-settings-line" aria-hidden="true"></span>

<span class="fr-icon-chat-upload-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-upload-line" aria-hidden="true"></span>

<span class="fr-icon-chat-voice-fill" aria-hidden="true"></span>
<span class="fr-icon-chat-voice-line" aria-hidden="true"></span>

<span class="fr-icon-emoji-sticker-fill" aria-hidden="true"></span>
<span class="fr-icon-emoji-sticker-line" aria-hidden="true"></span>

<span class="fr-icon-message-3-fill" aria-hidden="true"></span>
<span class="fr-icon-message-3-line" aria-hidden="true"></span>

<span class="fr-icon-speak-fill" aria-hidden="true"></span>
<span class="fr-icon-speak-line" aria-hidden="true"></span>
```

### Design

```html
<span class="fr-icon-ball-pen-fill" aria-hidden="true"></span>
<span class="fr-icon-ball-pen-line" aria-hidden="true"></span>

<span class="fr-icon-brush-3-fill" aria-hidden="true"></span>
<span class="fr-icon-brush-3-line" aria-hidden="true"></span>

<span class="fr-icon-brush-fill" aria-hidden="true"></span>
<span class="fr-icon-brush-line" aria-hidden="true"></span>

<span class="fr-icon-contrast-fill" aria-hidden="true"></span>
<span class="fr-icon-contrast-line" aria-hidden="true"></span>

<span class="fr-icon-crop-fill" aria-hidden="true"></span>
<span class="fr-icon-crop-line" aria-hidden="true"></span>

<span class="fr-icon-drag-move-2-fill" aria-hidden="true"></span>
<span class="fr-icon-drag-move-2-line" aria-hidden="true"></span>

<span class="fr-icon-drop-fill" aria-hidden="true"></span>
<span class="fr-icon-drop-line" aria-hidden="true"></span>

<span class="fr-icon-edit-box-fill" aria-hidden="true"></span>
<span class="fr-icon-edit-box-line" aria-hidden="true"></span>

<span class="fr-icon-edit-fill" aria-hidden="true"></span>
<span class="fr-icon-edit-line" aria-hidden="true"></span>

<span class="fr-icon-ink-bottle-fill" aria-hidden="true"></span>
<span class="fr-icon-ink-bottle-line" aria-hidden="true"></span>

<span class="fr-icon-layout-grid-fill" aria-hidden="true"></span>
<span class="fr-icon-layout-grid-line" aria-hidden="true"></span>

<span class="fr-icon-mark-pen-fill" aria-hidden="true"></span>
<span class="fr-icon-mark-pen-line" aria-hidden="true"></span>

<span class="fr-icon-paint-brush-fill" aria-hidden="true"></span>
<span class="fr-icon-paint-brush-line" aria-hidden="true"></span>

<span class="fr-icon-paint-fill" aria-hidden="true"></span>
<span class="fr-icon-paint-line" aria-hidden="true"></span>

<span class="fr-icon-palette-fill" aria-hidden="true"></span>
<span class="fr-icon-palette-line" aria-hidden="true"></span>

<span class="fr-icon-pantone-fill" aria-hidden="true"></span>
<span class="fr-icon-pantone-line" aria-hidden="true"></span>

<span class="fr-icon-pen-nib-fill" aria-hidden="true"></span>
<span class="fr-icon-pen-nib-line" aria-hidden="true"></span>

<span class="fr-icon-pencil-fill" aria-hidden="true"></span>
<span class="fr-icon-pencil-line" aria-hidden="true"></span>

<span class="fr-icon-pencil-ruler-fill" aria-hidden="true"></span>
<span class="fr-icon-pencil-ruler-line" aria-hidden="true"></span>

<span class="fr-icon-sip-fill" aria-hidden="true"></span>
<span class="fr-icon-sip-line" aria-hidden="true"></span>

<span class="fr-icon-shapes-fill" aria-hidden="true"></span>
<span class="fr-icon-shapes-line" aria-hidden="true"></span>

<span class="fr-icon-table-fill" aria-hidden="true"></span>
<span class="fr-icon-table-line" aria-hidden="true"></span>

<span class="fr-icon-eraser-fill" aria-hidden="true"></span>
<span class="fr-icon-eraser-line" aria-hidden="true"></span>

<!-- Icônes additionnelles disponibles dans la catégorie Design -->
<span class="fr-icon-anticlockwise-fill" aria-hidden="true"></span>
<span class="fr-icon-anticlockwise-line" aria-hidden="true"></span>

<span class="fr-icon-artboard-fill" aria-hidden="true"></span>
<span class="fr-icon-artboard-line" aria-hidden="true"></span>

<span class="fr-icon-scissors-fill" aria-hidden="true"></span>
<span class="fr-icon-scissors-line" aria-hidden="true"></span>

<!-- Voir documentation complète pour la liste exhaustive -->
```

### Development

```html
<span class="fr-icon-bug-fill" aria-hidden="true"></span>
<span class="fr-icon-bug-line" aria-hidden="true"></span>

<span class="fr-icon-code-box-fill" aria-hidden="true"></span>
<span class="fr-icon-code-box-line" aria-hidden="true"></span>

<span class="fr-icon-code-s-slash-line" aria-hidden="true"></span>

<span class="fr-icon-cursor-fill" aria-hidden="true"></span>
<span class="fr-icon-cursor-line" aria-hidden="true"></span>

<span class="fr-icon-git-branch-fill" aria-hidden="true"></span>
<span class="fr-icon-git-branch-line" aria-hidden="true"></span>

<span class="fr-icon-git-commit-fill" aria-hidden="true"></span>
<span class="fr-icon-git-commit-line" aria-hidden="true"></span>

<span class="fr-icon-git-merge-fill" aria-hidden="true"></span>
<span class="fr-icon-git-merge-line" aria-hidden="true"></span>

<span class="fr-icon-git-pull-request-fill" aria-hidden="true"></span>
<span class="fr-icon-git-pull-request-line" aria-hidden="true"></span>

<span class="fr-icon-git-repository-commits-fill" aria-hidden="true"></span>
<span class="fr-icon-git-repository-commits-line" aria-hidden="true"></span>

<span class="fr-icon-git-repository-fill" aria-hidden="true"></span>
<span class="fr-icon-git-repository-line" aria-hidden="true"></span>

<span class="fr-icon-git-repository-private-fill" aria-hidden="true"></span>
<span class="fr-icon-git-repository-private-line" aria-hidden="true"></span>

<span class="fr-icon-terminal-box-fill" aria-hidden="true"></span>
<span class="fr-icon-terminal-box-line" aria-hidden="true"></span>

<span class="fr-icon-terminal-line" aria-hidden="true"></span>

<span class="fr-icon-terminal-window-fill" aria-hidden="true"></span>
<span class="fr-icon-terminal-window-line" aria-hidden="true"></span>

<!-- Icônes additionnelles -->
<span class="fr-icon-braces-fill" aria-hidden="true"></span>
<span class="fr-icon-braces-line" aria-hidden="true"></span>

<span class="fr-icon-brackets-fill" aria-hidden="true"></span>
<span class="fr-icon-brackets-line" aria-hidden="true"></span>

<span class="fr-icon-code-fill" aria-hidden="true"></span>
<span class="fr-icon-code-line" aria-hidden="true"></span>

<span class="fr-icon-command-fill" aria-hidden="true"></span>
<span class="fr-icon-command-line" aria-hidden="true"></span>

<span class="fr-icon-css3-fill" aria-hidden="true"></span>
<span class="fr-icon-css3-line" aria-hidden="true"></span>

<span class="fr-icon-html5-fill" aria-hidden="true"></span>
<span class="fr-icon-html5-line" aria-hidden="true"></span>

<span class="fr-icon-javascript-fill" aria-hidden="true"></span>
<span class="fr-icon-javascript-line" aria-hidden="true"></span>
```

### Device

```html
<span class="fr-icon-bluetooth-fill" aria-hidden="true"></span>
<span class="fr-icon-bluetooth-line" aria-hidden="true"></span>

<span class="fr-icon-computer-fill" aria-hidden="true"></span>
<span class="fr-icon-computer-line" aria-hidden="true"></span>

<span class="fr-icon-database-fill" aria-hidden="true"></span>
<span class="fr-icon-database-line" aria-hidden="true"></span>

<span class="fr-icon-phone-fill" aria-hidden="true"></span>
<span class="fr-icon-phone-line" aria-hidden="true"></span>

<span class="fr-icon-smartphone-fill" aria-hidden="true"></span>
<span class="fr-icon-smartphone-line" aria-hidden="true"></span>

<span class="fr-icon-tablet-fill" aria-hidden="true"></span>
<span class="fr-icon-tablet-line" aria-hidden="true"></span>

<span class="fr-icon-wifi-fill" aria-hidden="true"></span>
<span class="fr-icon-wifi-line" aria-hidden="true"></span>

<!-- Voir documentation complète pour la liste exhaustive -->
```

### Media

```html
<span class="fr-icon-camera-fill" aria-hidden="true"></span>
<span class="fr-icon-camera-line" aria-hidden="true"></span>

<span class="fr-icon-image-fill" aria-hidden="true"></span>
<span class="fr-icon-image-line" aria-hidden="true"></span>

<span class="fr-icon-pause-circle-fill" aria-hidden="true"></span>
<span class="fr-icon-pause-circle-line" aria-hidden="true"></span>

<span class="fr-icon-play-circle-fill" aria-hidden="true"></span>
<span class="fr-icon-play-circle-line" aria-hidden="true"></span>

<span class="fr-icon-volume-down-fill" aria-hidden="true"></span>
<span class="fr-icon-volume-down-line" aria-hidden="true"></span>

<span class="fr-icon-volume-mute-fill" aria-hidden="true"></span>
<span class="fr-icon-volume-mute-line" aria-hidden="true"></span>

<span class="fr-icon-volume-up-fill" aria-hidden="true"></span>
<span class="fr-icon-volume-up-line" aria-hidden="true"></span>
```

### System

#### System - Icônes créées par l'équipe DSFR

```html
<span aria-hidden="true" class="fr-icon-add-line"></span>
<span aria-hidden="true" class="fr-icon-check-line"></span>
<span aria-hidden="true" class="fr-icon-close-line"></span>
<span aria-hidden="true" class="fr-icon-menu-fill"></span>
<span aria-hidden="true" class="fr-icon-menu-2-fill"></span>
<span aria-hidden="true" class="fr-icon-subtract-line"></span>
```

#### System - Icônes proposées par RemixIcon

```html
<span aria-hidden="true" class="fr-icon-add-circle-fill"></span>
<span aria-hidden="true" class="fr-icon-add-circle-line"></span>

<span aria-hidden="true" class="fr-icon-alarm-warning-fill"></span>
<span aria-hidden="true" class="fr-icon-alarm-warning-line"></span>

<span aria-hidden="true" class="fr-icon-alert-fill"></span>
<span aria-hidden="true" class="fr-icon-alert-line"></span>

<span aria-hidden="true" class="fr-icon-checkbox-fill"></span>
<span aria-hidden="true" class="fr-icon-checkbox-line"></span>

<span aria-hidden="true" class="fr-icon-checkbox-circle-fill"></span>
<span aria-hidden="true" class="fr-icon-checkbox-circle-line"></span>

<span aria-hidden="true" class="fr-icon-close-circle-fill"></span>
<span aria-hidden="true" class="fr-icon-close-circle-line"></span>

<span aria-hidden="true" class="fr-icon-delete-fill"></span>
<span aria-hidden="true" class="fr-icon-delete-line"></span>

<span aria-hidden="true" class="fr-icon-download-fill"></span>
<span aria-hidden="true" class="fr-icon-download-line"></span>

<span aria-hidden="true" class="fr-icon-error-warning-fill"></span>
<span aria-hidden="true" class="fr-icon-error-warning-line"></span>

<span aria-hidden="true" class="fr-icon-external-link-fill"></span>
<span aria-hidden="true" class="fr-icon-external-link-line"></span>

<span aria-hidden="true" class="fr-icon-eye-fill"></span>
<span aria-hidden="true" class="fr-icon-eye-line"></span>

<span aria-hidden="true" class="fr-icon-eye-off-fill"></span>
<span aria-hidden="true" class="fr-icon-eye-off-line"></span>

<span aria-hidden="true" class="fr-icon-filter-fill"></span>
<span aria-hidden="true" class="fr-icon-filter-line"></span>

<span aria-hidden="true" class="fr-icon-information-fill"></span>
<span aria-hidden="true" class="fr-icon-information-line"></span>

<span aria-hidden="true" class="fr-icon-lock-fill"></span>
<span aria-hidden="true" class="fr-icon-lock-line"></span>

<span aria-hidden="true" class="fr-icon-lock-unlock-fill"></span>
<span aria-hidden="true" class="fr-icon-lock-unlock-line"></span>

<span aria-hidden="true" class="fr-icon-logout-box-r-fill"></span>
<span aria-hidden="true" class="fr-icon-logout-box-r-line"></span>

<span aria-hidden="true" class="fr-icon-more-fill"></span>
<span aria-hidden="true" class="fr-icon-more-line"></span>

<span aria-hidden="true" class="fr-icon-notification-badge-fill"></span>
<span aria-hidden="true" class="fr-icon-notification-badge-line"></span>

<span aria-hidden="true" class="fr-icon-question-fill"></span>
<span aria-hidden="true" class="fr-icon-question-line"></span>

<span aria-hidden="true" class="fr-icon-refresh-fill"></span>
<span aria-hidden="true" class="fr-icon-refresh-line"></span>

<span aria-hidden="true" class="fr-icon-search-fill"></span>
<span aria-hidden="true" class="fr-icon-search-line"></span>

<span aria-hidden="true" class="fr-icon-settings-5-fill"></span>
<span aria-hidden="true" class="fr-icon-settings-5-line"></span>

<span aria-hidden="true" class="fr-icon-share-fill"></span>
<span aria-hidden="true" class="fr-icon-share-line"></span>

<span aria-hidden="true" class="fr-icon-shield-fill"></span>
<span aria-hidden="true" class="fr-icon-shield-line"></span>

<span aria-hidden="true" class="fr-icon-star-fill"></span>
<span aria-hidden="true" class="fr-icon-star-line"></span>

<span aria-hidden="true" class="fr-icon-star-s-fill"></span>
<span aria-hidden="true" class="fr-icon-star-s-line"></span>

<span aria-hidden="true" class="fr-icon-time-fill"></span>
<span aria-hidden="true" class="fr-icon-time-line"></span>

<span aria-hidden="true" class="fr-icon-timer-fill"></span>
<span aria-hidden="true" class="fr-icon-timer-line"></span>

<span aria-hidden="true" class="fr-icon-upload-fill"></span>
<span aria-hidden="true" class="fr-icon-upload-line"></span>

<span aria-hidden="true" class="fr-icon-zoom-in-fill"></span>
<span aria-hidden="true" class="fr-icon-zoom-in-line"></span>

<span aria-hidden="true" class="fr-icon-zoom-out-fill"></span>
<span aria-hidden="true" class="fr-icon-zoom-out-line"></span>
```

### User

```html
<span class="fr-icon-account-circle-fill" aria-hidden="true"></span>
<span class="fr-icon-account-circle-line" aria-hidden="true"></span>

<span class="fr-icon-account-fill" aria-hidden="true"></span>
<span class="fr-icon-account-line" aria-hidden="true"></span>

<span class="fr-icon-group-fill" aria-hidden="true"></span>
<span class="fr-icon-group-line" aria-hidden="true"></span>

<span class="fr-icon-team-fill" aria-hidden="true"></span>
<span class="fr-icon-team-line" aria-hidden="true"></span>

<span class="fr-icon-user-fill" aria-hidden="true"></span>
<span class="fr-icon-user-line" aria-hidden="true"></span>

<span class="fr-icon-user-add-fill" aria-hidden="true"></span>
<span class="fr-icon-user-add-line" aria-hidden="true"></span>

<span class="fr-icon-user-search-fill" aria-hidden="true"></span>
<span class="fr-icon-user-search-line" aria-hidden="true"></span>
```

### Weather

```html
<span class="fr-icon-cloudy-2-fill" aria-hidden="true"></span>
<span class="fr-icon-cloudy-2-line" aria-hidden="true"></span>

<span class="fr-icon-moon-fill" aria-hidden="true"></span>
<span class="fr-icon-moon-line" aria-hidden="true"></span>

<span class="fr-icon-fire-line" aria-hidden="true"></span>
<span class="fr-icon-fire-fill" aria-hidden="true"></span>

<span class="fr-icon-flood-line" aria-hidden="true"></span>
<span class="fr-icon-flood-fill" aria-hidden="true"></span>

<span class="fr-icon-snowy-fill" aria-hidden="true"></span>
<span class="fr-icon-snowy-line" aria-hidden="true"></span>

<span class="fr-icon-temp-cold-fill" aria-hidden="true"></span>
<span class="fr-icon-temp-cold-line" aria-hidden="true"></span>

<span class="fr-icon-windy-fill" aria-hidden="true"></span>
<span class="fr-icon-windy-line" aria-hidden="true"></span>
```

## Tailles

Les icônes sont disponibles en quatre tailles. Il est possible de modifier la taille des icônes à l'aide de modifiers spécifiques.

| Taille | Token | Classe | Dimension | Contexte d'utilisation |
|--------|-------|--------|-----------|------------------------|
| XS | `$xs` | `.fr-icon--sm` | 16x16px - 1rem | À utiliser avec la typographie Extra Small (XS), et Small (SM) |
| MD | `$md` | `.fr-icon` | 24x24px - 1.5rem | À utiliser avec la typographie Medium (MD). Taille par défaut, aucun modifiers |
| LG | `$lg` | `.fr-icon--lg` | 32x32px - 2rem | À utiliser avec la typographie Large (LG) |

## Règles d'utilisation

Les icônes fonctionnelles sont des symboles visuels utilisés pour représenter des idées, des objets ou des actions. Ils communiquent un message direct et attirent l'attention sur des informations importantes.

### Couleur

La couleur choisie pour vos icônes doit être issue des couleurs du DSFR. Lorsqu'une icône est rattachée à un label, elle prend automatiquement la couleur de ce label.

### Alignement et marge

L'icône doit être alignée en hauteur par rapport au libellé qui l'accompagne. Pour les marges externes, vous pouvez consulter la documentation espacements.
