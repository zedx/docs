# Evénements

- [Introduction](#introduction)
- [Evénements disponibles](#available-events)

<a name="introduction"></a>
## Introduction

ZEDx comprend une variété d'événements.

Chaque fois que quelque chose d'important est sur le point de se produire, qui se passe, ou qui vient d'arriver, ZEDx déclenche un `Evénement`. En tant que développeur d'extension, votre travail est assez simple: `Ecouter` les événements qui vous intéressent, et réagir en conséquence.

Par exemple :

<div class="content-list" markdown="1">
- Quand une `Annonce` est validée par un administrateur, ZEDx déclenche l'événement `AdWasValidated`. Une extension "Twitter Feed" pourrait écouter cet événement et réagir en envoyant un tweet avec le titre et l'URL de l'annonce.
- Lorsqu'une `Annonce` est sur le point d'être créée par un utilisateur, ZEDx déclenche l'événement `AdWillBeCreated`. Une extension "NoSpam" pourrait écouter cet événement et réagir en vérifiant le contenu de l'annonce.
</div>

Vous avez une idée? Super!

<a name="available-events"></a>
## Evénements disponibles

<style>
    .collection-method-list > p {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
    }

    .collection-method-list a {
        display: block;
    }
</style>

### Annonce

<div class="collection-method-list" markdown="1">
[AdRenewRequested](#AdRenewRequested)
[AdWasBanned](#AdWasBanned)
[AdWasCreated](#AdWasCreated)
[AdWasDeleted](#AdWasDeleted)
[AdWasExpired](#AdWasExpired)
[AdWasHold](#AdWasHold)
[AdWasUpdated](#AdWasUpdated)
[AdWasValidated](#AdWasValidated)
[AdWillBeCreated](#AdWillBeCreated)
[AdWillBeDeleted](#AdWillBeDeleted)
[AdWillBeDisplayed](#AdWillBeDisplayed)
[AdWillBeModerated](#AdWillBeModerated)
[AdWillBePreviewed](#AdWillBePreviewed)
[AdWillBeUpdated](#AdWillBeUpdated)
</div>

### Administration

<div class="collection-method-list" markdown="1">
[AdminWasLoggedIn](#AdminWasLoggedIn)
[AdminWasUpdated](#AdminWasUpdated)
[AdminWillBeLoggedOut](#AdminWillBeLoggedOut)
[AdminWillBeUpdated](#AdminWillBeUpdated)
</div>

### Type d'annonce

<div class="collection-method-list" markdown="1">
[AdtypeWasCreated](#AdtypeWasCreated)
[AdtypeWasDeleted](#AdtypeWasDeleted)
[AdtypeWasPurchased](#AdtypeWasPurchased)
[AdtypeWasUpdated](#AdtypeWasUpdated)
[AdtypeWillBeCreated](#AdtypeWillBeCreated)
[AdtypeWillBeDeleted](#AdtypeWillBeDeleted)
[AdtypeWillBeUpdated](#AdtypeWillBeUpdated)
</div>

### Cache

<div class="collection-method-list" markdown="1">
[CacheAdminWasUpdated](#CacheAdminWasUpdated)
[CacheAdtypeWasUpdated](#CacheAdtypeWasUpdated)
[CacheAdWasUpdated](#CacheAdWasUpdated)
[CacheCategoryWasUpdated](#CacheCategoryWasUpdated)
[CacheFieldWasUpdated](#CacheFieldWasUpdated)
[CacheIpWasUpdated](#CacheIpWasUpdated)
[CacheMenuWasUpdated](#CacheMenuWasUpdated)
[CachePageWasUpdated](#CachePageWasUpdated)
[CacheSettingWasUpdated](#CacheSettingWasUpdated)
[CacheSubscriptionWasUpdated](#CacheSubscriptionWasUpdated)
[CacheTemplateWasUpdated](#CacheTemplateWasUpdated)
[CacheUserWasUpdated](#CacheUserWasUpdated)
</div>

### Catégorie

<div class="collection-method-list" markdown="1">
[CategoryWasCreated](#CategoryWasCreated)
[CategoryWasDeleted](#CategoryWasDeleted)
[CategoryWasMoved](#CategoryWasMoved)
[CategoryWasUpdated](#CategoryWasUpdated)
</div>

### Champ

<div class="collection-method-list" markdown="1">
[FieldWasCreated](#FieldWasCreated)
[FieldWasDeleted](#FieldWasDeleted)
[FieldWasUpdated](#FieldWasUpdated)
[FieldWillBeCreated](#FieldWillBeCreated)
[FieldWillBeUpdated](#FieldWillBeUpdated)
</div>

### Ip

<div class="collection-method-list" markdown="1">
[IpWillBeBlacklisted](#IpWillBeBlacklisted)
[IpWillBeRemovedFromBlacklist](#IpWillBeRemovedFromBlacklist)
[IpWillBeRemovedFromWhitelist](#IpWillBeRemovedFromWhitelist)
[IpWillBeWhitelisted](#IpWillBeWhitelisted)
</div>

### Menu

<div class="collection-method-list" markdown="1">
[MenuWasCreated](#MenuWasCreated)
[MenuWasDeleted](#MenuWasDeleted)
[MenuWasMoved](#MenuWasMoved)
[MenuWasUpdated](#MenuWasUpdated)
[MenuWillBeCreated](#MenuWillBeCreated)
[MenuWillBeUpdated](#MenuWillBeUpdated)
</div>

### Page

<div class="collection-method-list" markdown="1">
[PageTemplateWasSwitched](#PageTemplateWasSwitched)
[PageThemeelementWasAttached](#PageThemeelementWasAttached)
[PageThemeelementWasDetached](#PageThemeelementWasDetached)
[PageWasCreated](#PageWasCreated)
[PageWasDeleted](#PageWasDeleted)
[PageWasUpdated](#PageWasUpdated)
[PageWillBeCreated](#PageWillBeCreated)
[PageWillBeUpdated](#PageWillBeUpdated)
</div>

### Paiement

<div class="collection-method-list" markdown="1">
[PaymentWasReceived](#PaymentWasReceived)
</div>

### Moteur de recherche

<div class="collection-method-list" markdown="1">
[SearchEngineRequested](#SearchEngineRequested)
[SearchEngineWillRender](#SearchEngineWillRender)
</div>

### Réglage

<div class="collection-method-list" markdown="1">
[SettingWasUpdated](#SettingWasUpdated)
[SettingWillBeUpdated](#SettingWillBeUpdated)
</div>

### Abonnement

<div class="collection-method-list" markdown="1">
[SubscriptionWasCreated](#SubscriptionWasCreated)
[SubscriptionWasDeleted](#SubscriptionWasDeleted)
[SubscriptionWasPurchased](#SubscriptionWasPurchased)
[SubscriptionWasSwaped](#SubscriptionWasSwaped)
[SubscriptionWasUpdated](#SubscriptionWasUpdated)
[SubscriptionWillBeCreated](#SubscriptionWillBeCreated)
[SubscriptionWillBeUpdated](#SubscriptionWillBeUpdated)
</div>

### Template

<div class="collection-method-list" markdown="1">
[TemplateWasCreated](#TemplateWasCreated)
[TemplateWasDeleted](#TemplateWasDeleted)
[TemplateWasUpdated](#TemplateWasUpdated)
[TemplateWillBeCreated](#TemplateWillBeCreated)
[TemplateWillBeUpdated](#TemplateWillBeUpdated)
</div>

### Utilisateur

<div class="collection-method-list" markdown="1">
[UserWasCreated](#UserWasCreated)
[UserWasDeleted](#UserWasDeleted)
[UserWasUpdated](#UserWasUpdated)
[UserWillBeCreated](#UserWillBeCreated)
[UserWillBeDeleted](#UserWillBeDeleted)
[UserWillBeUpdated](#UserWillBeUpdated)
</div>
