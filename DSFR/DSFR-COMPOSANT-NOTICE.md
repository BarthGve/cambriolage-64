# Bandeau d'information importante (Notice)

Le bandeau d'information importante est un élément éditorial permettant d'attirer l'attention des usagers sur une information importante et temporaire.

## Quand utiliser ce composant ?

Utiliser le bandeau d'information importante pour permettre aux usagers d'être informés ou d'accéder à une information primordiale ou urgente, de façon temporaire.

**Information** : Le bandeau d'information importante n'est pas conçu pour relayer une actualité, une information secondaire ou tout autre contenu informatif d'un site qui ne concernerait pas directement l'usager. Une utilisation excessive ou continue de ce type de bandeaux risquerait de rendre le composant invisible aux yeux des usagers, en les habituant à sa présence.

## Comment utiliser ce composant ?

- Placer le bandeau d'information importante directement sous la navigation principale, et visible sur toutes les pages du site, quel que soit l'appareil utilisé.
- Transmettre l'essentiel de l'information dans le contenu du bandeau. Il est toutefois possible d'ajouter un lien permettant de renvoyer l'usager vers une source d'information complète.

### À FAIRE

✅ Permettre à l'usager d'obtenir l'information principale à la seule lecture du bandeau d'information importante.

### À NE PAS FAIRE

❌ Ne pas forcer l'usager à devoir consulter une source complémentaire pour comprendre l'information relayée.

## Anatomie du composant

1. **Une icône** — obligatoire et normée pour les bandeaux de vigilance météo et les bandeaux d'alertes — En option
2. **Un titre en gras** — normé pour les bandeaux de vigilance météo et les bandeaux d'alertes — Obligatoire
3. **Une description** — recommandée pour apporter du contexte — En option
4. **Un lien** — obligatoire et normé pour les bandeaux de vigilance météo et les bandeaux d'alertes — En option
5. **Un fond** — Obligatoire
6. **Une croix de fermeture** — En option

## Variations

### Bandeaux génériques

#### Bandeau d'information importante (par défaut)

Utiliser le bandeau d'information importante pour afficher une information exceptionnelle, mais non critique pour la santé ou la sécurité de l'utilisateur.

```html
<div class="fr-notice fr-notice--info">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Titre du bandeau d'information</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

#### Bandeau d'avertissement

Utiliser le bandeau d'avertissement pour afficher une information qui peut affecter l'usager dans son usage du service (indisponibilité majeure du site ou d'une démarche importante par exemple) ou pour avertir d'un risque de sécurité lié au site ou au service (risque de phishing, usurpations etc.)

```html
<div class="fr-notice fr-notice--warning">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Titre du bandeau d'avertissement</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

#### Bandeau d'alerte

Utiliser le bandeau d'alerte pour afficher une information critique pour la santé ou la sécurité de l'utilisateur.

```html
<div class="fr-notice fr-notice--alert">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Titre du bandeau d'alerte</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

### Bandeaux de vigilance météo

Ces bandeaux servent à relayer des informations sur les niveaux de vigilance et risques météorologiques communiqués par Météo France.

Le Système de Design de l'État prévoit que ces bandeaux soient affichés à partir du niveau de vigilance orange. Les niveaux de vigilance vert et jaune ne justifiant pas d'afficher un bandeau d'information sur les sites de l'État.

#### Vigilance orange

Utiliser ce niveau de vigilance lorsque des phénomènes dangereux sont prévus. Son rôle est d'inciter l'usager à suivre l'évolution de la situation ainsi que les conseils de sécurité émis par les pouvoirs publics.

```html
<div class="fr-notice fr-notice--weather-orange">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Vigilance météo orange</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

#### Vigilance rouge

Utiliser ce niveau de vigilance lorsque des phénomènes dangereux, d'intensité exceptionnelle, sont prévus. Il doit inciter l'usager à suivre la situation et à impérativement respecter les consignes de sécurité émises par les pouvoirs publics.

```html
<div class="fr-notice fr-notice--weather-red">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Vigilance météo rouge</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

#### Vigilance violette

Réserver ce niveau de vigilance aux territoires ultra-marins où les phénomènes météorologiques liés aux cyclones y font l'objet de dispositifs d'alertes spécifiques à chaque territoire ou région, donnant lieu à une couleur d'alerte violette figurant le niveau d'alerte maximale.

```html
<div class="fr-notice fr-notice--weather-purple">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Vigilance météo violette</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

**Attention** : La vigilance violette ne fait pas partie du référentiel de Météo France, mais à un référentiel différent : celui de l'alerte cyclonique.

### Bandeaux d'alertes

Les bandeaux d'alerte sont conçus pour relayer des alertes relatifs aux risques majeurs pour la Nation, mettant en danger la sécurité des biens et des personnes. Ils sont utilisables uniquement dans les cas précis pour lesquels ils sont prévus.

#### Alerte attentat

Afficher ce bandeau uniquement lorsqu'un attentat est en cours. Cette information étant émise par le Ministère de l'Intérieur, les intitulés officiels doivent être respectés.

```html
<div class="fr-notice fr-notice--attack">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Attentat en cours</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

**Attention** : Ne pas utiliser ce bandeau pour signifier un relèvement, un abaissement ou le niveau en cours du plan Vigipirate : il s'agit d'une information et non d'une alerte.

#### Appel à témoins

Afficher ce bandeau uniquement lorsqu'un appel à témoins est émis par le Ministère de l'Intérieur ou une préfecture. Les intitulés officiels doivent être respectés.

```html
<div class="fr-notice fr-notice--witness">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Appel à témoins</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

#### Alerte technologique

Afficher ce bandeau uniquement en cas de cyber-attaque d'ampleur nationale ou d'alerte technologique émise par le Ministère de l'Intérieur. Les intitulés officiels doivent être respectés.

```html
<div class="fr-notice fr-notice--cyberattack">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Cyber-attaque</span>
                <span class="fr-notice__desc">Texte de description lorem ipsum sit consectetur adipiscing.</span>
                <a title="Lien de consultation - nouvelle fenêtre" href="#" target="_blank" rel="noopener external" class="fr-notice__link">Lien de consultation</a>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

## Variante avec icône personnalisée

Le composant Bandeau d'information importante comporte une icône par défaut qui peut être personnalisée avec l'utilisation d'une classe utilitaire d'icône `fr-icon--NOM-ICONE` sur le conteneur du titre du bandeau.

```html
<div class="fr-notice fr-notice--info">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title fr-icon-virus-fill">Titre du bandeau</span>
            </p>
        </div>
    </div>
</div>
```

## Variante avec bouton de fermeture

Le composant Bandeau d'information importante peut comporter un bouton de fermeture pour permettre à l'utilisateur de fermer le bandeau.

```html
<div class="fr-notice fr-notice--info">
    <div class="fr-container">
        <div class="fr-notice__body">
            <p>
                <span class="fr-notice__title">Titre du bandeau</span>
            </p>
            <button title="Masquer le message" onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)" type="button" class="fr-btn--close fr-btn">Masquer le message</button>
        </div>
    </div>
</div>
```

## Installation CSS

Pour fonctionner correctement le style CSS du composant et de ses dépendances doivent être importés.

### Dépendances CSS

| Dépendance | Obligatoire | Remarque |
|------------|-------------|----------|
| Core | Oui | |
| notice | Oui | |
| Button | Non | Uniquement sur la variation refermable |

### Exemple d'imports CSS

```html
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/core/core.min.css" rel="stylesheet">
<link href="https://cdn.jsdelivr.net/npm/@gouvfr/dsfr@latest/dist/component/notice/notice.min.css" rel="stylesheet">
```

## JavaScript

Le composant Bandeau d'information importante nécessite un JavaScript minimal pour la gestion de la fermeture du bandeau. En cliquant sur le bouton de fermeture, le bandeau est retiré du DOM grâce à un événement JavaScript.

### Fermeture du bandeau

Le bouton de fermeture doit être lié à une fonction JavaScript pour supprimer le bandeau du DOM. Voici un exemple de code en javascript vanilla pour gérer la suppression du bandeau :

```javascript
document.querySelector('.fr-notice__close').addEventListener('click', function() {
  this.closest('.fr-notice').remove();
});
```

Ou directement dans l'attribut `onclick` du bouton :

```html
<button
  title="Masquer le message"
  onclick="const notice = this.parentNode.parentNode.parentNode; notice.parentNode.removeChild(notice)"
  type="button"
  class="fr-btn--close fr-btn">
  Masquer le message
</button>
```

## Personnalisation

Le bandeau d'information importante n'est pas personnalisable. Toutefois, certains éléments sont optionnels.

### À FAIRE

✅ Conserver les icônes et couleurs de fond proposées par défaut, chacune étant liée à un cas d'usage spécifique.

### À NE PAS FAIRE

❌ Ne pas personnaliser les icônes et couleurs de fond, au risque de compromettre le message transmis et sa bonne compréhension par l'usager.

## Classes CSS

### Classes principales

- `.fr-notice` - Conteneur principal du bandeau
- `.fr-notice__body` - Corps du bandeau
- `.fr-notice__title` - Titre du bandeau (obligatoire)
- `.fr-notice__desc` - Description (optionnel)
- `.fr-notice__link` - Lien (optionnel)

### Classes de variation

**Bandeaux génériques :**
- `.fr-notice--info` - Bandeau d'information (par défaut)
- `.fr-notice--warning` - Bandeau d'avertissement
- `.fr-notice--alert` - Bandeau d'alerte

**Vigilance météo :**
- `.fr-notice--weather-orange` - Vigilance orange
- `.fr-notice--weather-red` - Vigilance rouge
- `.fr-notice--weather-purple` - Vigilance violette

**Alertes :**
- `.fr-notice--attack` - Alerte attentat
- `.fr-notice--witness` - Appel à témoins
- `.fr-notice--cyberattack` - Alerte technologique

## Règles éditoriales

### Bandeaux de vigilance météo

- Inclure le nom du phénomène météorologique en plus du niveau de vigilance au titre du bandeau
- Préciser une zone géographique et une temporalité au sein du texte d'accompagnement
- Respecter les termes définis par la circulaire interministérielle et les icônes associées

**Phénomènes couverts :**
- Vent
- Orages
- Pluie-Inondation
- Vagues-submersion
- Grand froid
- Canicule
- Avalanches
- Neige-Verglas
